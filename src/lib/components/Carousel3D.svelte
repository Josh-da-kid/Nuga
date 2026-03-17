<script lang="ts">
	import { onMount } from 'svelte';

	interface CarouselImage {
		id: number;
		src: string;
		alt?: string;
	}

	interface Props {
		images?: CarouselImage[];
		background?: string;
		gap?: string;
		cardWidth?: string;
		cardHeight?: string;
		smCardWidth?: string;
		smCardHeight?: string;
		lgCardWidth?: string;
		lgCardHeight?: string;
		mdCardWidth?: string;
		mdCardHeight?: string;
	}

	let {
		images = [
			{
				id: 1,
				src: 'https://images.unsplash.com/photo-1574629810360-7efbbe195018?w=600&h=400&fit=crop'
			},
			{
				id: 2,
				src: 'https://images.unsplash.com/photo-1579952363873-27f3bade9f55?w=600&h=400&fit=crop'
			},
			{
				id: 3,
				src: 'https://images.unsplash.com/photo-1517649763962-0c623066013b?w=600&h=400&fit=crop'
			},
			{
				id: 4,
				src: 'https://images.unsplash.com/photo-1461899477712-7a2fb87f1bfb?w=600&h=400&fit=crop'
			},
			{
				id: 5,
				src: 'https://images.unsplash.com/photo-1599058917212-d750089bc07e?w=600&h=400&fit=crop'
			}
		],
		background = 'bg-white',
		gap = 'gap-4 sm:gap-6 lg:gap-8',
		cardWidth = 'w-[200px]',
		cardHeight = 'h-[280px]',
		smCardWidth = 'sm:w-[240px]',
		smCardHeight = 'sm:h-[320px]',
		mdCardWidth = 'md:w-[260px]',
		mdCardHeight = 'md:h-[340px]',
		lgCardWidth = 'lg:w-[280px]',
		lgCardHeight = 'lg:h-[360px]'
	}: Props = $props();

	const idleScales = [0.85, 0.92, 1, 0.92, 0.85];
	const idleTranslates = [-30, -15, 0, 15, 30];

	let hoveredIndex = $state<number | null>(null);
	let cursorPositions = $state<number[][]>(images.map(() => [0.5, 0.5]));

	let currentIndex = $state(0);
	let isSmallScreen = $state(false);
	let touchStartX = $state(0);
	let touchEndX = $state(0);
	let containerRef: HTMLDivElement;

	function checkScreenSize() {
		if (typeof window !== 'undefined') {
			isSmallScreen = window.innerWidth < 640;
		}
	}

	onMount(() => {
		checkScreenSize();
		window.addEventListener('resize', checkScreenSize);
		return () => window.removeEventListener('resize', checkScreenSize);
	});

	function handleMouseEnter(index: number) {
		hoveredIndex = index;
	}

	function handleMouseLeave() {
		hoveredIndex = null;
		cursorPositions = images.map(() => [0.5, 0.5]);
	}

	function handleMouseMove(index: number, event: MouseEvent) {
		const rect = (event.currentTarget as HTMLElement).getBoundingClientRect();
		const x = (event.clientX - rect.left) / rect.width;
		const y = (event.clientY - rect.top) / rect.height;
		cursorPositions[index] = [x, y];
	}

	function getCardStyle(index: number): string {
		const isHovered = hoveredIndex === index;
		const isNearby = hoveredIndex !== null && Math.abs(hoveredIndex - index) === 1;
		const isFarNearby = hoveredIndex !== null && Math.abs(hoveredIndex - index) === 2;

		let scale = idleScales[index];
		let translateX = idleTranslates[index];
		let translateZ = 0;
		let rotateX = 0;
		let rotateY = 0;
		let zIndex = 10;

		if (isHovered) {
			scale = 1.15;
			translateZ = 60;
			zIndex = 50;
			rotateX = (0.5 - cursorPositions[index][1]) * 20;
			rotateY = (cursorPositions[index][0] - 0.5) * 20;
		} else if (hoveredIndex !== null) {
			if (isNearby) {
				scale = Math.max(0.7, idleScales[index] - 0.08);
				translateX = idleTranslates[index] * 1.3;
			} else if (isFarNearby) {
				scale = Math.max(0.65, idleScales[index] - 0.12);
				translateX = idleTranslates[index] * 1.5;
			}
		}

		const centerIndex = 2;
		const distanceFromCenter = Math.abs(index - centerIndex);
		const baseZ = -distanceFromCenter * 20;

		return `
			transform: 
				perspective(1200px) 
				translateX(${translateX}px) 
				translateZ(${baseZ + translateZ}px) 
				scale(${scale}) 
				rotateX(${rotateX}deg) 
				rotateY(${rotateY}deg);
			z-index: ${zIndex};
		`;
	}

	function nextSlide() {
		currentIndex = (currentIndex + 1) % images.length;
	}

	function prevSlide() {
		currentIndex = (currentIndex - 1 + images.length) % images.length;
	}

	function goToSlide(index: number) {
		currentIndex = index;
	}

	function handleTouchStart(e: TouchEvent) {
		touchStartX = e.touches[0].clientX;
	}

	function handleTouchMove(e: TouchEvent) {
		touchEndX = e.touches[0].clientX;
	}

	function handleTouchEnd() {
		const diff = touchStartX - touchEndX;
		if (Math.abs(diff) > 50) {
			if (diff > 0) {
				nextSlide();
			} else {
				prevSlide();
			}
		}
		touchStartX = 0;
		touchEndX = 0;
	}
</script>

