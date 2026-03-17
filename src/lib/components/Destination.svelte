<script lang="ts">
	import Carousel3D from './Carousel3D.svelte';
	const destinationImages = [
		{
			id: 1,
			src: '/destination1.svg',
			alt: 'CrossRiver Masquerade'
		},
		{
			id: 2,
			src: '/destination2.svg',
			alt: 'CrossRiver Carnival'
		},
		{
			id: 3,
			src: '/destination3.svg',
			alt: 'Prince Bassey Otu, CrossRiver State Governor'
		},
		{
			id: 4,
			src: '/destination4.svg',
			alt: 'Obudu Cattle Ranch Gate'
		},
		{
			id: 5,
			src: '/destination5.svg',
			alt: 'Football Pitch'
		}
	];
</script>

<section
	class="relative w-full h-full flex flex-col justify-center items-center rounded-2xl overflow-hidden py-24 text-center p-6"
>
	<img
		src="/crossriver.svg"
		alt="Cross River Logo"
		class="w-24 sm:w-32 lg:w-38 object-contain mb-4"
	/>
	<h1 class="font-bold text-xl md:text-2xl lg:text-3xl">Destination Cross River</h1>
	<p class="text-lg md:text-xl lg:text-2xl mt-2">The People's Paradise.</p>
	<p class="text-lg md:text-xl lg:text-2xl mt-1">Welcome Home</p>

	<div class="w-full mt-8">
		<Carousel3D images={destinationImages} />
	</div>
</section>
