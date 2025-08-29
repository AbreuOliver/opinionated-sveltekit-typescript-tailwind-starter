<script lang="ts">
	import Megaphone from '$lib/icons/Megaphone.svelte';
	import '../../global.css';

	export let bannerText: string;
	export let styling: string = '';

	let isBannerVisible = true;

	function closeBanner() {
		isBannerVisible = false;
	}
</script>

<!-- {#if isBannerVisible}
	<div
		tabindex="-1"
		class="relative z-50 col-span-3 col-start-1 w-full h-auto md:h-14 text-black bg-[#FFDD00] font-normal py-4 md:py-0 banner-container text-left"
	>
		<div
			class="grid grid-cols-[3rem_1fr_3rem] max-w-[95vw] md:max-w-[850px] mx-auto w-full h-full place-content-center place-items-center gap-x-4"
		>
			<a
				href="#events"
				class="flex items-center col-span-2 col-start-1 text-sm pl-6 hover:underline transition duration-150"
			>
				{bannerText} Awana begins <span class="font-bold px-1">Wednesday, September 10, 2025</span> •
				All kids welcome! • Learn more under Children’s Ministry
			</a>

			<div class="flex justify-center items-center w-12 h-full col-span-1 col-start-3">
				<button
					on:click={closeBanner}
					type="button"
					class="inline-flex justify-center items-center w-8 h-8 text-sm rounded-full text-neutral-700 hover:bg-red-600 transition duration-150 hover:text-white"
				>
					<svg
						class="w-3 h-3"
						aria-hidden="true"
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 14 14"
					>
						<path
							stroke="currentColor"
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="m1 1 6 6m0 0 6 6M7 7l6-6M7 7l-6 6"
						/>
					</svg>
					<span class="sr-only">Close banner</span>
				</button>
			</div>
		</div>
	</div>
{/if} -->

{#if isBannerVisible}
	<div tabindex="-1" class="relative z-50 w-full bg-[#FFDD00] text-black font-normal">
		<div
			class="flex items-center mx-auto w-full max-w-[95vw] md:max-w-[850px] px-4 md:h-14 py-3 md:py-0"
		>
			<div class="flex items-center gap-3">
				<a
					href="/about#childrens-ministry"
					class="flex-1 text-center text-sm leading-6 hover:underline"
				>
					Awana begins <span class="font-bold">Wednesday, September 10</span> • All kids welcome! • Learn
					more here
				</a>
				<!-- <button
					on:click={closeBanner}
					type="button"
					class="shrink-0 inline-flex justify-center items-center w-8 h-8 text-sm rounded-full text-neutral-700 hover:bg-red-600 hover:text-white transition"
					aria-label="Close banner"
				>
					<svg
						class="w-3 h-3"
						aria-hidden="true"
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 14 14"
					>
						<path
							stroke="currentColor"
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="m1 1 6 6m0 0 6 6M7 7l6-6M7 7l-6 6"
						/>
					</svg>
				</button> -->
			</div>
		</div>
	</div>
{/if}

<!-- <style>
	.banner-container::before {
		content: '';
		position: absolute;
		z-index: -1;
		bottom: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: linear-gradient(
			45deg,
			#e44235,
			/* Red */ #ff7043,
			/* Red-orange */ #ffde59,
			/* Yellow */ #d1ed64,
			/* Yellow-green */ #38b6ff,
			/* Light Blue */ #1d87ff,
			/* Mid Blue */ #223dfe,
			/* Deep Blue */ #5c2dfe,
			/* Indigo */ #c13cfe
		);
		background-size: 600% 100%;
		animation: rainbowBorder 10s linear infinite;
	}

	@keyframes rainbowBorder {
		0% {
			background-position: 0% 33%;
		}
		50% {
			background-position: 33% 66%;
		}
		100% {
			background-position: 66% 99%;
		}
	}
</style> -->
