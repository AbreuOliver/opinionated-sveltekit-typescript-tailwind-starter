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

{#if isBannerVisible}
	<!-- <div
		tabindex="-1"
		class="${styling} grid custom-grid-cols gap-x-clamp grid-rows-auto row-span-1 z-999 place-items-center col-span-3 col-start-1 w-full h-[fit-content] py-4 md:py-0 md:h-14 font-normal bg-gradient-to-r
		from-[#BFA2DB] via-[#C9F6FF] to-[#D7F9D7]
		 text-black"
	>
		<div
			class="grid grid-cols-[3rem_1fr_3rem] max-w-[95vw] md:max-w-[850px] gap-x-clamp col-span-3 col-start-1 row-span-1 row-start-1 w-full h-full place-content-center place-items-center"
		>
			<a
				href="#events"
				class="flex col-span-2 col-start-1 items-center text-sm text-text-left cursor-pointer title debug-border flex-wrap pl-6"
			>
				{bannerText} Learn more.
			</a>

			<div class="flex col-span-1 col-start-3 justify-center items-center w-12 h-full">
				<button
					on:click={closeBanner}
					type="button"
					class="inline-flex justify-center items-center w-8 h-8 text-sm rounded-full text-neutral-900/50 hover:bg-neutral-500/50 hover:text-neutral-100"
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
	</div> -->
	<!-- <div
		tabindex="-1"
		class="z-50 col-span-3 col-start-1 w-full h-auto md:h-14 text-black font-normal py-4 md:py-0"
		style="
		background: linear-gradient(90deg, #38B6FF, #E44235);
		background-size: 100% 100%;
		background-position: 0% 50%;
		animation: gradientShift 6s ease infinite;
	"
	>
		<div
			class="grid grid-cols-[3rem_1fr_3rem] max-w-[95vw] md:max-w-[850px] mx-auto w-full h-full place-content-center place-items-center gap-x-4"
		>
			<a
				href="#events"
				class="flex items-center col-span-2 col-start-1 text-sm text-left pl-6 hover:underline transition duration-150"
			>
				{bannerText} Learn more.
			</a>

			<div class="flex justify-center items-center w-12 h-full col-span-1 col-start-3">
				<button
					on:click={closeBanner}
					type="button"
					class="inline-flex justify-center items-center w-8 h-8 text-sm rounded-full text-black hover:bg-black/10 transition duration-150"
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
	</div> -->
	<div
		tabindex="-1"
		class="relative z-50 col-span-3 col-start-1 w-full h-auto md:h-14 text-black font-normal py-4 md:py-0 bg-neutral-800 banner-container"
	>
		<div
			class="grid grid-cols-[3rem_1fr_3rem] max-w-[95vw] md:max-w-[850px] mx-auto w-full h-full place-content-center place-items-center gap-x-4"
		>
			<a
				href="#events"
				class="flex items-center col-span-2 col-start-1 text-sm text-left pl-6 hover:underline transition duration-150"
			>
				{bannerText} Learn more.
			</a>

			<div class="flex justify-center items-center w-12 h-full col-span-1 col-start-3">
				<button
					on:click={closeBanner}
					type="button"
					class="inline-flex justify-center items-center w-8 h-8 text-sm rounded-full text-neutral-200 hover:bg-red-600 transition duration-150"
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
{/if}

<style>
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
</style>
