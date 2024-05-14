<script lang="ts">
	import { cn } from '$lib/utils/cn';

	export let type: 'submit' | 'button' = 'button';
	export let disabled = false;
	export let classes = '';
</script>

<button {type} on:click {disabled} class={cn('', classes)}>
	<slot />
</button>
