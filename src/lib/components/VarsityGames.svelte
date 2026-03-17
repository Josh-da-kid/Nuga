<script>
	const federations = [
		{
			title: 'The International University Sports Federation (FISU)',
			image: 'federation1.svg'
		},
		{
			title: 'The Federation of African University Sports (FASU)',
			image: 'federation2.svg'
		},
		{
			title: 'Nigeria University Games Association (NUGA)',
			image: 'federation4.svg'
		}
	];
</script>

<section class="max-w-7xl mx-auto p-4 md:p-8 lg:p-12 text-center mt-24 rounded-3xl">
	<h1 class="font-bold text-2xl md:text-4xl">The Varsity Games Network</h1>
	<p class="text-lg md:text-xl mt-4 mb-8 max-w-2xl text-center mx-auto">
		Connecting the Paradise Games to the global university sports movement.
	</p>

	<div>
		<img src="/varsity.svg" alt="" />
	</div>

	<section class="grid md:grid-cols-2 mx-auto gap-24 mt-16 justify-between items-start">
		<div>
			<div class="text-start">
				<h2 class="font-bold text-2xl md:text-4xl">Federations</h2>

				<p class="text-lg md:text-xl mt-4 mb-8 max-w-xl">
					The Paradise Games is operating within internationally recognised university sports
					frameworks.
				</p>
			</div>

			<div class="flex flex-col gap-8 mt-12">
				{#each federations as federation}
					<div
						class="border-2 border-sky-500 rounded-xl p-6 gap-8 max-w-xl flex flex-col sm:flex-row items-center shadow-md"
					>
						<img src={federation.image} alt={federation.title} class="w-32 h-auto mb-4" />

						<li class="font-semibold text-lg">{federation.title}</li>
					</div>
				{/each}
			</div>
		</div>

		<div class="h-auto">
			<img src="/col.svg" alt="" />
		</div>
	</section>
</section>
