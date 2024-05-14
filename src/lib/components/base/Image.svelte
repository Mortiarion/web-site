<script lang="ts">
	import { cn } from '$lib/utils/cn';

	export let eager = false;
	export let alt = '';
	export let src = '';
	export let width = '';
	export let height = '';
	export let cover = false;
	export let classes = '';
</script>

<img
	{src}
	{alt}
	{width}
	{height}
	loading={eager ? 'eager' : 'lazy'}
	decoding="async"
	class={cn('block h-auto max-w-full object-center', classes, {
		'h-full w-full object-cover ': cover
	})}
/>
