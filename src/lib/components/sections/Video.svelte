<script lang="ts">
	import Image from '$lib/components/base/Image.svelte';
	import Section from '$lib/components/base/Section.svelte';
	import Container from '$lib/components/base/Container.svelte';

	let PandaWalker = { src: '/panda-walk.gif', alt: 'panda-walk' };
	let PandaFunny = { src: '/panda-funny.gif', alt: 'panda-funny' };
	let PandaAngry = { src: '/panda-angry.gif', alt: 'panda-angry' };
</script>

<Section>
	<Container>
		<Image classes="w-full" src={PandaWalker.src} alt={PandaWalker.alt} />
		<Image classes="w-full" src={PandaFunny.src} alt={PandaFunny.alt} />
		<Image classes="w-full" src={PandaAngry.src} alt={PandaAngry.alt} />
		<!-- {#each PandaWalker as panda}
            <Image src={panda.src} alt={panda.alt} />
        {/each} -->
	</Container>
</Section>
