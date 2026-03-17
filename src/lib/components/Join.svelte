<script lang="ts">
	interface Button {
		label: string;
		bgColor: string;
		width?: string;
	}

	let buttons: Button[] = [
		{ label: 'Institution', bgColor: 'bg-green-600' },
		{ label: 'Athlete', bgColor: 'bg-pink-600' },
		{ label: 'Officials', bgColor: 'bg-sky-600' },
		{ label: 'Volunteer', bgColor: 'bg-yellow-500' },
		{ label: 'Fans', bgColor: 'bg-amber-700' }
	];
</script>

<section
	class="relative w-full h-full flex flex-col gap-2 justify-center items-center rounded-2xl overflow-hidden py-12 text-center p-6"
>
	<h1 class="flex items-center font-bold text-2xl sm:text-3xl lg:text-4xl">
		Be a Part of <br /> Paradise Games 2026
	</h1>
	<p class="text-lg md:text-xl lg:text-2xl">Register to Join Us Today!</p>

	<div
		class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3 gap-6 mt-12 justify-center items-center mx-auto"
	>
		{#each buttons.slice(0, 3) as button}
			<div
				class="bg-blue-100/40 backdrop-blur-sm items-center mx-auto flex flex-col w-fit px-2 py-2 rounded-full"
			>
				<button
					class="{button.bgColor} text-white px-6 sm:px-10 lg:px-16 py-3 sm:py-4 rounded-full font-medium text-sm sm:text-lg hover:scale-105 transition-transform shadow-2xl hover:shadow-xl w-[200px]"
				>
					{button.label}
				</button>
			</div>
		{/each}
		<div class="md:col-span-3 grid md:grid-cols-2 justify-center gap-6">
			{#each buttons.slice(3) as button}
				<div
					class="bg-blue-100/40 backdrop-blur-sm items-center mx-auto flex flex-col w-fit px-2 py-2 rounded-full"
				>
					<button
						class="{button.bgColor} text-white px-6 sm:px-10 lg:px-16 py-3 sm:py-4 rounded-full font-medium text-sm sm:text-lg hover:scale-105 transition-transform shadow-2xl hover:shadow-xl w-[200px]"
					>
						{button.label}
					</button>
				</div>
			{/each}
		</div>
	</div>
</section>
