<script lang="ts">
	//   export let class: string = 'border-b';
	const currentYear = new Date().getFullYear();
</script>

<div class={`w-full bg-theme-200 text-white`}>
	<!-- The footer keeps the same grid structure using the centralized container -->
	<div class="container-content py-6 lg:py-8">
		<div class="grid grid-cols-1 gap-y-8 md:grid-cols-2">
			<!-- Left: Logo + Service Times -->
			<div class="space-y-8">
				<a href="/#home" class="flex items-center h-12">
					<img
						src="https://ik.imagekit.io/bip1v395ybp/Emmanuel%20Baptist%20Church/ebc-logo-new-large_WrsHKgywk.png?updatedAt=1730625294622"
						alt="logo"
						class="w-11 h-11"
					/>
					<svg
						class="h-12 w-auto text-neutral-50 md:ml-2 p-1"
						xmlns="http://www.w3.org/2000/svg"
						viewBox="0 0 204 57"
						fill="none"
						aria-hidden="true"
					>
						<!-- ... same SVG as header, but white ... -->
					</svg>
				</a>

				<div>
					<h2 class="mb-4 font-semibold text-neutral-300 uppercase text-md">Service Times</h2>
					<ul class="space-y-4 font-medium text-neutral-100">
						<li class="text-sky-300 text-md">
							Sunday Bible Study<br /><span class="text-white">10:00 AM</span>
						</li>
						<li class="text-sky-300 text-md">
							Sunday Worship<br /><span class="text-white">11:00 AM &amp; 6:30 PM</span>
						</li>
						<li class="text-sky-300 text-md">
							Wednesday Prayer Meeting<br /><span class="text-white">7:00 PM</span>
						</li>
					</ul>
				</div>
			</div>

			<!-- Right: Contact Info -->
			<div>
				<h2 class="mb-4 font-semibold text-neutral-300 uppercase text-md">Contact Info</h2>
				<ul class="space-y-4 font-medium text-neutral-100">
					<li>
						<a
							href="https://www.google.com/maps/search/?api=1&amp;query=5975+US+70+East+La+Grange,+NC+28551"
							target="_blank"
							rel="noopener noreferrer"
							class="flex items-center gap-4 hover:underline"
						>
							<svg
								class="h-6 w-6 text-sky-300"
								xmlns="http://www.w3.org/2000/svg"
								viewBox="0 0 16 16"
								><path
									fill="currentColor"
									fill-rule="evenodd"
									d="m7.539 14.841l.003.003l.002.002a.755.755 0 0 0 .912 0l.002-.002l.003-.003l.012-.009a6 6 0 0 0 .19-.153a15.6 15.6 0 0 0 2.046-2.082C11.81 11.235 13 9.255 13 7A5 5 0 0 0 3 7c0 2.255 1.19 4.235 2.292 5.597a15.6 15.6 0 0 0 2.046 2.082l.189.153zM8 8.5a1.5 1.5 0 1 0 0-3a1.5 1.5 0 0 0 0 3"
									clip-rule="evenodd"
								/></svg
							>
							<span>5975 US 70 East La Grange, NC 28551</span>
						</a>
					</li>
					<li>
						<a href="tel:+12525662170" class="flex items-center gap-4 hover:underline">
							<svg
								class="h-6 w-6 text-sky-300"
								xmlns="http://www.w3.org/2000/svg"
								viewBox="0 0 20 20"
								><path
									fill="currentColor"
									fill-rule="evenodd"
									d="M2 3.5A1.5 1.5 0 0 1 3.5 2h1.148a1.5 1.5 0 0 1 1.465 1.175l.716 3.223a1.5 1.5 0 0 1-1.052 1.767l-.933.267c-.41.117-.643.555-.48.95a11.54 11.54 0 0 0 6.254 6.254c.395.163.833-.07.95-.48l.267-.933a1.5 1.5 0 0 1 1.767-1.052l3.223.716A1.5 1.5 0 0 1 18 15.352V16.5a1.5 1.5 0 0 1-1.5 1.5H15c-1.149 0-2.263-.15-3.326-.43A13.02 13.02 0 0 1 2.43 8.327A13 13 0 0 1 2 5z"
									clip-rule="evenodd"
								/></svg
							>
							<span>(252) 566-2170</span>
						</a>
					</li>
					<li>
						<a
							href="mailto:info@emmanuelbaptistnc.org"
							class="flex items-center gap-4 hover:underline"
						>
							<svg
								class="h-6 w-6 text-sky-300"
								xmlns="http://www.w3.org/2000/svg"
								viewBox="0 0 24 24"
								><g fill="currentColor"
									><path
										d="M1.5 8.67v8.58a3 3 0 0 0 3 3h15a3 3 0 0 0 3-3V8.67l-8.928 5.493a3 3 0 0 1-3.144 0z"
									/><path
										d="M22.5 6.908V6.75a3 3 0 0 0-3-3h-15a3 3 0 0 0-3 3v.158l9.714 5.978a1.5 1.5 0 0 0 1.572 0z"
									/></g
								></svg
							>
							<span>info@emmanuelbaptistnc.org</span>
						</a>
					</li>
				</ul>
			</div>
		</div>

		<hr class="my-8 border-neutral-200 dark:border-neutral-700" />

		<div class="flex flex-col sm:flex-row sm:items-center sm:justify-between gap-4">
			<div class="text-neutral-200 leading-relaxed">
				<p class="text-base">
					<span class="mr-2 whitespace-nowrap">© {currentYear} • Emmanuel Baptist Church.</span>
					<span class="mr-2">All Rights Reserved.</span>
					<a href="/legal#privacy-policy" class="underline hover:text-sky-300">Privacy Policy</a>
					<span class="mx-2">&amp;</span>
					<a href="/legal#terms-of-service" class="underline hover:text-sky-300">Terms of Use</a>
				</p>
			</div>

			<div>
				<a
					href="https://www.facebook.com/emmanuelchurchlagrange/"
					target="_blank"
					rel="noopener noreferrer"
					class="text-neutral-200 hover:text-sky-300"
					aria-label="Facebook page"
				>
					<svg class="h-8 md:h-10 w-auto" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"
						><path
							fill="currentColor"
							d="M22 12c0-5.52-4.48-10-10-10S2 6.48 2 12c0 4.84 3.44 8.87 8 9.8V15H8v-3h2V9.5C10 7.57 11.57 6 13.5 6H16v3h-2c-.55 0-1 .45-1 1v2h3v3h-3v6.95c5.05-.5 9-4.76 9-9.95"
						/></svg
					>
				</a>
			</div>
		</div>
	</div>
</div>
