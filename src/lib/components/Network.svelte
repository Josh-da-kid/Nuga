<script>
	const networks = [
		{
			title: 'Official Title Sponsor(s)',
			images: [
				'/network1.svg',
				'/network2.svg',
				'/network3.svg',
				'/network4.svg',
				'/network5.svg',
				'/network6.svg',
				'/network7.svg'
			]
		},
		{
			title: 'Official Global Partners',
			images: [
				'/network8.svg',
				'/network4.svg',
				'/network5.svg',
				'/network6.svg',
				'/network3.svg',
				'/network6.svg',
				'/network7.svg'
			]
		},
		{
			title: 'Official Games Sponsors',
			images: [
				'/network9.svg',
				'/network4.svg',
				'/network5.svg',
				'/network6.svg',
				'/network3.svg',
				'/network7.svg'
			]
		},
		{
			title: 'Official Media Sponsors',
			images: [
				'/network8.svg',
				'/network4.svg',
				'/network5.svg',
				'/network6.svg',
				'/network3.svg',
				'/network7.svg'
			]
		},
		{
			title: 'Official Media Sponsors',
			images: [
				'/network8.svg',
				'/network4.svg',
				'/network5.svg',
				'/network6.svg',
				'/network3.svg',
				'/network7.svg'
			]
		},
		{
			title: 'Advert Community',
			images: [
				'/network9.svg',
				'/network4.svg',
				'/network5.svg',
				'/network6.svg',
				'/network3.svg',
				'/network7.svg'
			]
		}
	];
</script>

<section
	class="max-w-7xl mx-auto p-4 md:p-8 lg:p-12 text-center bg-gradient-to-b from-sky-100 via-pink-100/20 to-green-200/20 mt-24 rounded-3xl"
>
	<h1 class="font-bold text-2xl md:text-4xl">Paradise Games Development Network</h1>
	<p class="text-lg md:text-xl mt-4 mb-8 max-w-2xl text-center mx-auto">
		Trusted by leading brands across sport, media, logistics and culture, building the future of the
		Paradise Games..
	</p>

	{#each networks as network}
		{@const colClass =
			network.images.length === 6
				? 'grid-cols-2 md:grid-cols-3 lg:grid-cols-6'
				: 'grid-cols-2 md:grid-cols-4 lg:grid-cols-7'}
		<div class="mt-12">
			<h2 class="font-bold text-xl md:text-2xl">{network.title}</h2>
			<div class="bg-gray-100/10 rounded-2xl p-3">
				<div class="grid {colClass} gap-4 bg-white rounded-2xl p-3">
					{#each network.images as image}
						<div class="flex items-center justify-center">
							<img
								src={image}
								alt={network.title}
								class="w-full h-24 md:h-28 lg:h-32 object-contain p-2"
							/>
						</div>
					{/each}
				</div>
			</div>
		</div>
	{/each}
</section>
