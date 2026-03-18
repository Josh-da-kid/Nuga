<script lang="ts">
	let mobileMenuOpen = $state(false);
</script>

<nav class="nav fixed top-4 left-0 right-0 z-50 flex justify-center px-4 gap-8">
	<div
		class="nav-container bg-[#081E52]/80 flex items-center justify-between px-4 md:px-8 py-2 lg:py-0 rounded-full w-full max-w-6xl backdrop-blur-md shadow-lg"
	>
		<div class="flex-shrink-0">
			<img src="/paradise-games.svg" class="w-32 md:w-36 lg:w-44 h-auto" alt="Paradise Games" />
		</div>

		<ul
			class="hidden md:flex gap-6 lg:gap-8 text-lg justify-center items-center text-white mx-auto"
		>
			<li><a href="/" class="hover:text-blue-400 hover:underline transition-colors">Home</a></li>
			<li>
				<a href="/about" class="hover:text-blue-400 hover:underline transition-colors">About</a>
			</li>
			<li>
				<a href="/ezibiz" class="hover:text-blue-400 hover:underline transition-colors">Ezibiz</a>
			</li>
			<li>
				<a href="/media" class="hover:text-blue-400 hover:underline transition-colors">Media</a>
			</li>
			<li>
				<a href="/nuga" class="hover:text-blue-400 hover:underline transition-colors">NUGA</a>
			</li>
		</ul>

		<button
			class="md:hidden text-white p-2"
			onclick={() => (mobileMenuOpen = !mobileMenuOpen)}
			aria-label="Toggle menu"
		>
			<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
				{#if mobileMenuOpen}
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M6 18L18 6M6 6l12 12"
					/>
				{:else}
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M4 6h16M4 12h16M4 18h16"
					/>
				{/if}
			</svg>
		</button>
	</div>

	{#if mobileMenuOpen}
		<div
			class="md:hidden fixed top-24 left-4 right-4 bg-[#081E52]/95 backdrop-blur-md rounded-2xl p-6 shadow-2xl z-40"
		>
			<ul class="flex flex-col gap-4 text-lg text-center">
				<li>
					<a
						href="/"
						class="block py-2 hover:text-[#4ADE80]"
						onclick={() => (mobileMenuOpen = false)}>Home</a
					>
				</li>
				<li>
					<a
						href="/about"
						class="block py-2 hover:text-[#4ADE80]"
						onclick={() => (mobileMenuOpen = false)}>About</a
					>
				</li>
				<li>
					<a
						href="/ezibiz"
						class="block py-2 hover:text-[#4ADE80]"
						onclick={() => (mobileMenuOpen = false)}>Ezibiz</a
					>
				</li>
				<li>
					<a
						href="/media"
						class="block py-2 hover:text-[#4ADE80]"
						onclick={() => (mobileMenuOpen = false)}>Media</a
					>
				</li>
				<li>
					<a
						href="/nuga"
						class="block py-2 hover:text-[#4ADE80]"
						onclick={() => (mobileMenuOpen = false)}>NUGA</a
					>
				</li>
			</ul>
			<button class="w-full mt-4 bg-[#FFAD33] text-black px-6 py-3 rounded-full font-semibold">
				Get Involved
			</button>
		</div>
	{/if}

	<div
		class="items-center hidden justify-center md:flex flex-shrink-0 shadow-lg bg-gray-100/20 rounded-full px-6"
	>
		<button
			class="hidden md:block whitespace-nowrap bg-[#FFAD33] text-black px-6 lg:px-8 py-2 lg:py-3 2xl:py-3 rounded-full font-semibold text-base hover:scale-105 transition-transform shadow-md flex-shrink-0"
		>
			Get Involved
		</button>
	</div>
</nav>
