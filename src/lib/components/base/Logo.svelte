<script lang="ts">
	import { cn } from '$lib/utils/cn';

	import Image from '$lib/components/base/Image.svelte';
	export let href = '/';
	export let classes = '';
	let logoLinkTech = '/logo-link-tech.png';
</script>

<a {href} class={cn('', classes)}>
	<Image src={logoLinkTech} alt={'logo'}></Image>
</a>
