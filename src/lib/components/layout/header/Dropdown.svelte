<script lang="ts">
	import { onMount } from 'svelte';
	import { writable } from 'svelte/store';

	interface Item {
		href: string;
		description: string;
	}

	export let items: Item[] = [];
	export let buttonId: string = '';
	export let dropdownId: string = '';
	export let label: string = '';

	const isOpen = writable(false);

	function toggleDropdown() {
		isOpen.update((n) => !n);
	}

	function handleClickOutside(event: MouseEvent) {
		const dropdown = document.getElementById(dropdownId);
		const button = document.getElementById(buttonId);
		if (
			dropdown &&
			button &&
			!dropdown.contains(event.target as Node) &&
			!button.contains(event.target as Node)
		) {
			isOpen.set(false);
		}
	}

	onMount(() => {
		document.addEventListener('click', handleClickOutside);
		return () => {
			document.removeEventListener('click', handleClickOutside);
		};
	});
</script>

<button id={buttonId} on:click={toggleDropdown} class="triangle flex items-center"
	>{label}</button
>

{#if $isOpen}
	<ul
		id={dropdownId}
		class="absolute z-[1] flex flex-col gap-2 rounded-2xl bg-white p-3 font-normal text-black shadow-md"
	>
		{#each items as item}
			<li><a href={item.href}>{item.description}</a></li>
		{/each}
	</ul>
{/if}

<style lang="postcss">
	.triangle::after {
		content: '';
		border-right: 6px solid transparent;
		border-left: 6px solid transparent;
		border-top: 6px solid white;
		margin-left: 10px;
	}
</style>
