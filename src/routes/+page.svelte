<script lang="ts">
	import Nav from '$lib/components/Nav.svelte';
	import Hero from '$lib/components/Hero.svelte';
	import Metrics from '$lib/components/Metrics.svelte';
	import Media from '$lib/components/Media.svelte';
	import Paradise from '$lib/components/Paradise.svelte';
	import Destination from '$lib/components/Destination.svelte';
	import Unical from '$lib/components/Unical.svelte';
	import GreatestShow from '$lib/components/GreatestShow.svelte';
	import Join from '$lib/components/Join.svelte';
	import Ezibiz from '$lib/components/Ezibiz.svelte';
	import Support from '$lib/components/Support.svelte';
	import Network from '$lib/components/Network.svelte';
	import VarsityGames from '$lib/components/VarsityGames.svelte';
</script>

<main>
	<Nav />
	<Hero />
	<Metrics />
	<Media />
	<Paradise />
	<Destination />
	<Unical />
	<GreatestShow />
	<Join />
	<Ezibiz />
	<Support />
	<Network />
	<VarsityGames />
</main>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
		overflow-x: hidden;
	}
</style>
