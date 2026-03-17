<script lang="ts">
	interface SupportCard {
		id: number;
		image: string;
		title1: string;
		title2: string;
		description: string;
		button: string;
	}

	let supportCards: SupportCard[] = [
		{
			id: 1,
			image: 'https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=400&h=400&fit=crop',
			title1: 'Volunteer',
			title2: 'We Need You on the Team',
			description: 'Make a Real Difference with your time and energy. Sign up today!',
			button: 'Volunteer'
		},
		{
			id: 2,
			image: 'https://images.unsplash.com/photo-1587563871167-1ee9c731aefb?w=400&h=400&fit=crop',
			title1: 'Donate',
			title2: 'Support What Matters',
			description: 'Your Contribution helps athletes shine and communities unites',
			button: 'Donate'
		}
	];
</script>

<section
	class="bg-gradient-to-r text-white mt-24 grid grid-cols-1 md:grid-cols-2 gap-8 from-amber-900 to-blue-950 p-4 rounded-3xl justify-center items-center mx-auto max-w-7xl"
>
	<!-- Support Cards (Left) -->
	<div class="grid grid-cols-1 md:grid-cols-2 gap-4 order-2 md:order-1">
		{#each supportCards as card}
			<div class="bg-white p-3 rounded-2xl mx-auto w-full">
				<div class="relative w-full">
					<img
						class="w-full h-48 md:h-auto object-cover rounded-xl"
						src={card.image}
						alt={card.title1}
					/>
					<div
						class="absolute bottom-0 left-0 right-0 bg-gradient-to-t from-black/70 to-transparent p-3 rounded-b-xl"
					>
						<h2 class="text-white text-center font-bold text-xl md:text-2xl lg:text-4xl">
							{card.title1}
						</h2>
					</div>
				</div>
				<div class="flex flex-col justify-center mt-4">
					<h3 class="font-bold text-lg md:text-xl text-gray-900 text-center">
						{card.title2}
					</h3>
					<p class="text-gray-600 mt-2 text-sm md:text-lg lg:text-xl text-center">
						{card.description}
					</p>
					<div class="items-center text-center flex justify-center">
						<button
							class="bg-yellow-600 text-black px-6 py-3 rounded-full font-bold text-sm md:text-base lg:text-lg mt-4 hover:scale-105 transition-transform shadow-lg hover:shadow-xl w-fit md:w-[220px]"
						>
							{card.button}
						</button>
					</div>
				</div>
			</div>
		{/each}
	</div>

	<!-- Join the Movement (Right) -->
	<div
		class="p-4 md:p-8 lg:p-12 order-1 md:order-2 flex flex-col justify-center text-center md:text-left"
	>
		<div class="flex flex-col items-center md:items-start">
			<h1
				class="text-3xl sm:text-4xl md:text-5xl lg:text-[120px] font-bold text-white leading-tight"
			>
				JOIN
			</h1>
			<img src="/brush.svg" class="-mt-2 md:-mt-4 w-20 sm:w-28 md:w-32" alt="" />
		</div>
		<h1 class="text-3xl sm:text-4xl md:text-5xl lg:text-[120px] font-bold text-white leading-tight">
			THE MOVE<br class="hidden md:block" />MENT
		</h1>
		<p class="text-sm md:text-lg lg:text-xl mt-4">Support The Paradise Games</p>
	</div>
</section>
