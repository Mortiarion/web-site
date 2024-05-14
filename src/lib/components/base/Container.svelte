<script lang="ts">
	import { cn } from '$lib/utils/cn';

	export let classes = '';
</script>

<div class={cn('max-w-full', classes)}>
	<slot />
</div>
