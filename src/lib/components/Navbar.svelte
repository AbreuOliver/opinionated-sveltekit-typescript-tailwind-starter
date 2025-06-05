<script lang="ts">
	import HamburgerMenu from '$lib/icons/HamburgerMenu.svelte';
	import Logo from '$lib/icons/Logo.svelte';
	import Wordmark from '$lib/icons/Wordmark.svelte';

	export let styling: string = '';

	let menuText: string[] = ['Discover', 'events', 'media', 'give'];
</script>

<div
	class="${styling} grid custom-grid-cols gap-x-clamp grid-rows-auto row-span-1 md:place-items-center col-span-3 col-start-1 w-full h-20 md:h-18 font-semibold text-neutral-900 md:border-b md:last:border-neutral-400"
>
	<div
		class="grid col-span-1 col-start-2 row-span-1 row-start-1 justify-start items-center w-full max-w-[95vw] md:max-w-[850px] gap-x-clamp md:place-items-start"
	>
		<!-- SUBGRID HERE -->
		<div class="grid grid-cols-[1fr_4fr] w-full debug-border">
			<!-- COLUMN 1 -->
			<a href="#hero" class="flex items-center h-full">
				<Logo size={12} />
				<Wordmark topLineTextColor="white" bottomLineTextColor="#FAFAFA" />
			</a>
			<!-- COLUMN 2 -->
			<nav class="flex justify-end items-center text-white">
				<div class="flex justify-center p-1 w-16 h-16 justify-content lg:w-0 lg:hidden">
					<HamburgerMenu size={10} />
				</div>
				<ul class="hidden items-center pr-4 space-x-12 lg:flex">
					{#each menuText as text}
						<li>
							<a
								href={`#${text.toLowerCase()}`}
								class="relative hover:text-blue-900 capitalize text-outfit after:content-[''] after:block after:absolute after:left-0 after:bottom-0 after:h-[2px] after:w-full after:bg-blue-900 after:rounded-md after:scale-x-0 hover:after:scale-x-100 after:translate-y-2 after:transition-transform after:duration-300"
							>
								{text}
							</a>
						</li>
					{/each}
				</ul>
			</nav>
		</div>
	</div>
</div>
