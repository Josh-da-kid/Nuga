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
	class="bg-gradient-to-r text-white grid grid-cols-1 md:grid-cols-2 gap-8 mt-24 from-red-800 to-blue-950 p-4 rounded-3xl max-w-7xl justify-center items-center mx-auto"
>
	<div
		class="p-4 md:p-8 lg:p-12 text-center sm:text-left items-center sm:items-start justify-center sm:justify-start flex flex-col"
	>
		<h1 class="flex flex-col text-4xl sm:text-5xl md:text-6xl font-medium text-white">
			Subscribe to our Newsletter
		</h1>

		<div class="flex flex-col text-lg md:text-xl lg:text-2xl font-medium mt-8 gap-2">
			<p class="text-md md:text-lg lg:text-xl mt-2">Never Miss a Moment</p>
			<p class="text-md md:text-lg lg:text-xl mt-2">
				From major announcements to behind-the-scenes highlights, we’ll keep you informed.
			</p>
			<p class="text-md md:text-lg lg:text-xl mt-2">👉 Subscribe for Updates</p>
		</div>
	</div>

	<div>
		<label for="Email Address" class="flex flex-col text-lg md:text-xl lg:text-2xl gap-3">
			Email Address
			<input
				type="text"
				class=" rounded-full px-4 py-3 md:py-4 lg:py-5 text-black text-base w-[330px] lg:w-[500px]"
				placeholder="Enter your email"
			/>
		</label>

		<div
			class="bg-blue-100/30 mt-5 z-20 backdrop-blur-sm items-center justify-center sm:justify-start mx-auto sm:mx-0 flex flex-col w-fit px-2 py-2 rounded-full"
		>
			<button
				class="bg-yellow-500 text-black px-8 sm:px-10 md:px-14 py-3 sm:py-4 rounded-full font-bold text-sm sm:text-lg hover:scale-105 transition-transform shadow-lg hover:shadow-xl"
			>
				Donate
			</button>
		</div>
	</div>
</section>
