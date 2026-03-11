<script lang="ts">
	import SmallCalendar from '$lib/components/SmallCalendar.svelte';
	import calendarEvents from '$lib/data/calendar-events.json';
	import '../global.css';
</script>

<div id="main" class="flex flex-col items-center space-y-0 grow min-h-40">
	<!-- ********** HERO SECTION ********** -->
	<section
		class="relative w-screen overflow-hidden -mt-6 md:max-h-dvh py-12"
		aria-labelledby="home-title"
	>
		<!-- Background gradient (subtle, intentional) -->
		<div
			aria-hidden="true"
			class="absolute inset-0 -z-10 bg-gradient-to-br from-sky-50 via-sky-50 to-white"
		></div>

		<!-- Optional soft blobs (kept subtle) -->
		<div aria-hidden="true" class="pointer-events-none absolute inset-0 -z-10 opacity-40">
			<div
				class="absolute left-[-10%] top-16 h-56 w-96 blur-[106px] bg-gradient-to-br from-sky-200 to-sky-400"
			></div>
			<div
				class="absolute right-[-8%] top-40 h-40 w-80 blur-[106px] bg-gradient-to-r from-sky-300 to-sky-200"
			></div>
		</div>

		<div id="home" class="mx-auto w-full max-w-7xl px-6 md:px-12 xl:px-6 scroll-mt-28">
			<div class="mx-auto max-w-2xl py-20 sm:py-28 text-center">
				<h1
					id="home-title"
					class="flex flex-col gap-2 sm:gap-3 text-5xl sm:text-6xl font-extrabold tracking-tight text-zinc-900 pb-8"
				>
					<span class="animate-fade-up animate-duration-700 animate-delay-1500 animate-ease-linear"
						>Truth.</span
					>
					<span class="animate-fade-up animate-duration-700 animate-delay-500 animate-ease-linear"
						>Hope.</span
					>
					<span class="animate-fade-up animate-duration-700 animate-delay-1000 animate-ease-linear"
						>Community.</span
					>
				</h1>

				<p class="mt-6 text-lg leading-7 text-zinc-700">
					A loving church in La Grange, NC that believes in the life-changing power of Jesus.
					Sharing His truth and hope in our community and around the world.
				</p>

				<!-- CTAs -->
				<div class="mt-10 flex flex-wrap items-center justify-center gap-4">
					<a
						href="/plan-your-visit"
						class="inline-flex items-center justify-center rounded-full bg-sky-600 px-6 py-3 text-base font-semibold text-white shadow-sm hover:bg-sky-700 focus:outline-none focus-visible:ring-2 focus-visible:ring-sky-300 w-11/12 md:w-56 h-12"
					>
						Plan Your Visit
					</a>
					<a
						href="#discover"
						class="inline-flex items-center justify-center rounded-full border border-zinc-300 bg-white px-6 py-3 text-base font-semibold text-zinc-900 hover:bg-zinc-50 focus:outline-none focus-visible:ring-2 focus-visible:ring-sky-300 w-11/12 md:w-56 h-12"
					>
						Learn More
					</a>
				</div>
			</div>

			<!-- Information subsection -->
			<div class="mx-auto mt-6 grid w-full max-w-5xl gap-6 pb-12 sm:grid-cols-2">
				<!-- Service Times -->
				<div class="rounded-xl border border-zinc-200 bg-white p-6 shadow-sm">
					<h2 class="mb-4 text-lg font-semibold text-zinc-900">Service Times</h2>
					<ul class="space-y-4 text-zinc-700">
						<li class="flex items-center justify-between">
							<span class="text-left">Sunday<br />Bible Study</span>
							<time class="text-right text-zinc-600">10:00 AM</time>
						</li>
						<li class="flex items-center justify-between">
							<span class="text-left">Sunday Worship</span>
							<span class="text-right text-zinc-600">11:00 AM<br />&amp; 6:30 PM</span>
						</li>
						<li class="flex items-center justify-between">
							<span class="text-left">Wednesday<br />Prayer Meeting</span>
							<time class="text-right text-zinc-600">7:00 PM</time>
						</li>
					</ul>
				</div>

				<!-- Contact Info -->
				<div class="rounded-xl border border-zinc-200 bg-white p-6 shadow-sm">
					<h2 class="mb-4 text-lg font-semibold text-zinc-900">Contact Info</h2>
					<ul class="space-y-4 text-zinc-700">
						<li>
							<a
								href="https://www.google.com/maps/search/?api=1&amp;query=5975+US+70+East+La+Grange,+NC+28551"
								target="_blank"
								rel="noopener noreferrer"
								class="group inline-flex items-start gap-3 hover:underline"
							>
								<svg class="mt-0.5 h-5 w-5 text-zinc-500" viewBox="0 0 16 16" fill="currentColor"
									><path
										fill="currentColor"
										fill-rule="evenodd"
										d="m7.539 14.841l.003.003l.002.002a.755.755 0 0 0 .912 0l.002-.002l.003-.003l.012-.009a6 6 0 0 0 .19-.153a15.6 15.6 0 0 0 2.046-2.082C11.81 11.235 13 9.255 13 7A5 5 0 0 0 3 7c0 2.255 1.19 4.235 2.292 5.597a15.6 15.6 0 0 0 2.046 2.082l.189.153zM8 8.5a1.5 1.5 0 1 0 0-3a1.5 1.5 0 0 0 0 3"
										clip-rule="evenodd"
									></path></svg
								>
								<span>5975 US 70 East<br />La Grange, NC 28551</span>
							</a>
						</li>
						<li>
							<a
								href="tel:+12525662170"
								class="group inline-flex items-center gap-3 hover:underline"
							>
								<svg class="h-5 w-5 text-zinc-500" viewBox="0 0 20 20" fill="currentColor"
									><path
										fill="currentColor"
										fill-rule="evenodd"
										d="M2 3.5A1.5 1.5 0 0 1 3.5 2h1.148a1.5 1.5 0 0 1 1.465 1.175l.716 3.223a1.5 1.5 0 0 1-1.052 1.767l-.933.267c-.41.117-.643.555-.48.95a11.54 11.54 0 0 0 6.254 6.254c.395.163.833-.07.95-.48l.267-.933a1.5 1.5 0 0 1 1.767-1.052l3.223.716A1.5 1.5 0 0 1 18 15.352V16.5a1.5 1.5 0 0 1-1.5 1.5H15c-1.149 0-2.263-.15-3.326-.43A13.02 13.02 0 0 1 2.43 8.327A13 13 0 0 1 2 5z"
										clip-rule="evenodd"
									></path></svg
								>
								<span>(252) 566-2170</span>
							</a>
						</li>
						<li>
							<a
								href="mailto:info@emmanuelbaptistnc.org"
								class="group inline-flex items-center gap-3 hover:underline"
							>
								<svg class="h-5 w-5 text-zinc-500" viewBox="0 0 20 20" fill="currentColor"
									><path
										fill="currentColor"
										fill-rule="evenodd"
										d="M2 5a1 1 0 0 1 1-1h14a1 1 0 0 1 1 1v10a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V5zm1 0v10h14V5H3z"
										clip-rule="evenodd"
									></path>
									<path fill="currentColor" d="M4 6.5l6 4l6-4V5l-6 4l-6-4v1.5z"></path>
								</svg>
								<span>info@emmanuelbaptistnc.org</span>
							</a>
						</li>
					</ul>
				</div>
			</div>
		</div>
	</section>

	<!-- /**********/ DISCOVER SECTION /**********/ -->
	<section id="discover" class="w-screen border-t border-zinc-200 bg-white py-20">
		<div class="mx-auto w-full max-w-6xl px-6 md:px-12 xl:px-6">
			<!-- Header -->
			<div class="mx-auto max-w-2xl text-center">
				<h2 class="text-3xl sm:text-4xl font-semibold tracking-tight text-zinc-900">
					Discover Emmanuel
				</h2>
				<p class="mt-2 text-zinc-600">
					Learn more about who we are, how we serve God and others, and what we believe.
				</p>
			</div>

			<!-- Cards -->
			<div class="mt-12 grid gap-6 sm:gap-8 sm:grid-cols-2 lg:grid-cols-3">
				<!-- Card 1 -->
				<a
					href="/about#our-pastor"
					class="group block overflow-hidden rounded-xl border border-zinc-200 bg-white shadow-sm transition hover:shadow-md focus:outline-none focus-visible:ring-2 focus-visible:ring-sky-300"
				>
					<div class="relative overflow-hidden">
						<img
							src="https://ik.imagekit.io/bip1v395ybp/Emmanuel%20Baptist%20Church/mini-pastor-garner_FiOaKJ7bb.webp?updatedAt=1729398571290"
							alt="Pastor Ricky Garner"
							loading="lazy"
							width="1000"
							height="667"
							class="h-56 w-full object-cover object-top transition-transform duration-500 group-hover:scale-105"
						/>
					</div>
					<div class="p-5 sm:p-6">
						<h3 class="text-lg sm:text-xl font-semibold text-zinc-900">Leadership</h3>
						<p class="mt-2 text-sm text-zinc-600">
							Pastor Ricky Garner, Pastor of Emmanuel Baptist Church
						</p>
						<span class="mt-4 inline-flex items-center gap-2 font-medium text-sky-700">
							<span>Learn more</span>
							<svg
								class="h-4 w-4 opacity-0 -translate-x-1 transition group-hover:translate-x-0 group-hover:opacity-100"
								viewBox="0 0 24 24"
								fill="currentColor"
								aria-hidden="true"
							>
								<path
									fill-rule="evenodd"
									d="M12.97 3.97a.75.75 0 0 1 1.06 0l7.5 7.5a.75.75 0 0 1 0 1.06l-7.5 7.5a.75.75 0 1 1-1.06-1.06l6.22-6.22H3a.75.75 0 0 1 0-1.5h16.19l-6.22-6.22a.75.75 0 0 1 0-1.06z"
									clip-rule="evenodd"
								/>
							</svg>
						</span>
					</div>
				</a>

				<!-- Card 2 -->
				<a
					href="/about#ministries"
					class="group block overflow-hidden rounded-xl border border-zinc-200 bg-white shadow-sm transition hover:shadow-md focus:outline-none focus-visible:ring-2 focus-visible:ring-sky-300"
				>
					<div class="relative overflow-hidden">
						<img
							src="https://ik.imagekit.io/bip1v395ybp/Emmanuel%20Baptist%20Church/Church%20Fellowshipping_Dk0eKsE4a7.JPG?updatedAt=1733798803071"
							alt="Church members fellowshipping"
							loading="lazy"
							width="1000"
							height="667"
							class="h-56 w-full object-cover object-top transition-transform duration-500 group-hover:scale-105"
						/>
					</div>
					<div class="p-5 sm:p-6">
						<h3 class="text-lg sm:text-xl font-semibold text-zinc-900">Ministries</h3>
						<p class="mt-2 text-sm text-zinc-600">
							Learn how we serve God in our community and around the world
						</p>
						<span class="mt-4 inline-flex items-center gap-2 font-medium text-sky-700">
							<span>Learn more</span>
							<svg
								class="h-4 w-4 opacity-0 -translate-x-1 transition group-hover:translate-x-0 group-hover:opacity-100"
								viewBox="0 0 24 24"
								fill="currentColor"
								aria-hidden="true"
							>
								<path
									fill-rule="evenodd"
									d="M12.97 3.97a.75.75 0 0 1 1.06 0l7.5 7.5a.75.75 0 0 1 0 1.06l-7.5 7.5a.75.75 0 1 1-1.06-1.06l6.22-6.22H3a.75.75 0 0 1 0-1.5h16.19l-6.22-6.22a.75.75 0 0 1 0-1.06z"
									clip-rule="evenodd"
								/>
							</svg>
						</span>
					</div>
				</a>

				<!-- Card 3 -->
				<a
					href="/about#beliefs"
					class="group block overflow-hidden rounded-xl border border-zinc-200 bg-white shadow-sm transition hover:shadow-md focus:outline-none focus-visible:ring-2 focus-visible:ring-sky-300"
				>
					<div class="relative overflow-hidden">
						<img
							src="https://images.unsplash.com/photo-1499051775559-dcb9f02d2107?q=80&w=3174&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
							alt="Open Bible on a desk"
							loading="lazy"
							width="1000"
							height="667"
							class="h-56 w-full object-cover object-top transition-transform duration-500 group-hover:scale-105"
						/>
					</div>
					<div class="p-5 sm:p-6">
						<h3 class="text-lg sm:text-xl font-semibold text-zinc-900">Beliefs</h3>
						<p class="mt-2 text-sm text-zinc-600">The core doctrines that guide our life and ministry.</p>
						<span class="mt-4 inline-flex items-center gap-2 font-medium text-sky-700">
							<span>Learn more</span>
							<svg
								class="h-4 w-4 opacity-0 -translate-x-1 transition group-hover:translate-x-0 group-hover:opacity-100"
								viewBox="0 0 24 24"
								fill="currentColor"
								aria-hidden="true"
							>
								<path
									fill-rule="evenodd"
									d="M12.97 3.97a.75.75 0 0 1 1.06 0l7.5 7.5a.75.75 0 0 1 0 1.06l-7.5 7.5a.75.75 0 1 1-1.06-1.06l6.22-6.22H3a.75.75 0 0 1 0-1.5h16.19l-6.22-6.22a.75.75 0 0 1 0-1.06z"
									clip-rule="evenodd"
								/>
							</svg>
						</span>
					</div>
				</a>
			</div>
		</div>
	</section>

	<!-- ********** MEDIA SECTION ********** -->
	<section id="media" class="w-screen border-y border-zinc-200 bg-zinc-50 py-20">
		<div class="mx-auto w-full max-w-7xl px-6 md:px-12 xl:px-6">
			<!-- Header -->
			<div class="mx-auto max-w-2xl text-center">
				<h2 class="text-3xl sm:text-4xl font-semibold tracking-tight text-zinc-900">
					Latest Service
				</h2>
			</div>

			<!-- Player -->
			<div class="mx-auto mt-8 max-w-5xl rounded-xl border border-zinc-200">
				<div class="relative overflow-hidden rounded-xl ring-1 ring-zinc-200 shadow-sm">
					<!-- 16:9 wrapper; use aspect-video if your Tailwind config supports it -->
					<div class="relative w-full pb-[56.25%]">
						<iframe
							title="EBC Livestream or Latest Sermon"
							allow="autoplay; fullscreen; picture-in-picture"
							class="absolute inset-0 h-full w-full"
							src="https://control.resi.io/webplayer/video.html?id=ae4b050f-68f2-458f-834e-bd578c9b51d3&startPos=240&debug&autoplay=1"
							style="border:0"
						></iframe>
					</div>
				</div>
			</div>

			<!-- CTA -->
			<div class="mt-10 flex justify-center">
				<a
					href="https://www.youtube.com/@emmanuelbaptistnc85/streams"
					target="_blank"
					rel="noopener noreferrer"
					class="inline-flex h-12 items-center justify-center rounded-full border border-zinc-300 bg-white px-6 text-base font-semibold text-zinc-900 transition-colors hover:bg-zinc-50 focus:outline-none focus-visible:ring-2 focus-visible:ring-sky-300 focus-visible:ring-offset-2"
				>
					View Past Sermons
				</a>
			</div>

			<script defer src="https://control.resi.io/webplayer/page.min.js"></script>
		</div>
	</section>