{#if isSmallScreen}
	<section class="w-full flex items-center justify-center overflow-hidden {background} py-6">
		<div class="w-full max-w-sm mx-auto px-4">
			<div
				class="relative overflow-hidden rounded-2xl"
				bind:this={containerRef}
				ontouchstart={handleTouchStart}
				ontouchmove={handleTouchMove}
				ontouchend={handleTouchEnd}
				role="region"
				aria-label="Image carousel"
			>
				<div
					class="flex transition-transform duration-500 ease-out"
					style="transform: translateX(-{currentIndex * 100}%)"
				>
					{#each images as image}
						<div class="w-full flex-shrink-0 aspect-[3/4]">
							<img
								src={image.src}
								alt={image.alt || ''}
								class="w-full h-full object-cover"
								draggable="false"
							/>
						</div>
					{/each}
				</div>

				<button class="nav-btn nav-prev" onclick={prevSlide} aria-label="Previous slide">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 24 24"
						stroke-width="2"
						stroke="currentColor"
						class="w-5 h-5"
					>
						<path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5 8.25 12l7.5-7.5" />
					</svg>
				</button>
				<button class="nav-btn nav-next" onclick={nextSlide} aria-label="Next slide">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 24 24"
						stroke-width="2"
						stroke="currentColor"
						class="w-5 h-5"
					>
						<path stroke-linecap="round" stroke-linejoin="round" d="m8.25 4.5 7.5 7.5-7.5 7.5" />
					</svg>
				</button>
			</div>

			<div class="flex justify-center gap-2 mt-4">
				{#each images as _, i}
					<button
						class="dot-indicator {i === currentIndex ? 'active' : ''}"
						onclick={() => goToSlide(i)}
						aria-label="Go to slide {i + 1}"
					></button>
				{/each}
			</div>

			<p class="text-center text-xs text-gray-400 mt-3">Swipe or use arrows to navigate</p>
		</div>
	</section>
{:else}
	<section class="w-full flex items-center justify-center overflow-hidden {background}">
		<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 sm:py-12">
			<div class="relative flex items-center justify-center {gap} py-8 perspective-container">
				{#each images as image, index}
					<div
						class="carousel-card {cardWidth} {cardHeight} {smCardWidth} {smCardHeight} {mdCardWidth} {mdCardHeight} {lgCardWidth} {lgCardHeight}"
						style={getCardStyle(index)}
						onmouseenter={() => handleMouseEnter(index)}
						onmouseleave={handleMouseLeave}
						onmousemove={(e) => handleMouseMove(index, e)}
						role="group"
						aria-label="Gallery image"
					>
						<div class="card-inner">
							<div class="card-image-container">
								<img src={image.src} alt={image.alt || ''} class="card-image" draggable="false" />
							</div>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</section>
{/if}

<style>
	.perspective-container {
		perspective: 1200px;
		transform-style: preserve-3d;
	}

	.carousel-card {
		position: relative;
		transform-style: preserve-3d;
		transition: all 0.5s cubic-bezier(0.25, 0.46, 0.45, 0.94);
		cursor: pointer;
	}

	.card-inner {
		position: relative;
		width: 100%;
		height: 100%;
		background: linear-gradient(145deg, rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0.05));
		border-radius: 1.5rem;
		overflow: hidden;
		backdrop-filter: blur(10px);
		border: 1px solid rgba(0, 0, 0, 0.08);
		box-shadow:
			0 25px 50px -12px rgba(0, 0, 0, 0.15),
			0 0 0 1px rgba(255, 255, 255, 0.05) inset;
		transition: all 0.5s cubic-bezier(0.25, 0.46, 0.45, 0.94);
	}

	.carousel-card:hover .card-inner {
		box-shadow:
			0 35px 60px -15px rgba(0, 0, 0, 0.25),
			0 8px 20px -8px rgba(59, 130, 246, 0.2),
			0 0 0 1px rgba(0, 0, 0, 0.1) inset;
	}

	.card-image-container {
		position: relative;
		width: 100%;
		height: 100%;
		overflow: hidden;
	}

	.card-image {
		width: 100%;
		height: 100%;
		object-fit: cover;
		transition: all 0.5s cubic-bezier(0.25, 0.46, 0.45, 0.94);
	}

	.carousel-card:hover .card-image {
		transform: scale(1.05);
	}

	.nav-btn {
		position: absolute;
		top: 50%;
		transform: translateY(-50%);
		width: 40px;
		height: 40px;
		border-radius: 50%;
		background: rgba(255, 255, 255, 0.9);
		backdrop-filter: blur(8px);
		border: 1px solid rgba(0, 0, 0, 0.1);
		display: flex;
		align-items: center;
		justify-content: center;
		cursor: pointer;
		transition: all 0.3s ease;
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
		z-index: 10;
	}

	.nav-btn:hover {
		background: rgba(255, 255, 255, 1);
		transform: translateY(-50%) scale(1.1);
		box-shadow: 0 6px 16px rgba(0, 0, 0, 0.2);
	}

	.nav-prev {
		left: 12px;
	}

	.nav-next {
		right: 12px;
	}

	.dot-indicator {
		width: 8px;
		height: 8px;
		border-radius: 50%;
		background: rgba(0, 0, 0, 0.2);
		border: none;
		cursor: pointer;
		transition: all 0.3s ease;
		padding: 0;
	}

	.dot-indicator:hover {
		background: rgba(0, 0, 0, 0.4);
	}

	.dot-indicator.active {
		background: #3b82f6;
		width: 24px;
		border-radius: 4px;
	}
</style>
