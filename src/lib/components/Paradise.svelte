<script lang="ts">
	export let stadiumImage: string = '/stadium-bg.jpg';

	const countdown = {
		days: 94,
		hours: 9,
		mins: 29
	};
</script>

<section class="relative w-full h-full flex justify-center items-center overflow-visible">
	<!-- Stadium Background Image -->
	<div class="absolute inset-0 z-0 overflow-hidden">
		<img src="/paradise.png" alt="Stadium Background" class="w-full h-full object-cover" />
		<div class="absolute inset-0 bg-gradient-to-b from-black/70 via-black/50 to-black/80"></div>
	</div>

	<!-- Main Content - Positioned at bottom left -->
	<div class="absolute bottom-8 sm:bottom-12 left-4 sm:left-8 lg:left-16 z-20">
		<!-- Paradise Games Text -->
		<div class="mb-4 sm:mb-6">
			<h4 class="text-white/80 text-xs sm:text-sm uppercase tracking-widest mb-1">
				AFRICA'S WARMEST WELCOME
			</h4>
			<h1
				class="text-white default-font text-3xl sm:text-4xl md:text-5xl lg:text-[110px] 2xl:text-[130px] font-extrabold leading-tight"
			>
				The <br /><span
					>ParAdisE <img
						src="/brush.svg"
						class="w-24 sm:w-32 lg:w-48 -mt-1 sm:-mt-2"
						alt="Brush"
					/></span
				> gAmEs
			</h1>
		</div>
	</div>
	<!-- CTA Button  -->
	<div
		class="bg-blue-100/90 absolute -bottom-8 z-20 backdrop-blur-sm items-center mx-auto flex flex-col w-fit px-2 py-2 rounded-full"
	>
		<button
			class="bg-blue-900 text-white px-6 sm:px-10 py-3 sm:py-4 rounded-full font-bold text-sm sm:text-lg hover:scale-105 transition-transform shadow-lg hover:shadow-xl"
		>
			Get Involved
		</button>
	</div>
</section>

<style>
	section {
		min-height: 400px;
	}
	@media (min-width: 768px) {
		section {
			min-height: 500px;
		}
	}
	@media (min-width: 1024px) {
		section {
			min-height: 600px;
		}
	}
</style>
