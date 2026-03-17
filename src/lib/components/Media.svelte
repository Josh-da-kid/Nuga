<script lang="ts">
	let currentPage = $state(1);
	const totalPages = 4;

	let mediaItems = [
		{
			tag: 'Politics',
			image: 'otu.svg',
			date: '12/Feb/2026',
			title: 'GOV OTU BACKS UNICAL TO HOST NUGA GAMES',
			description:
				'Governor otu gave this assurance during an inspection tour of facilities at the UJ Esuene Stadium'
		},
		{
			tag: 'Sports',
			image: 'media2.svg',
			date: '10/Feb/2026',
			title: 'NUGA GAMES TO HOLD IN CALABAR IN 2026',
			description:
				'The Nigeria University Games Association (NUGA) has announced that the 2026 edition of the games will be hosted in Calabar, Cross River State.'
		},
		{
			tag: 'Education',
			image: 'media3.svg',
			date: '08/Feb/2026',
			title: 'UNICAL TO HOST NUGA GAMES IN 2026',
			description:
				'The University of Calabar (UNICAL) has been selected as the host for the 2026 Nigeria University Games Association (NUGA) games, marking a significant milestone for the institution and the city of Calabar.'
		},
		{
			tag: 'Sports',
			image: 'media4.svg',
			date: '05/Feb/2026',
			title: 'NUGA GAMES TO HOLD IN CALABAR IN 2026',
			description:
				'The Nigeria University Games Association (NUGA) has announced that the 2026 edition of the games will be hosted in Calabar, Cross River State.'
		}
	];

	let videoPreviews = [
		{
			thumbnail: 'media2.svg',
			title: 'NUGA Games 2026 Highlights',
			duration: '3:45',
			date: '12/Feb/2026',
			description: 'Watch the best moments from previous NUGA Games and get excited for 2026'
		},
		{
			thumbnail: 'media3.svg',
			title: 'Governor Otu Visits UNICAL',
			duration: '2:30',
			date: '10/Feb/2026',
			description: 'Governor Otu inspects facilities ahead of the upcoming games in Calabar'
		},
		{
			thumbnail: 'media4.svg',
			title: 'Opening Ceremony Preview',
			duration: '5:12',
			date: '08/Feb/2026',
			description: 'A sneak peek at what to expect during the grand opening ceremony'
		},
		{
			thumbnail: 'otu.svg',
			title: 'Sports Facilities Tour',
			duration: '4:18',
			date: '05/Feb/2026',
			description: 'Take a tour of the world-class sports facilities at UNICAL'
		}
	];

	function goToPage(page) {
		if (page >= 1 && page <= totalPages) {
			currentPage = page;
		}
	}

	function nextPage() {
		if (currentPage < totalPages) {
			currentPage++;
		}
	}

	function prevPage() {
		if (currentPage > 1) {
			currentPage--;
		}
	}
</script>

