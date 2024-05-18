<!-- <script lang="ts">
	import { onMount } from 'svelte';

	export let isOpen: boolean = false;
	export let onClose: () => void = () => {};

	function handleClickOutside(event: MouseEvent) {
		const popup = document.getElementById('popup');
		if (popup && !popup.contains(event.target as Node)) {
			onClose();
		}
	}

	onMount(() => {
		document.addEventListener('click', handleClickOutside);
		return () => {
			document.removeEventListener('click', handleClickOutside);
		};
	});
</script>

{#if isOpen}
	<div class="popup-backdrop">
		<div id="popup" class="popup">
			<button class="close-btn" on:click={onClose}>X</button>
			<slot></slot>
		</div>
	</div>
{/if}

<style>
	.popup-backdrop {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: rgba(0, 0, 0, 0.5);
		display: flex;
		align-items: center;
		justify-content: center;
		z-index: 1000;
	}
	.popup {
		background: white;
		padding: 1rem;
		border-radius: 8px;
		box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
		max-width: 500px;
		width: 100%;
		position: relative;
	}
	.close-btn {
		position: absolute;
		top: 1rem;
		right: 1rem;
		cursor: pointer;
	}
</style> -->

<script lang="ts">
	export let showModal: Boolean; // boolean

	let dialog: HTMLDialogElement; // HTMLDialogElement

	$: if (dialog && showModal) dialog.showModal();
</script>

<!-- svelte-ignore a11y-click-events-have-key-events a11y-no-noninteractive-element-interactions -->
<dialog
	bind:this={dialog}
	on:close={() => (showModal = false)}
	on:click|self={() => dialog.close()}
>
	<!-- svelte-ignore a11y-no-static-element-interactions -->
	<div on:click|stopPropagation>
		<slot name="header" />
		<hr class=" mb-2" />
		<slot />
		<hr class=" mb-2" />
		<!-- svelte-ignore a11y-autofocus -->
		<button class=" rounded-lg bg-slate-200 p-1" autofocus on:click={() => dialog.close()}
			>close modal</button
		>
	</div>
</dialog>

<style>
	dialog {
		max-width: 32em;
		border-radius: 0.2em;
		border: none;
		padding: 0;
	}
	dialog::backdrop {
		background: rgba(0, 0, 0, 0.3);
	}
	dialog > div {
		padding: 1em;
	}
	dialog[open] {
		animation: zoom 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
	}
	@keyframes zoom {
		from {
			transform: scale(0.95);
		}
		to {
			transform: scale(1);
		}
	}
	dialog[open]::backdrop {
		animation: fade 0.2s ease-out;
	}
	@keyframes fade {
		from {
			opacity: 0;
		}
		to {
			opacity: 1;
		}
	}
	button {
		display: block;
	}
</style>
