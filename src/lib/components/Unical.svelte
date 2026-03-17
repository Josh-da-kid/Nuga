<script lang="ts">
	import Carousel3D from './Carousel3D.svelte';
	const unicalImages = [
		{
			id: 1,
			src: '/unical01.svg',
			alt: 'University Faculties'
		},
		{
			id: 2,
			src: '/unical2.svg',
			alt: 'Unical Student award ceremony'
		},
		{
			id: 3,
			src: '/unical3.svg',
			alt: 'Unical HOD'
		},
		{
			id: 4,
			src: '/unical4.svg',
			alt: 'NUGA Associates'
		},
		{
			id: 5,
			src: '/unical5.svg',
			alt: 'University Of Calabar'
		}
	];
</script>

<section
	class="relative w-full h-full flex flex-col justify-center items-center rounded-2xl overflow-hidden py-24 text-center p-6"
>
	<img src="/unical1.svg" alt="Unical Logo" class="w-24 sm:w-32 lg:w-24 object-contain mb-4" />
	<h1 class="font-bold text-xl md:text-2xl lg:text-3xl">This is Unical</h1>
	<p class="text-lg md:text-xl lg:text-2xl mt-2">Knowledge for Service</p>

	<div class="w-full mt-8">
		<Carousel3D images={unicalImages} />
	</div>
</section>
