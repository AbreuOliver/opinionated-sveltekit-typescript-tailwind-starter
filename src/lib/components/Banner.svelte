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
	<div
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

			<!-- Close Button Column -->
			<div class="flex col-span-1 col-start-3 justify-center items-center w-12 h-full">
				<button
					on:click={closeBanner}
					type="button"
					class="inline-flex justify-center items-center w-8 h-8 text-sm rounded-full text-mono-900/50 hover:bg-mono-500/50 hover:text-mono-100"
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
