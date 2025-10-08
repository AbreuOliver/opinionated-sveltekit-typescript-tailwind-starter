<script lang="ts">
	import '../../global.css';

	export let isBannerVisible = true;
	export let href: string = '/#events';
	export let text: string =
		'40th Anniversary Sunday · Oct 26 · 10:30 AM · Celebrating 40 years of ministry';

	function closeBanner() {
		isBannerVisible = false;
	}
</script>

{#if isBannerVisible}
	<div
		tabindex="-1"
		class="relative z-50 w-full bg-gradient-to-r from-yellow-300 via-yellow-200 to-amber-400 shadow-sm ring-1 ring-amber-800/10 text-zinc-900 font-normal"
	>
		<div
			aria-hidden="true"
			class="pointer-events-none absolute inset-0 -z-10
               before:content-[''] before:absolute before:inset-y-0 before:w-[45%]
               before:-skew-x-12 before:bg-gradient-to-r before:from-white/0 before:via-white/35 before:to-white/0
               before:translate-x-[-120%] before:animate-[shine_2500ms_linear_infinite]"
		></div>
		<div
			class="flex items-center mx-auto w-full max-w-[95vw] md:max-w-[850px] px-4 md:h-14 py-3 md:py-0"
		>
			<div class="flex items-center gap-3 w-full">
				<a
					href="/about#childrens-ministry"
					class="flex-1 text-center text-sm leading-6 hover:underline mr-auto"
				>
					<span class="font-semibold">40th Anniversary Sunday</span> · Oct 26 · 10:30 AM
					<span class="hidden sm:inline"> · Celebrating 40 years of ministry</span>
				</a>
				<button
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
				</button>
			</div>
		</div>
	</div>
{/if}

<style>
	@keyframes shine {
		0% {
			transform: translateX(-120%);
		}
		70% {
			transform: translateX(120%);
		}
		100% {
			transform: translateX(120%);
		}
	}
</style>
