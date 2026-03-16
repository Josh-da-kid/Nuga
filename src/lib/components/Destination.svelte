<script lang="ts">
	import Carousel3D from './Carousel3D.svelte';
	const destinationImages = [
		{
			id: 1,
			src: 'https://images.unsplash.com/photo-1506744038136-46273834b3fb?w=600&h=400&fit=crop',
			alt: 'Image 1'
		},
		{
			id: 2,
			src: 'https://images.unsplash.com/photo-1494526585095-c41746248156?w=600&h=400&fit=crop',
			alt: 'Image 2'
		},
		{
			id: 3,
			src: 'https://images.unsplash.com/photo-1500534623283-312aade485b7?w=600&h=400&fit=crop',
			alt: 'Image 3'
		},
		{
			id: 4,
			src: 'https://images.unsplash.com/photo-1491895200222-0fc4a4c35e18?w=600&h=400&fit=crop',
			alt: 'Image 4'
		},
		{
			id: 5,
			src: 'https://images.unsplash.com/photo-1504384308090-c894fdcc538d?w=600&h=400&fit=crop',
			alt: 'Image 5'
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
