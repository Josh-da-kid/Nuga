<script>
	import { onMount } from 'svelte';

	let fontsLoaded = false;

	onMount(() => {
		if (document.fonts) {
			document.fonts.ready.then(() => {
				fontsLoaded = true;
			});
		}
	});
</script>

<section class="mt-24 rounded-3xl">
	<section class="flex flex-col md:flex-row bg-black text-white rounded-3xl overflow-hidden">
		<!-- Left Image -->
		<div class="w-full md:w-1/3 hidden md:flex items-center justify-center">
			<img src="/footer1.svg" alt="" class="w-full h-48 md:h-full object-cover" />
		</div>

		<!-- Center Content -->
		<div
			class="flex-1 flex flex-col items-center justify-center py-12 px-4 md:px-8 lg:px-12 text-center"
		>
			<div
				class="road-rage-bold text-4xl sm:text-5xl md:text-6xl lg:text-7xl xl:text-[120px] leading-tight"
			>
				Let the <br />
				games <br />
				begin!
			</div>

			<p class="text-lg sm:text-xl md:text-2xl lg:text-3xl mt-6 md:mt-10 font-bold">
				WELCOME TO PARADISE GAMES 2026
			</p>

			<div class="mt-8 md:mt-12">
				<button
					class="bg-yellow-600 text-black px-8 sm:px-10 md:px-14 py-3 sm:py-4 rounded-full font-bold text-sm sm:text-lg hover:scale-105 transition-transform shadow-lg hover:shadow-xl w-full sm:w-auto"
				>
					Get Involved
				</button>
			</div>
		</div>

		<!-- Right Image -->
		<div class="w-full md:w-1/3 hidden md:flex items-center justify-center">
			<img src="/footer2.svg" alt="" class="w-full h-48 md:h-full object-cover" />
		</div>
	</section>
</section>

<style>
	.road-rage-bold {
		font-family: 'Road Rage', sans-serif;
		font-weight: 800;
		font-style: normal;
	}
</style>