<section class="py-12 sm:py-16 lg:py-24 relative">
	<div class="text-center mb-12 lg:mb-16 relative">
		<h1 class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900">
			Media Centre
		</h1>
		<p class="text-lg sm:text-xl md:text-2xl text-gray-600 mt-2">Read more about us</p>
		<img
			src="footballer-2.svg"
			class="w-32 sm:w-48 md:w-64 lg:w-auto h-auto absolute -right-4 sm:right-0 lg:right-8 top-1/2 -translate-y-1/2 opacity-20 lg:opacity-100 pointer-events-none"
			alt="Footballer"
		/>
	</div>

	<div
		class="bg-gradient-to-b to-gray-400 from-blue-950 rounded-t-3xl p-6 sm:p-8 lg:p-12 relative overflow-visible bg-cover bg-center bg-no-repeat"
		style="background-image: url('/mediabg.png');"
	>
		<img
			src="female-athlete.svg"
			class="absolute bottom-0 left-0 w-64 sm:w-80 lg:w-96 h-auto opacity-30 lg:opacity-50 pointer-events-none"
			alt=""
		/>
		<div class="relative z-10 grid grid-cols-1 lg:grid-cols-3 gap-8">
			<!-- Latest Information - Only visible on mobile/tablet, hidden on desktop -->
			<div class="lg:hidden flex flex-col justify-center">
				<div class="text-center">
					<p class="text-white text-lg sm:text-xl font-medium mb-6">Let's bring you up to speed!</p>
					<div class="relative inline-block">
						<h2 class="text-4xl sm:text-5xl font-bold text-white leading-tight">Latest</h2>
						<img
							class="w-28 sm:w-36 absolute -bottom-3 left-1/2 -translate-x-1/2 pointer-events-none"
							src="/brush.svg"
							alt=""
						/>
					</div>
					<h2 class="text-4xl sm:text-5xl font-bold text-white leading-tight mt-6">Information</h2>
				</div>
			</div>

			<!-- Media Items -->
			<div class="lg:col-span-2 media-font">
				<div class="grid grid-cols-1 sm:grid-cols-2 gap-y-36 gap-8 max-w-3xl pb-28">
					{#each mediaItems as item}
						<div
							class="bg-white/20 min-h-[320px] p-3 rounded-xl relative max-w-[430px] flex items-end"
						>
							<article
								class="bg-white rounded-xl shadow-lg hover:shadow-2xl transition-all duration-300 transform hover:-translate-y-1 group w-full -mb-28"
							>
								<div class="relative p-4">
									<img
										src={item.image}
										alt={item.title}
										class="w-full h-48 sm:h-56 border-2 border-gray-200 rounded-xl object-cover group-hover:scale-105 transition-transform duration-500"
									/>
									<span
										class="absolute top-8 left-6 bg-blue-600/80 text-white text-xs sm:text-sm font-semibold px-3 py-1 rounded-full"
									>
										{item.tag}
									</span>
								</div>
								<div class="p-4 sm:p-5">
									<p class="text-gray-500 text-sm">{item.date}</p>
									<h2
										class="text-base sm:text-lg font-bold text-gray-900 mt-2 line-clamp-2 group-hover:text-blue-600 transition-colors"
									>
										{item.title}
									</h2>
									<p class="text-gray-600 mt-2 text-sm line-clamp-3">{item.description}</p>
									<a
										href="#"
										class="inline-block mt-4 text-blue-600 font-semibold text-sm hover:text-blue-800 transition-colors"
									>
										READ MORE <span
											class="inline-block ml-1 transition-transform group-hover:translate-x-1"
											>→</span
										>
									</a>
								</div>
							</article>
						</div>
					{/each}
				</div>

				<!-- Pagination below media items -->
				<div
					class="flex items-center justify-center md:items-start md:justify-start gap-2 mt-16 pb-8"
				>
					<button
						onclick={prevPage}
						disabled={currentPage === 1}
						class="p-2 rounded-full bg-white/20 text-white hover:bg-white/30 disabled:opacity-50 disabled:cursor-not-allowed transition-colors"
					>
						<svg
							xmlns="http://www.w3.org/2000/svg"
							class="h-5 w-5"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							stroke-width="2"
						>
							<path stroke-linecap="round" stroke-linejoin="round" d="M15 19l-7-7 7-7" />
						</svg>
					</button>

					{#each Array(totalPages) as _, i}
						<button
							onclick={() => goToPage(i + 1)}
							class="w-10 h-10 rounded-full flex items-center justify-center font-semibold transition-colors {currentPage ===
							i + 1
								? 'bg-white text-blue-900'
								: 'bg-white/20 text-white hover:bg-white/30'}"
						>
							{i + 1}
						</button>
					{/each}

					<button
						onclick={nextPage}
						disabled={currentPage === totalPages}
						class="p-2 rounded-full bg-white/20 text-white hover:bg-white/30 disabled:opacity-50 disabled:cursor-not-allowed transition-colors"
					>
						<svg
							xmlns="http://www.w3.org/2000/svg"
							class="h-5 w-5"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							stroke-width="2"
						>
							<path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7" />
						</svg>
					</button>
				</div>
			</div>

			<!-- Latest Information - Only visible on desktop -->
			<div class="hidden lg:flex lg:col-span-1 flex-col">
				<div class="text-left">
					<p class="text-white text-lg sm:text-xl lg:text-xl font-medium mb-6">
						Let's bring you up to speed!
					</p>
					<div class="relative inline-block">
						<h2
							class="text-4xl sm:text-5xl md:text-6xl lg:text-[100px] 2xl:text-[130px] font-bold text-white leading-tight"
						>
							Latest
						</h2>
						<img
							class="w-28 sm:w-36 lg:w-44 absolute -bottom-3 left-1/2 -translate-x-1/2 lg:left-auto lg:right-0 lg:translate-x-2 pointer-events-none"
							src="/brush.svg"
							alt=""
						/>
					</div>
					<h2
						class="text-4xl sm:text-5xl md:text-6xl lg:text-[100px] 2xl:text-[130px] font-bold text-white leading-tight mt-6"
					>
						Inform <br />ation
					</h2>
				</div>

				<!-- Explore button -->
				<div
					class="items-start justify-start flex mt-5 w-fit bg-gray-200/20 backdrop-blur-md rounded-full px-4 py-2 shadow-lg"
				>
					<button
						class="flex items-center gap-2 bg-gray-200 text-black px-6 lg:px-8 py-2 lg:py-3 rounded-full font-semibold text-base lg:text-lg hover:scale-105 transition-transform shadow-md"
					>
						Explore All News
						<svg
							xmlns="http://www.w3.org/2000/svg"
							class="h-5 w-5"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							stroke-width="2"
						>
							<path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
						</svg>
					</button>
				</div>
			</div>
		</div>
	</div>

	<!-- Latest Videos Section -->
	<section
		class="bg-gradient-to-b from-gray-400 to-blue-950 rounded-b-3xl p-6 sm:p-8 lg:p-12 relative overflow-hidden"
	>
		<div class="items-start justify-start mx-auto flex flex-col px-4 md:px-8 lg:px-12">
			<h2 class="text-white font-bold text-2xl lg:text-4xl xl:text-5xl mb-8 flex flex-col">
				Latest <p class="inline-block">
					<span>Videos</span> <img src="/brush.svg" class="h-6 w-24 -mt-3" alt="" />
				</p>
			</h2>
		</div>

		<div class="grid grid-cols-1 lg:grid-cols-2 gap-8 lg:px-12 items-stretch">
			<!-- Left: YouTube Video Frame - styled like mediaItems -->
			<div class=" mx-auto w-full flex flex-col">
				<div class="bg-white/30 p-3 rounded-xl">
					<article
						class="bg-white rounded-xl overflow-hidden md:h-[600px] shadow-lg hover:shadow-2xl transition-all duration-300 transform hover:-translate-y-1 group flex-1"
					>
						<div class="relative overflow-hidden">
							<div class="aspect-video">
								<iframe
									class="w-full h-full"
									src="https://www.youtube.com/embed/dQw4w9WgXcQ"
									title="YouTube video player"
									frameborder="0"
									allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
									allowfullscreen
								></iframe>
							</div>
							<span
								class="absolute top-4 left-4 bg-red-600 text-white text-xs sm:text-sm font-semibold px-3 py-1 rounded-full"
							>
								Featured
							</span>
						</div>
						<div class="p-4 sm:p-5">
							<h2 class="text-base sm:text-lg font-bold text-gray-900 mt-2">
								NUGA Games 2026 - Official Trailer
							</h2>
							<p class="text-gray-600 mt-2 text-sm">
								Watch the official trailer for the upcoming NUGA Games
							</p>
						</div>
					</article>
				</div>
				<div class="flex items-center justify-between mt-4 lg:mt-8">
					<p class="text-white text-lg sm:text-xl">
						Be the first to know when we upload a new video
					</p>
					<svg
						class="text-white w-8 h-8 flex-shrink-0"
						xmlns="http://www.w3.org/2000/svg"
						width="24"
						height="24"
						viewBox="0 0 24 24"
						><path
							fill="none"
							stroke="currentColor"
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M5 12h14m-7-7l7 7l-7 7"
						/></svg
					>
				</div>
			</div>

			<!-- Right: YouTube Preview Videos - styled like mediaItems with flex-row text -->
			<div class="media-font mx-auto w-full max-w-xl flex flex-col">
				<div class="p-3 bg-white/30 rounded-xl">
					<div class="grid grid-cols-1 gap-4 md:h-[600px] bg-white p-3 rounded-xl flex-1">
						{#each videoPreviews as video}
							<div
								class="bg-white/30 p-3 rounded-xl cursor-pointer hover:bg-white/50 transition-colors group"
							>
								<article
									class="bg-white rounded-xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-300 transform hover:-translate-y-1"
								>
									<div class="flex flex-row">
										<!-- Video thumbnail -->
										<div class="relative overflow-hidden w-40 sm:w-48 flex-shrink-0">
											<img
												src={video.thumbnail}
												alt={video.title}
												class="w-full h-24 sm:h-28 object-cover group-hover:scale-105 transition-transform duration-500"
											/>
											<span
												class="absolute bottom-1 right-1 bg-black/80 text-white text-xs px-1 py-0.5 rounded"
											>
												{video.duration}
											</span>
											<div
												class="absolute inset-0 flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity bg-black/40"
											>
												<div class="bg-red-600 w-10 h-8 rounded flex items-center justify-center">
													<svg
														class="w-5 h-4 text-white ml-0.5"
														fill="currentColor"
														viewBox="0 0 24 24"
													>
														<path d="M8 5v14l11-7z" />
													</svg>
												</div>
											</div>
										</div>
										<!-- Text content side by side -->
										<div class="p-3 sm:p-4 flex flex-col justify-center">
											<p class="text-gray-500 text-xs">{video.date || '12/Feb/2026'}</p>
											<h4 class="text-sm font-bold text-gray-900 line-clamp-2">{video.title}</h4>
											<p class="text-gray-600 mt-1 text-xs line-clamp-2">
												{video.description ||
													'Watch the latest highlights and updates from NUGA Games 2026'}
											</p>
										</div>
									</div>
								</article>
							</div>
						{/each}
					</div>
				</div>
				<div class="flex flex-col sm:flex-row gap-4 mt-4 items-center justify-between">
					<!-- youtube button -->
					<div
						class="items-center justify-center w-fit bg-gray-200/20 backdrop-blur-md rounded-full px-4 py-2 shadow-lg"
					>
						<button
							class="flex items-center gap-2 bg-yellow-600 text-black px-6 lg:px-8 py-3 lg:py-5 rounded-full font-semibold text-base lg:text-lg hover:scale-105 transition-transform shadow-md"
						>
							Check Our Youtube
						</button>
					</div>

					<!-- get involved button -->
					<div
						class="items-center justify-center w-fit bg-gray-200/20 backdrop-blur-md rounded-full px-4 py-2 shadow-lg"
					>
						<button
							class="flex items-center gap-2 bg-gradient-to-b from-gray-200 to-green-200 text-black px-6 lg:px-12 py-3 lg:py-5 rounded-full font-semibold text-base lg:text-lg hover:scale-105 transition-transform shadow-md"
						>
							Get Involved
						</button>
					</div>
				</div>
			</div>
		</div>
	</section>
</section>
