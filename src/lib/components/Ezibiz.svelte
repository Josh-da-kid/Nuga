<script lang="ts">
	interface Product {
		id: number;
		image: string;
		title: string;
		price: string;
		rating: number;
		isNew?: boolean;
	}

	let products: Product[] = [
		{
			id: 1,
			image: 'https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=400&h=400&fit=crop',
			title: 'Nike Air Max 2026',
			price: '₦45,000',
			rating: 4.5,
			isNew: true
		},
		{
			id: 2,
			image: 'https://images.unsplash.com/photo-1587563871167-1ee9c731aefb?w=400&h=400&fit=crop',
			title: 'Sports Jersey Set',
			price: '₦12,500',
			rating: 4.0
		},
		{
			id: 3,
			image: 'https://images.unsplash.com/photo-1606107557195-0e29a4b5b4aa?w=400&h=400&fit=crop',
			title: 'Running Sneakers',
			price: '₦32,000',
			rating: 4.8,
			isNew: true
		},
		{
			id: 4,
			image: 'https://images.unsplash.com/photo-1523275335684-37898b6baf30?w=400&h=400&fit=crop',
			title: 'Fitness Watch Pro',
			price: '₦28,000',
			rating: 4.2
		},
		{
			id: 5,
			image: 'https://images.unsplash.com/photo-1560769629-975ec94e6a86?w=400&h=400&fit=crop',
			title: 'Training Hoodie',
			price: '₦18,500',
			rating: 4.6,
			isNew: true
		},
		{
			id: 6,
			image: 'https://images.unsplash.com/photo-1576566588028-4147f3842f27?w=400&h=400&fit=crop',
			title: 'Sports Cap',
			price: '₦5,500',
			rating: 3.9
		}
	];

	function getStarRating(rating: number): string[] {
		const stars: string[] = [];
		const fullStars = Math.floor(rating);
		const hasHalfStar = rating % 1 >= 0.5;

		for (let i = 0; i < fullStars; i++) {
			stars.push('full');
		}
		if (hasHalfStar) {
			stars.push('half');
		}
		while (stars.length < 5) {
			stars.push('empty');
		}
		return stars;
	}
</script>

<section
	class="bg-gradient-to-r text-white grid grid-cols-1 md:grid-cols-2 gap-8 from-amber-900 to-blue-950 p-4 rounded-3xl max-w-7xl justify-center items-center mx-auto"
>
	<div
		class="p-4 md:p-8 lg:p-12 text-center sm:text-left items-center sm:items-start justify-center sm:justify-start flex flex-col"
	>
		<h1 class="flex flex-col text-4xl sm:text-5xl md:text-6xl lg:text-[150px] font-bold text-white">
			EziBiz <span
				><img
					src="/brush.svg"
					class="-mt-3 md:-mt-5 w-24 h-8 md:w-32 md:h-12 lg:w-auto lg:h-auto"
					alt=""
				/></span
			>
		</h1>
		<p class="text-md md:text-lg lg:text-xl mt-2">
			The Paradise Games Online <br /> Store (eMarket).
		</p>

		<div class="flex flex-col text-lg md:text-xl lg:text-2xl font-medium mt-8 gap-2">
			<p>Don't Just Watch</p>
			<p>The Game. Wear It.</p>

			<div
				class="bg-blue-100/90 mt-5 z-20 backdrop-blur-sm items-center flex flex-col w-fit px-2 py-2 rounded-full"
			>
				<button
					class="bg-yellow-600 text-black px-6 sm:px-10 md:px-14 py-3 sm:py-4 rounded-full font-bold text-sm sm:text-lg hover:scale-105 transition-transform shadow-lg hover:shadow-xl"
				>
					Shop Now
				</button>
			</div>
		</div>
	</div>

	<!-- Shopping Items -->
	<div class="flex flex-col bg-gray-100/10 p-3 rounded-2xl">
		<div class="grid grid-cols-2 md:grid-cols-3 gap-3 sm:gap-4 bg-white p-3 rounded-2xl">
			{#each products as product}
				<div
					class="bg-gray-200 backdrop-blur-sm rounded-lg overflow-hidden hover:bg-white/15 transition-colors cursor-pointer group"
				>
					<div class="relative">
						<img
							src={product.image}
							alt={product.title}
							class="w-full h-28 sm:h-32 md:h-36 object-cover"
						/>

						<!-- Favorite Button -->
						<button
							class="absolute top-2 right-2 w-7 h-7 sm:w-8 sm:h-8 bg-white/90 rounded-full flex items-center justify-center shadow-md hover:scale-110 transition-transform"
						>
							<svg
								xmlns="http://www.w3.org/2000/svg"
								class="h-4 w-4 sm:h-5 sm:w-5 text-gray-600"
								fill="none"
								viewBox="0 0 24 24"
								stroke="currentColor"
							>
								<path
									stroke-linecap="round"
									stroke-linejoin="round"
									stroke-width="2"
									d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"
								/>
							</svg>
						</button>

						<!-- New Tag -->
						{#if product.isNew}
							<span
								class="absolute top-2 left-2 bg-amber-800 text-white text-[10px] sm:text-xs px-2 py-0.5 rounded-lg font-medium"
							>
								New
							</span>
						{/if}
					</div>

					<div class="p-2 sm:p-3">
						<h3 class="text-white text-xs sm:text-sm font-medium truncate">{product.title}</h3>
						<div class="flex items-center justify-between mt-1 sm:mt-2">
							<span class="text-yellow-500 font-bold text-sm sm:text-base">{product.price}</span>
							<div class="flex items-center gap-0.5">
								{#each getStarRating(product.rating) as star}
									{#if star === 'full'}
										<svg
											class="w-3 h-3 sm:w-4 sm:h-4 text-orange-500"
											fill="currentColor"
											viewBox="0 0 20 20"
										>
											<path
												d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
											/>
										</svg>
									{:else if star === 'half'}
										<svg
											class="w-3 h-3 sm:w-4 sm:h-4 text-orange-500"
											fill="currentColor"
											viewBox="0 0 20 20"
										>
											<defs>
												<linearGradient id="halfStar">
													<stop offset="50%" stop-color="currentColor" />
													<stop offset="50%" stop-color="#e5e7eb" />
												</linearGradient>
											</defs>
											<path
												fill="url(#halfStar)"
												d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
											/>
										</svg>
									{:else}
										<svg
											class="w-3 h-3 sm:w-4 sm:h-4 text-gray-300"
											fill="currentColor"
											viewBox="0 0 20 20"
										>
											<path
												d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
											/>
										</svg>
									{/if}
								{/each}
							</div>
						</div>
					</div>
				</div>
			{/each}
		</div>

		<!-- Bottom Section -->
		<div class="flex flex-col sm:flex-row justify-between items-center mt-4 sm:mt-6 gap-3">
			<p class="text-white/80 text-sm sm:text-base">Shop now and stand out in Paradise style</p>
			<button
				class="flex items-center gap-2 bg-yellow-600 text-black px-4 sm:px-6 py-2 sm:py-3 rounded-full font-medium text-sm sm:text-base hover:scale-105 transition-transform"
			>
				Explore our store
				<svg
					xmlns="http://www.w3.org/2000/svg"
					class="h-4 w-4 sm:h-5 sm:w-5"
					fill="none"
					viewBox="0 0 24 24"
					stroke="currentColor"
				>
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M17 8l4 4m0 0l-4 4m4-4H3"
					/>
				</svg>
			</button>
		</div>
	</div>
</section>
