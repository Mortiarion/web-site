<script lang="ts">
	import "@fontsource/montserrat";
	import "@fontsource/montserrat/500.css";
	import "@fontsource/montserrat/600.css";
	import "@fontsource/montserrat/700.css";
	import '$lib/styles/app.css';
	import Header from '$lib/components/layout/header/Header.svelte';
	import Footer from '$lib/components/layout/footer/Footer.svelte';
</script>

<svelte:head>
	<title>web-site</title>
</svelte:head>

<div class="flex min-h-screen flex-col">
	<Header />
	<main class="flex-auto">
		<slot />
	</main>
	<Footer />
</div>
