<script lang="ts">
	export let stadiumImage: string = '/stadium-bg.jpg';

	const countdown = {
		days: 94,
		hours: 9,
		mins: 29
	};
</script>

<section
	class="relative w-full h-full min-h-[85vh] md:min-h-[90vh] flex justify-center items-center rounded-b-2xl md:rounded-b-[4rem] lg:rounded-b-[9rem]"
>
	<!-- Stadium Background Image -->
	<div
		class="absolute inset-0 z-0 overflow-hidden rounded-b-2xl md:rounded-b-[4rem] lg:rounded-b-[9rem]"
	>
		<img src="/herobg.png" alt="Stadium Background" class="w-full h-full object-cover" />
		<div class="absolute inset-0 bg-gradient-to-b from-black/70 via-black/50 to-black/80"></div>
	</div>
	<!-- Left Athlete (Footballer) - Larger, closer to center, 3D pouring effect -->
	<div
		class="absolute left-0 lg:-left-16 2xl:left-0 lg:bottom-[-18%] bottom-[-15%] z-20 hidden lg:block"
	>
		<img
			src="/footballer.svg"
			alt="Footballer"
			class="h-[550px] md:h-[750px] 2xl:h-[900px] w-auto object-contain"
			style="filter: drop-shadow(-20px 0 30px rgba(0,0,0,0.6)); transform: perspective(1000px) rotateY(10deg) translateX(20px);"
		/>
	</div>

	<!-- Main Content -->
	<div class="z-10 flex flex-col items-center pt-28 md:pt-48 pb-16 px-2 md:px-4">
		<!-- Countdown Timer -->
		<div class="bg-blue-400/40 px-3 sm:px-6 rounded-3xl py-3 sm:py-4 mb-6 sm:mb-8">
			<div class="flex gap-2 sm:gap-4 md:gap-6">
				<div
					class="bg-white rounded-lg md:rounded-xl px-2 sm:px-4 md:px-6 py-2 md:py-3 shadow-lg text-center min-w-[50px] sm:min-w-[70px] md:min-w-[90px]"
				>
					<div class="text-2xl sm:text-3xl md:text-5xl font-bold text-[#1a2a4a]">
						{countdown.days}
					</div>
					<div class="text-[10px] sm:text-xs md:text-base text-gray-600 uppercase font-medium">
						Days
					</div>
				</div>

				<div class="text-white text-3xl sm:text-4xl md:text-6xl items-center flex mx-auto">:</div>
				<div
					class="bg-white rounded-lg md:rounded-xl px-2 sm:px-4 md:px-6 py-2 md:py-3 shadow-lg text-center min-w-[50px] sm:min-w-[70px] md:min-w-[90px]"
				>
					<div class="text-2xl sm:text-3xl md:text-5xl font-bold text-[#1a2a4a]">
						{String(countdown.hours).padStart(2, '0')}
					</div>
					<div class="text-[10px] sm:text-xs md:text-base text-gray-600 uppercase font-medium">
						Hours
					</div>
				</div>

				<div class="text-white text-3xl sm:text-4xl md:text-6xl items-center flex mx-auto">:</div>
				<div
					class="bg-white rounded-lg md:rounded-xl px-2 sm:px-4 md:px-6 py-2 md:py-3 shadow-lg text-center min-w-[50px] sm:min-w-[70px] md:min-w-[90px]"
				>
					<div class="text-2xl sm:text-3xl md:text-5xl font-bold text-[#1a2a4a]">
						{String(countdown.mins).padStart(2, '0')}
					</div>
					<div class="text-[10px] sm:text-xs md:text-base text-gray-600 uppercase font-medium">
						Mins
					</div>
				</div>
			</div>
		</div>

		<!-- Main Title -->
		<h1
			class="text-4xl sm:text-5xl md:text-7xl lg:text-[160px] font-black text-center leading-none mb-2"
		>
			<span
				class="bg-gradient-to-b from-white via-gray-100 to-green-400 bg-clip-text text-transparent drop-shadow-[0_0_30px_rgba(74,222,128,0.5)]"
			>
				Paradise
			</span>
			<br />
			<span
				class="bg-gradient-to-r from-white via-gray-100 to-green-400 bg-clip-text text-transparent drop-shadow-[0_0_30px_rgba(74,222,128,0.5)]"
			>
				Games
			</span>
		</h1>

		<h2
			class="text-white flex gap-2 sm:gap-4 text-lg sm:text-2xl md:text-4xl lg:text-6xl font-extrabold uppercase tracking-widest mb-4 sm:mb-6 md:mb-8"
		>
			<span>
				UNICAL <span
					><img
						src="/brush.svg"
						class="-mt-1 sm:-mt-2 h-3 md:h-5 lg:h-8 w-16 sm:w-auto text-center items-center justify-center flex mx-auto"
						alt="Brush"
					/></span
				></span
			> <span> 2026 </span>
		</h2>

		<!-- Description -->
		<p
			class="text-gray-300 text-sm sm:text-base md:text-xl lg:text-2xl text-center max-w-[90%] sm:max-w-lg md:max-w-2xl leading-relaxed mb-6 sm:mb-8 md:mb-10"
		>
			The 28th Edition of the Nigerian University Games is coming to Calabar. Over 100 universities.
			Thousands of athletes. One unforgettable celebration of sport, culture, and media excellence.
		</p>

		<!-- CTA Button -->
		<div class="bg-gray-100/40 px-4 sm:px-6 rounded-full py-3 sm:py-4 mb-6 sm:mb-8">
			<button
				class="bg-green-100 text-black px-6 sm:px-10 md:px-14 py-3 sm:py-4 md:py-6 rounded-full font-bold text-sm sm:text-lg md:text-xl hover:scale-105 transition-transform shadow-[0_0_30px_rgba(74,222,128,0.4)] hover:shadow-[0_0_50px_rgba(74,222,128,0.6)]"
			>
				Get Involved
			</button>
		</div>
	</div>

	<!-- Right Athlete - Larger, closer to center, 3D pouring effect -->
	<div class="absolute right-0 bottom-0 z-20 hidden lg:block">
		<img
			src="/athlete.svg"
			alt="Athlete"
			class="h-[520px] md:h-[720px] lg:h-[750px] 2xl:h-[900px] w-auto object-contain"
			style="filter: drop-shadow(20px 0 30px rgba(0,0,0,0.6)); transform: perspective(1000px) rotateY(-10deg) translateX(-20px);"
		/>
	</div>

	<!-- Partner Logos -->
	<div class="absolute bottom-4 md:bottom-8 right-6 md:right-12 z-40 text-right flex gap-4">
		<p
			class="text-white text-xs md:text-xl font-bold uppercase tracking-wider mb-2 items-center flex"
		>
			Powered by:
		</p>
		<div class="flex gap-3 md:gap-4 justify-end items-center mx-auto">
			<img src="/nuga.svg" alt="NUGA" />
			<img src="/unical.svg" alt="UNICAL Logo" />
		</div>
	</div>
</section>