<!-- ********** EVENTS SECTION ********** -->
<section id="events" class="w-screen border-t border-zinc-200 bg-white py-20">
  <div class="mx-auto w-full max-w-7xl px-6 md:px-12 xl:px-6">
    <div class="mx-auto max-w-2xl text-center">
      <h2 class="text-3xl sm:text-4xl font-semibold tracking-tight text-zinc-900">
        Upcoming Events
      </h2>
      <p class="mt-2 text-zinc-600">
        See what events are planned for the coming weeks. Join us as we grow in faith and fellowship together.
      </p>
    </div>

    <!-- Calendar -->
    <div class="mx-auto mt-10 overflow-hidden  bg-transparent ">
      <SmallCalendar events={calendarEvents} />
    </div>
  </div>
</section>

<!-- ********** GIVE SECTION ********** -->
<section id="give" class="w-screen border-t border-zinc-200 bg-zinc-50 py-20">
  <div class="mx-auto w-full max-w-7xl px-6 md:px-12 xl:px-6">
    <div class="mx-auto max-w-2xl text-center">
      <h2 class="text-3xl sm:text-4xl font-semibold tracking-tight text-zinc-900">Giving</h2>
      <h3 class="mt-2 text-xl font-medium text-zinc-800">
        Your obedience and generosity is changing lives.
      </h3>
      <p class="mt-4 text-zinc-600">
        Our church's mission is funded solely by the giving of members and regular attenders.
        You can give by cash or check in any of our services or at our church office throughout the week.
      </p>
    </div>

    <div class="mx-auto mt-10 w-full max-w-3xl space-y-4">
      <!-- On Campus -->
      <div class="flex items-center gap-4 rounded-xl border border-zinc-200 bg-white p-5 shadow-sm">
        <div class="flex h-10 w-10 items-center justify-center rounded-full bg-sky-600 text-white">
          <!-- house icon -->
          <svg class="h-5 w-5" viewBox="0 0 256 256" fill="currentColor" aria-hidden="true">
            <path d="M227.09 146.86L190 124.6V104a6 6 0 0 0-3-5.21l-53-30.27V46h18a6 6 0 0 0 0-12h-18V16a6 6 0 0 0-12 0v18h-18a6 6 0 0 0 0 12h18v22.52L69 98.79a6 6 0 0 0-3 5.21v20.6l-37.09 22.26A6 6 0 0 0 26 152v64a6 6 0 0 0 6 6h80a6 6 0 0 0 6-6v-48a10 10 0 0 1 20 0v48a6 6 0 0 0 6 6h80a6 6 0 0 0 6-6v-64a6 6 0 0 0-2.91-5.14M38 155.4l28-16.8V210H38Zm90-9.4a22 22 0 0 0-22 22v42H78V107.48l50-28.57l50 28.57V210h-28v-42a22 22 0 0 0-22-22m90 64h-28v-71.4l28 16.8Z"/>
          </svg>
        </div>
        <h4 class="text-lg font-semibold text-zinc-900">On Campus</h4>
      </div>

      <!-- By Mail -->
      <div class="flex items-center gap-4 rounded-xl border border-zinc-200 bg-white p-5 shadow-sm">
        <div class="flex h-10 w-10 items-center justify-center rounded-full bg-zinc-700 text-white">
          <!-- envelope icon -->
          <svg class="h-5 w-5" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true">
            <path d="M8 12h2a1 1 0 0 0 0-2H8a1 1 0 0 0 0 2m9-6h-5V4h1a1 1 0 0 0 0-2h-2a1 1 0 0 0-1 1v3H7a4 4 0 0 0-4 4v6a1 1 0 0 0 1 1h6v4a1 1 0 0 0 2 0v-4h8a1 1 0 0 0 1-1v-6a4 4 0 0 0-4-4m-4 4v5H5v-5a2 2 0 0 1 2-2h6.56a3.9 3.9 0 0 0-.56 2m6 5h-4v-5a2 2 0 0 1 4 0Z"/>
          </svg>
        </div>
        <h4 class="text-lg font-semibold text-zinc-900">By Mail</h4>
      </div>

      <!-- Online (Coming Soon) -->
      <div class="flex items-center gap-4 rounded-xl border border-zinc-200 bg-white p-5 shadow-sm">
        <div class="flex h-10 w-10 items-center justify-center rounded-full bg-zinc-400 text-white">
          <!-- globe icon -->
          <svg class="h-5 w-5" viewBox="0 0 16 16" fill="currentColor" aria-hidden="true">
            <path d="M16 7.38A7.82 7.82 0 0 0 8 .5a7.82 7.82 0 0 0-8 6.88v1.24a7.82 7.82 0 0 0 8 6.88a7.82 7.82 0 0 0 8-6.88zm-1.25 0h-3a11.3 11.3 0 0 0-.43-2.54a7.6 7.6 0 0 0 1.75-1a6 6 0 0 1 1.65 3.54zm-9.18 0a9.7 9.7 0 0 1 .37-2.14A8.4 8.4 0 0 0 8 5.5a8.5 8.5 0 0 0 2.09-.26a10.2 10.2 0 0 1 .37 2.14zm4.92 1.24a9.6 9.6 0 0 1-.37 2.14a8.5 8.5 0 0 0-4.18 0a9.7 9.7 0 0 1-.37-2.14zm.4-5A12 12 0 0 0 10 2a6.9 6.9 0 0 1 2 1a6.6 6.6 0 0 1-1.14.66zm-2.6-1.86a10 10 0 0 1 1.38 2.3A7.6 7.6 0 0 1 8 4.25a7.6 7.6 0 0 1-1.67-.19a9.8 9.8 0 0 1 1.38-2.3zm-3.15 1.9A6.6 6.6 0 0 1 4 3a6.9 6.9 0 0 1 2-1a10.4 10.4 0 0 0-.86 1.66M3 3.83a7.6 7.6 0 0 0 1.75 1a11 11 0 0 0-.43 2.54h-3A6 6 0 0 1 3 3.83M1.28 8.62h3a11 11 0 0 0 .43 2.54a7.6 7.6 0 0 0-1.75 1a6 6 0 0 1-1.68-3.54m3.86 3.72A10.4 10.4 0 0 0 6 14a6.9 6.9 0 0 1-2-1a6.6 6.6 0 0 1 1.14-.66m2.57 1.9a9.8 9.8 0 0 1-1.38-2.3a7.4 7.4 0 0 1 3.34 0a9.8 9.8 0 0 1-1.38 2.3zm3.15-1.9a6.6 6.6 0 0 1 1.19.66a7.2 7.2 0 0 1-2 1a11.5 11.5 0 0 0 .81-1.66m2.14-.17a7.6 7.6 0 0 0-1.75-1a10.8 10.8 0 0 0 .43-2.54h3A6 6 0 0 1 13 12.17"/>
          </svg>
        </div>
        <h4 class="text-lg font-semibold text-zinc-900">Online (Coming Soon)</h4>
      </div>
    </div>
  </div>
</section>

</div>
