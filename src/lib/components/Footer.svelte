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
	<section class="flex flex-col md:flex-row bg-black text-white rounded-t-3xl overflow-hidden">
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

	<hr />
	<section class="bg-black text-white">
		<div
			class="max-w-7xl mx-auto grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-8 lg:gap-12 pt-12 lg:pt-16 px-6 pb-12"
		>
			<div class="col-span-2 md:col-span-3 lg:col-span-1">
				<h2 class="text-xl lg:text-2xl font-bold">
					Paradise <span class="text-blue-600">Games</span> <br /> UNICAL 2026
				</h2>
				<p class="text-sm mt-3 text-gray-400">
					The 28th Nigeria University Games - A confluence of Sports, Carnival, & Entertainment
				</p>

				<ul class="flex gap-4 mt-4">
					<li>
						<a
							href="#"
							class="w-9 h-9 rounded-full bg-gray-800 flex items-center justify-center hover:bg-blue-600 transition-colors"
							aria-label="Facebook"
						>
							<svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
								<path
									d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"
								/>
							</svg>
						</a>
					</li>
					<li>
						<a
							href="#"
							class="w-9 h-9 rounded-full bg-gray-800 flex items-center justify-center hover:bg-blue-600 transition-colors"
							aria-label="X (Twitter)"
						>
							<svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
								<path
									d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"
								/>
							</svg>
						</a>
					</li>
					<li>
						<a
							href="#"
							class="w-9 h-9 rounded-full bg-gray-800 flex items-center justify-center hover:bg-blue-600 transition-colors"
							aria-label="Instagram"
						>
							<svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
								<path
									d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"
								/>
							</svg>
						</a>
					</li>
					<li>
						<a
							href="#"
							class="w-9 h-9 rounded-full bg-gray-800 flex items-center justify-center hover:bg-blue-600 transition-colors"
							aria-label="LinkedIn"
						>
							<svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
								<path
									d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
								/>
							</svg>
						</a>
					</li>
				</ul>
			</div>

			<div>
				<h2 class="font-bold text-base lg:text-lg mb-4">Quick Links</h2>
				<ul class="text-sm text-gray-400 space-y-2">
					<li><a href="#" class="hover:text-blue-500 transition-colors">Media</a></li>
					<li><a href="#" class="hover:text-blue-500 transition-colors">Paradise Games</a></li>
					<li><a href="#" class="hover:text-blue-500 transition-colors">Our Athletes</a></li>
					<li><a href="#" class="hover:text-blue-500 transition-colors">Nuga</a></li>
					<li><a href="#" class="hover:text-blue-500 transition-colors">Legacy</a></li>
				</ul>
			</div>

			<div>
				<h2 class="font-bold text-base lg:text-lg mb-4">Contact Us</h2>
				<ul class="text-sm text-gray-400 space-y-2">
					<li>University of Calabar</li>
					<li>+2342345 673448</li>
					<li>
						<a href="mailto:info@paradisegames.ng" class="hover:text-blue-500 transition-colors"
							>info@paradisegames.ng</a
						>
					</li>
				</ul>
			</div>

			<div>
				<h2 class="font-bold text-base lg:text-lg mb-4">Customer Care</h2>
				<ul class="text-sm text-gray-400 space-y-2">
					<li><a href="#" class="hover:text-blue-500 transition-colors">Help Center</a></li>
					<li><a href="#" class="hover:text-blue-500 transition-colors">Terms & Conditions</a></li>
					<li><a href="#" class="hover:text-blue-500 transition-colors">Privacy Policy</a></li>
					<li><a href="#" class="hover:text-blue-500 transition-colors">Returns & Refund</a></li>
					<li><a href="#" class="hover:text-blue-500 transition-colors">Survey & Feedback</a></li>
				</ul>
			</div>

			<div>
				<h2 class="font-bold text-base lg:text-lg mb-4">Pages</h2>
				<ul class="text-sm text-gray-400 space-y-2">
					<li><a href="#" class="hover:text-blue-500 transition-colors">About Us</a></li>
					<li><a href="#" class="hover:text-blue-500 transition-colors">Shop</a></li>
					<li><a href="#" class="hover:text-blue-500 transition-colors">Contact Us</a></li>
					<li><a href="#" class="hover:text-blue-500 transition-colors">Services</a></li>
					<li><a href="#" class="hover:text-blue-500 transition-colors">Blog</a></li>
				</ul>
			</div>
		</div>
	</section>

	<!-- SVGs -->
	<div class="bg-black">
		<div
			class="max-w-7xl mx-auto flex flex-col sm:flex-row items-center justify-between gap-6 px-6 py-6"
		>
			<div class="flex items-center gap-3 sm:gap-4">
				<img src="/nuga.svg" class="w-12 sm:w-16 md:w-20" alt="NUGA" />
				<img src="/unical.svg" class="w-12 sm:w-16 md:w-20" alt="UNICAL" />
			</div>

			<div class="flex items-center -space-x-2">
				<img src="/basketball1.svg" class="w-10 h-10 sm:w-14 sm:h-14 md:w-16 md:h-16" alt="" />
				<img src="/football.svg" class="w-10 h-10 sm:w-14 sm:h-14 md:w-16 md:h-16" alt="" />
			</div>
		</div>
		<hr class="border-gray-800" />

		<p class="text-white text-center text-sm py-4 pb-8">
			© 2026 Paradise Games - UNICAL. All rights reserved.
		</p>
	</div>
</section>

<style>
	.road-rage-bold {
		font-family: 'Road Rage', sans-serif;
		font-weight: 800;
		font-style: normal;
	}
</style>
