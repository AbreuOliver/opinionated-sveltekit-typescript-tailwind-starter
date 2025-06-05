<script lang="ts">
	import Address from '$lib/icons/Address.svelte';
	import Phone from '$lib/icons/Phone.svelte';
	import Email from '$lib/icons/Email.svelte';
	import Facebook from '$lib/icons/Facebook.svelte';

	import '../../global.css';
</script>

<section
	id="hero"
	class="grid custom-grid-cols gap-x-clamp grid-rows-[1fr_auto] col-span-3 col-start-1 row-span-1 row-start-1 w-full h-[95vh] min-h-[800px] bg-[url('https://ik.imagekit.io/bip1v395ybp/Emmanuel%20Baptist%20Church/mini-ebc_hero_7Kjkq7MHZP.webp?updatedAt=1729398571353')] bg-cover bg-center"
>
	<div
		id="hero-info"
		class="col-span-1 col-start-2 row-span-1 row-start-1 w-full h-full min-h-full debug-border"
	>
		<h1
			class="md:font-semibold text-neutral-100 font-extrabold text-left leading-tight mt-16 mb-8 md:mb-4 text-[2.75rem] md:text-7xl whitespace-none md:pt-[30vh] pt-[12rem]"
		>
			Helping Others<br />
			<a
				type="button"
				href="/find-jesus"
				class="hidden md:inline relative text-white hover:text-transparent hover:bg-clip-text hover:bg-gradient-to-tr hover:from-blue-600 hover:to-cyan-500
	  after:content-[''] after:absolute after:left-0 after:bottom-0 after:w-full after:h-[8px] after:bg-gradient-to-tr after:from-blue-600 after:to-cyan-500 after:rounded-full after:scale-x-0 hover:after:scale-x-100 after:origin-left after:transition-transform after:duration-300 after:translate-y-1"
			>
				Find
			</a>
			<a
				type="button"
				href="/find-jesus"
				class="text-transparent bg-clip-text bg-gradient-to-tr from-blue-600 to-cyan-500 md:hidden"
			>
				Find
			</a>
			<span class="font-sans font-[700]">&</span>
			<br class="md:hidden" />
			<a
				type="button"
				href="/follow-jesus"
				class="hidden md:inline relative text-white hover:text-transparent hover:bg-clip-text
	hover:bg-gradient-to-tr
	hover:from-theme-400 hover:to-blue-600
	after:content-['']
	after:absolute after:left-0 after:bottom-0 after:w-full after:h-[8px] after:bg-gradient-to-tr after:from-theme-400 after:to-blue-600 after:rounded-full after:scale-x-0 hover:after:scale-x-100 after:origin-left after:transition-transform after:duration-300 after:translate-y-1
	"
			>
				Follow
			</a>
			<a
				type="button"
				href="/follow-jesus"
				class="font-bold text-transparent bg-clip-text bg-gradient-to-tr to-blue-500 md:hidden from-theme-300"
			>
				Follow
			</a>
			<span class="">Jesus</span>
		</h1>
		<div
			class="flex flex-col items-start mt-12 space-y-4 md:flex-row md:space-y-0 md:space-x-4 md:items-center font-outfitMedium"
		>
			<a href="/plan-your-visit"
				><button
					type="button"
					class="text-white rounded-full text-xl py-2.5 px-5 text-center me-2 w-[95%] md:max-w-[275px] h-16 bg-theme-900 font-heading-medium focus:outline-none focus:ring-4 focus:ring-blue-300 transform transition-transform duration-300 ease-in-out hover:scale-105 hover:bg-gradient-to-tr hover:from-blue-600 hover:to-cyan-500 hover:text-white"
				>
					Plan Your Visit
				</button>
			</a>
			<button
				type="button"
				class="text-white py-2.5 px-5 text-center me-2 text-xl focus:outline-none backdrop-blur-sm rounded-full border border-neutral-200 hover:bg-neutral-100 hover:text-theme-900 focus:z-3 focus:ring-4 focus:ring-neutral-100 w-[95%] md:max-w-[275px] h-16 transform transition-transform duration-300 ease-in-out hover:scale-105"
			>
				<a href="#discover">Learn More</a>
			</button>
		</div>
	</div>

	<div
		id="contact-info"
		class="hidden col-span-3 col-start-1 row-span-1 row-start-2 justify-center items-center w-full h-16 text-white bg-blue-700 md:flex"
	>
		<div class="grid items-center w-full h-full custom-grid-cols">
			<div
				class="flex flex-grow col-span-1 col-start-2 justify-between items-center h-full debug-border"
			>
				<Address />
				<Phone />
				<Email />
				<Facebook />
			</div>
		</div>
	</div>
</section>
