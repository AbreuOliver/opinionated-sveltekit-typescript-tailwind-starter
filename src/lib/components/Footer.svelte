<script lang="ts">
	import Facebook from '$lib/icons/Facebook.svelte';
	import Logo from '$lib/icons/Logo.svelte';
	import Wordmark from '$lib/icons/Wordmark.svelte';

	export let styling: string = '';

	const currentYear: number = new Date().getFullYear();
</script>

<footer
	class={`${styling} grid grid-cols-[1fr_minmax(clamp(1rem,6vw,3rem),80ch)_1fr] gap-x-[clamp(1rem,6vw,3rem)] py-12`}
>
	<div class="col-span-1 col-start-2 mx-auto w-full">
		<div
			class="grid grid-cols-1 gap-y-8 grid-rows-[75px_auto_auto_auto] md:grid-cols-2 md:grid-rows-[75px_auto_auto]"
		>
			<div class="col-start-1 row-start-1 w-full h-full">
				<a href="https://flowbite.com/" class="flex items-center">
					<Logo size={16} />
					<span class="pl-4"></span>
					<Wordmark topLineTextColor="white" bottomLineTextColor="#FAFAFA" />
				</a>
			</div>
			<div class="col-start-1 row-start-2 w-full">
				<h2 class="mb-6 text-lg font-semibold text-neutral-400 uppercase">Service Times</h2>
				<ul class="pl-4 space-y-4 font-medium text-neutral-200 md:pl-0">
					<li class="">
						<a href="https://flowbite.com/" class="text-sky-300"
							>Sunday Bible Study <br /><span class="text-white">10:00 AM</span></a
						>
					</li>
					<li>
						<a href="https://tailwindcss.com/" class="text-sky-300"
							>Sunday Worship: <br /><span class="text-white">11:00 AM & 6:30 PM</span></a
						>
					</li>
					<li>
						<a href="https://tailwindcss.com/" class="text-sky-300"
							>Wednesday Prayer Meeting: <br /><span class="text-white">7:00 PM</span></a
						>
					</li>
				</ul>
			</div>

			<div class="row-start-3 w-full md:col-start-2 md:row-start-2 md:block">
				<h2 class="mb-6 text-lg font-semibold text-neutral-400 uppercase">Legal</h2>
				<ul class="pl-4 font-medium text-neutral-200 md:pl-0">
					<li class="mb-4">
						<a href="/" class="hover:underline">Privacy Policy</a>
					</li>
					<li>
						<a href="/" class="hover:underline">Terms &amp; Conditions</a>
					</li>
				</ul>
			</div>
			<!-- <hr class="row-end-3 my-2 w-full border-neutral-500 md:row-start-3 md:col-span-2" /> -->
			<div class="col-start-1 row-start-4 w-full">
				<h2 class="mb-6 text-lg font-semibold text-neutral-400 uppercase">Contact Info</h2>
				<ul class="pl-4 space-y-4 font-medium text-neutral-200 md:pl-0">
					<li class="">
						<a
							href="https://www.google.com/maps/search/?api=1&query=5975+US+70+East+La+Grange,+NC+28551"
							target="_blank"
							rel="noopener noreferrer"
						>
							<div class="flex items-center space-x-2 cursor-pointer hover:underline">
								<svg
									class="h-12 max-w-[1.5rem] text-sky-300"
									xmlns="http://www.w3.org/2000/svg"
									width="auto"
									height="auto"
									viewBox="0 0 16 16"
								>
									<path
										fill="currentColor"
										fill-rule="evenodd"
										d="m7.539 14.841l.003.003l.002.002a.755.755 0 0 0 .912 0l.002-.002l.003-.003l.012-.009a6 6 0 0 0 .19-.153a15.6 15.6 0 0 0 2.046-2.082C11.81 11.235 13 9.255 13 7A5 5 0 0 0 3 7c0 2.255 1.19 4.235 2.292 5.597a15.6 15.6 0 0 0 2.046 2.082l.189.153zM8 8.5a1.5 1.5 0 1 0 0-3a1.5 1.5 0 0 0 0 3"
										clip-rule="evenodd"
									/>
								</svg>
								<p>5975 US 70 East La Grange, NC 28551</p>
							</div>
						</a>
					</li>
					<li>
						<a href="tel:+12525662170">
							<div class="flex items-center space-x-2 cursor-pointer hover:underline">
								<svg
									class="h-8 max-w-[1.5rem] text-sky-300"
									xmlns="http://www.w3.org/2000/svg"
									width="auto"
									height="auto"
									viewBox="0 0 20 20"
								>
									<path
										fill="currentColor"
										fill-rule="evenodd"
										d="M2 3.5A1.5 1.5 0 0 1 3.5 2h1.148a1.5 1.5 0 0 1 1.465 1.175l.716 3.223a1.5 1.5 0 0 1-1.052 1.767l-.933.267c-.41.117-.643.555-.48.95a11.54 11.54 0 0 0 6.254 6.254c.395.163.833-.07.95-.48l.267-.933a1.5 1.5 0 0 1 1.767-1.052l3.223.716A1.5 1.5 0 0 1 18 15.352V16.5a1.5 1.5 0 0 1-1.5 1.5H15c-1.149 0-2.263-.15-3.326-.43A13.02 13.02 0 0 1 2.43 8.327A13 13 0 0 1 2 5z"
										clip-rule="evenodd"
									/>
								</svg>
								<p>(252) 566-2170</p>
							</div>
						</a>
					</li>
					<li>
						<a href="mailto:info@emmanuelbaptistnc.org">
							<div class="flex items-center space-x-2 cursor-pointer hover:underline">
								<svg
									class="h-8 max-w-[1.5rem] text-sky-300"
									xmlns="http://www.w3.org/2000/svg"
									width="auto"
									height="auto"
									viewBox="0 0 24 24"
								>
									<g fill="currentColor">
										<path
											d="M1.5 8.67v8.58a3 3 0 0 0 3 3h15a3 3 0 0 0 3-3V8.67l-8.928 5.493a3 3 0 0 1-3.144 0z"
										/>
										<path
											d="M22.5 6.908V6.75a3 3 0 0 0-3-3h-15a3 3 0 0 0-3 3v.158l9.714 5.978a1.5 1.5 0 0 0 1.572 0z"
										/>
									</g>
								</svg>
								<p>info@emmanuelbaptistnc.org</p>
							</div>
						</a>
					</li>
				</ul>
			</div>
		</div>
		<hr class="my-12 border-neutral-200 sm:mx-auto dark:border-neutral-700 lg:my-8" />
		<div class="pb-8 sm:flex sm:items-center sm:justify-between">
			<span class="text-sm text-neutral-200 sm:text-center"
				>© {currentYear}
				<a href="https://emmanuelbaptistnc.org/" class="hover:underline">Emmanuel Baptist Church</a
				>.
				<br class="md:hidden" />
				All Rights Reserved.
			</span>
			<div class="flex mt-4 sm:justify-center sm:mt-0">
				<span class="text-neutral-200 hover:text-neutral-900 dark:hover:text-white">
					<Facebook />
					<span class="sr-only">Facebook page</span>
				</span>
			</div>
		</div>
	</div>
</footer>
