<script lang="ts">
	import SmallCalendar from '$lib/components/SmallCalendar.svelte';
	import '../global.css';
</script>

<div id="main" class="flex flex-col items-center space-y-32 grow min-h-40">
	<!-- /**********/ HERO SECTION /**********/ -->
	<section
		class="data-[size=md]:scale-[0.8] data-[size=sm]:scale-75 w-screen relative z-10 ease-in-out flex transition-all duration-700 will-change-auto items-center flex-col space-y-40"
	>
		<div class="relative flex-col items-center max-w-8xl" id="home">
			<!-- GRADIENTS -->
			<div aria-hidden="true" class="grid absolute inset-0 grid-cols-2 -space-x-52 opacity-40">
				<div class="blur-[106px] h-56 bg-gradient-to-br from-theme-800 to-purple-400"></div>
				<div class="blur-[106px] h-32 bg-gradient-to-r from-cyan-400 to-sky-300"></div>
			</div>
			<!-- HERO SECTION -->
			<div class="flex-col items-center px-6 mx-auto w-full max-w-7xl md:px-12 xl:px-6">
				<div class="relative flex-col items-center pt-36 ml-auto">
					<div class="flex-col items-center mx-auto w-full text-center md:w-1/2 lg:w-2/3">
						<h1 class="text-5xl font-bold text-mono-900 md:text-6xl xl:text-7xl">
							<span
								class="animate-fade-up animate-duration-700 animate-delay-1500 animate-ease-linear"
								>Truth.</span
							>
							<br />
							<span
								class="animate-fade-up animate-duration-700 animate-delay-500 animate-ease-linear"
								>Hope.</span
							>
							<br />
							<span
								class="animate-fade-up animate-duration-700 animate-delay-1000 animate-ease-linear"
								>Community.</span
							>
						</h1>

						<p class="mt-8 text-mono-700">
							A loving church in La Grange, NC that believes in the life-changing power of Jesus.
							Sharing His truth and hope in our community and around the world.
						</p>
						<!-- CALL-TO-ACTION BUTTONS -->
						<div class="flex flex-wrap gap-y-4 gap-x-6 justify-center mt-16">
							<a
								href="/plan-your-visit"
								class="flex relative justify-center items-center px-6 w-full h-12 md:h-14 md:w-64 before:absolute before:inset-0 before:rounded-full after:rounded-full before:transition before:duration-300 hover:before:scale-105 active:duration-75 active:before:scale-95 sm:w-max before:bg-gradient-to-tr before:from-blue-700 before:to-theme-900"
							>
								<span
									class="relative w-32 text-base font-semibold text-center text-white capitalize"
									>Plan your visit</span
								>
							</a>
							<a
								href="#discover"
								class="flex relative justify-center items-center px-6 w-full h-12 md:h-14 md:w-64 before:absolute before:inset-0 before:rounded-full before:border before:border-transparent before:bg-mono-200 before:bg-gradient-to-b before:transition before:duration-300 hover:before:scale-105 active:duration-75 active:before:scale-95 sm:w-max"
							>
								<span class="relative w-32 text-base font-semibold capitalize">Learn more</span>
							</a>
						</div>
						<!-- INFORMATION SUBSECTION -->
						<div class="gap-x-12 justify-evenly py-8 mt-16 w-full sm:flex">
							<div class="text-center grow min-w-[300px]">
								<div class="p-6 rounded-lg border border-mono-200">
									<h6 class="mb-4 text-lg font-bold text-mono-700">Service Times</h6>
									<ul class="pl-4 space-y-4 font-medium text-mono-500 md:pl-0">
										<li class="flex justify-between items-center">
											<span class="text-left">Sunday <br /> Bible Study</span>
											<span class="text-right">10:00 AM</span>
										</li>
										<li class="flex justify-between items-center">
											<span class="text-left">Sunday Worship</span>
											<span class="text-right">11:00 AM <br /> &amp; 6:30 PM</span>
										</li>
										<li class="flex justify-between items-center">
											<span class="text-left">Wednesday <br /> Prayer Meeting</span>
											<span class="text-right">7:00 PM</span>
										</li>
									</ul>
								</div>
							</div>
							<div class="text-center grow min-w-[300px]">
								<div class="p-6 mt-4 rounded-lg border border-mono-200 md:mt-0">
									<h6 class="mb-6 text-lg font-bold text-mono-700">Contact Info</h6>
									<ul class="pl-4 space-y-4 font-medium text-mono-500 md:pl-0">
										<li class="flex flex-col text-left md:flex-row md:justify-start">
											<a
												href="https://www.google.com/maps/search/?api=1&amp;query=5975+US+70+East+La+Grange,+NC+28551"
												target="_blank"
												rel="noopener noreferrer"
											>
												<div class="flex items-center space-x-4 cursor-pointer hover:underline">
													<svg
														class="h-8 max-w-[1.5rem]"
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
														></path>
													</svg>
													<p>5975 US 70 East <br /> La Grange, NC 28551</p>
												</div>
											</a>
										</li>
										<li class="flex flex-col text-left md:flex-row md:justify-between">
											<a href="tel:+12525662170">
												<div class="flex items-center space-x-4 cursor-pointer hover:underline">
													<svg
														class="h-8 max-w-[1.5rem]"
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
														></path>
													</svg>
													<p>(252) 566-2170</p>
												</div>
											</a>
										</li>
										<li class="flex flex-col text-left md:flex-row md:justify-between">
											<a href="mailto:info@emmanuelbaptistnc.org">
												<div class="flex items-center space-x-4 cursor-pointer hover:underline">
													<svg
														class="h-8 max-w-[1.5rem]"
														xmlns="http://www.w3.org/2000/svg"
														width="auto"
														height="auto"
														viewBox="0 0 20 20"
													>
														<path
															fill="currentColor"
															fill-rule="evenodd"
															d="M2 5a1 1 0 0 1 1-1h14a1 1 0 0 1 1 1v10a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V5zm1 0v10h14V5H3z"
															clip-rule="evenodd"
														></path>
														<path fill="currentColor" d="M4 6.5l6 4l6-4V5l-6 4l-6-4v1.5z"></path>
													</svg>
													<p>info@emmanuelbaptistnc.org</p>
												</div>
											</a>
										</li>
									</ul>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>
	<!-- /**********/ DISCOVER SECTION /**********/ -->
	<section id="discover" class="pt-20 w-screen border-t border-mono-200">
		<div class="flex flex-col items-center px-6 mx-auto max-w-8xl md:px-12 xl:px-6">
			<!-- Header Section -->
			<div class="mx-auto mb-16 text-center md:w-1/2 lg:w-2/3">
				<h2 class="mt-8 text-3xl font-bold text-mono-700 md:text-4xl">Discover Emmanuel</h2>
				<p class="my-8 text-mono-700">
					Learn more about who we are, how we serve God and others, and what we believe
				</p>
			</div>
			<!-- Cards Section -->
			<div class="grid gap-8 justify-center items-center max-w-5xl md:grid-cols-2 lg:grid-cols-3">
				<!-- Card 1 -->
				<a
					href="/about#our-pastor"
					class="p-6 bg-white bg-opacity-50 rounded-2xl border border-mono-100 shadow-2xl cursor-pointer group sm:p-8 shadow-mono-600/10"
				>
					<div class="overflow-hidden relative rounded-md">
						<img
							src="https://ik.imagekit.io/bip1v395ybp/Emmanuel%20Baptist%20Church/mini-pastor-garner_FiOaKJ7bb.webp?updatedAt=1729398571290"
							alt="art cover"
							loading="lazy"
							width="1000"
							height="667"
							class="object-cover object-top w-full h-64 transition duration-500 group-hover:scale-105"
						/>
					</div>
					<div class="mt-6 group relative bg-white transition hover:z-[1]">
						<h3 class="text-2xl font-semibold text-mono-800">Leadership</h3>
						<p class="mt-6 mb-8 text-mono-600 dark:text-mono-300">
							Pastor Ricky Garner, Pastor of Emmanuel Baptist Church
						</p>
						<span class="flex justify-between items-center group-hover:text-mono-900">
							<span class="capitalize text-info">Learn more</span>
							<svg
								xmlns="http://www.w3.org/2000/svg"
								viewBox="0 0 24 24"
								fill="currentColor"
								class="w-5 h-5 opacity-0 transition duration-300 group-hover:opacity-100 group-hover:translate-x-0"
							>
								<path
									fill-rule="evenodd"
									d="M12.97 3.97a.75.75 0 011.06 0l7.5 7.5a.75.75 0 010 1.06l-7.5 7.5a.75.75 0 11-1.06-1.06l6.22-6.22H3a.75.75 0 010-1.5h16.19l-6.22-6.22a.75.75 0 010-1.06z"
									clip-rule="evenodd"
								></path>
							</svg>
						</span>
					</div>
				</a>
				<!-- Card 2 -->
				<a
					href="/about#ministries"
					class="p-6 bg-white bg-opacity-50 rounded-2xl border border-mono-100 shadow-2xl cursor-pointer group sm:p-8 shadow-mono-600/10"
				>
					<div class="overflow-hidden relative rounded-xl">
						<img
							src="https://ik.imagekit.io/bip1v395ybp/Emmanuel%20Baptist%20Church/Church%20Fellowshipping_Dk0eKsE4a7.JPG?updatedAt=1733798803071"
							alt="art cover"
							loading="lazy"
							width="1000"
							height="667"
							class="object-cover object-top w-full h-64 transition duration-500 group-hover:scale-105"
						/>
					</div>
					<div class="mt-6 group relative bg-white transition hover:z-[1]">
						<h3 class="text-2xl font-semibold text-mono-800">Ministries</h3>
						<p class="mt-6 mb-8 text-mono-600 dark:text-mono-300">
							Learn how we serve God in our community and around the world
						</p>
						<span class="flex justify-between items-center group-hover:text-mono-900">
							<span class="capitalize text-info">Learn more</span>
							<svg
								xmlns="http://www.w3.org/2000/svg"
								viewBox="0 0 24 24"
								fill="currentColor"
								class="w-5 h-5 opacity-0 transition duration-300 group-hover:opacity-100 group-hover:translate-x-0"
							>
								<path
									fill-rule="evenodd"
									d="M12.97 3.97a.75.75 0 011.06 0l7.5 7.5a.75.75 0 010 1.06l-7.5 7.5a.75.75 0 11-1.06-1.06l6.22-6.22H3a.75.75 0 010-1.5h16.19l-6.22-6.22a.75.75 0 010-1.06z"
									clip-rule="evenodd"
								></path>
							</svg>
						</span>
					</div>
				</a>
				<!-- Card 3 -->
				<a
					href="/about#beliefs"
					class="p-6 bg-white bg-opacity-50 rounded-2xl border border-mono-100 shadow-2xl cursor-pointer group sm:p-8 shadow-mono-600/10"
				>
					<div class="overflow-hidden relative rounded-xl">
						<img
							src="https://images.unsplash.com/photo-1499051775559-dcb9f02d2107?q=80&w=3174&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
							alt="art cover"
							loading="lazy"
							width="1000"
							height="667"
							class="object-cover object-top w-full h-64 transition duration-500 group-hover:scale-105"
						/>
					</div>
					<div class="mt-6 group relative bg-white transition hover:z-[1]">
						<h3 class="text-2xl font-semibold text-mono-800">Beliefs</h3>
						<p class="mt-6 mb-8 text-mono-600 dark:text-mono-300">
							The beliefs that guide our behaviors
						</p>
						<span class="flex justify-between items-center group-hover:text-mono-900">
							<span class="capitalize text-info">Learn more</span>
							<svg
								xmlns="http://www.w3.org/2000/svg"
								viewBox="0 0 24 24"
								fill="currentColor"
								class="w-5 h-5 opacity-0 transition duration-300 group-hover:opacity-100 group-hover:translate-x-0"
							>
								<path
									fill-rule="evenodd"
									d="M12.97 3.97a.75.75 0 011.06 0l7.5 7.5a.75.75 0 010 1.06l-7.5 7.5a.75.75 0 11-1.06-1.06l6.22-6.22H3a.75.75 0 010-1.5h16.19l-6.22-6.22a.75.75 0 010-1.06z"
									clip-rule="evenodd"
								></path>
							</svg>
						</span>
					</div>
				</a>
			</div>
		</div>
	</section>
	<!-- /**********/ MEDIA SECTION /**********/ -->
	<section id="media" class="relative py-12 mt-40 w-screen bg-mono-200 border-y">
		<div class="flex-col items-center mx-auto w-screen text-center md:w-3/4">
			<h2 class="mt-8 text-3xl font-bold text-mono-700 md:text-4xl mb-12">Latest Sermon</h2>
			<!-- <p class="px-4 my-8 mb-16 text-mono-700">
				The Christian's Role In Government by Pastor Ricky Garner
			</p>
			<video class="object-cover pb-4 w-screen h-full rounded-xl" autoplay muted loop controls>
				<source
					src="https://pub-6221dcfef65c4b58b96f2c7c9868de3c.r2.dev/Christians-Role-In-Government.mp4"
					type="video/mp4"
				/>
				Your browser does not support the video tag.
			</video> -->
			<div style="position:relative;overflow:hidden;padding-top:56.25%;">
				<iframe
					title="EBC Livestream or Latest Sermon"
					allow="autoplay; fullscreen"
					class="resi-video-frame"
					src="https://control.resi.io/webplayer/video.html?id=ae4b050f-68f2-458f-834e-bd578c9b51d3&startPos=240&debug&autoplay=1"
					style="position:absolute;top:0;left:0;width:100%;height:100%;border:none; border-radius: 15px;"
				>
				</iframe>
			</div>
			<script
				defer
				type="text/javascript"
				src="https://control.resi.io/webplayer/page.min.js"
			></script>
			<button
				type="button"
				class="text-mono-800 py-2.5 px-5 text-center me-2 mt-12 text-xl focus:outline-none backdrop-blur-sm rounded-full border-2 border-mono-800 hover:bg-gray-100 hover:text-theme-900 focus:z-3 focus:ring-4 focus:ring-gray-100 w-[95%] md:max-w-[275px] h-14 transform transition-transform duration-300 ease-in-out hover:scale-105 font-semibold"
			>
				<a href="https://www.youtube.com/@emmanuelbaptistnc85/videos">View Past Sermons</a>
			</button>
		</div>
	</section>
	<!-- /**********/ EVENTS SECTION /**********/ -->
	<section id="events" class="w-screen">
		<div class="flex-col items-center mx-auto w-full text-center md:w-1/2 lg:w-2/3">
			<h2 class="mt-8 text-3xl font-bold text-mono-700 md:text-4xl">Upcoming Events</h2>
			<p class="px-4 my-8 text-mono-700">
				See what events are planned for the coming weeks. Join us as we grow in faith and fellowship
				together!
			</p>
		</div>
		<!-- EVENT DETAILS -->
		<div
			class="mx-4 md:mx-auto max-w-md md:max-h-[25rem] overflow-hidden rounded-xl border-2 bg-white shadow-none md:max-w-4xl my-12"
		>
			<div class="md:flex">
				<div class="shrink-0 py-0">
					<img
						loading="lazy"
						class="h-full w-full max-h-[25rem] object-cover"
						src="https://ik.imagekit.io/bip1v395ybp/Emmanuel%20Baptist%20Church/scott-pauley_zYX0B38cd.jpg?updatedAt=1739652942389"
						alt="Evangelist Scott Pauley Headshot"
					/>
				</div>
				<div class="px-6 py-4">
					<h3 class="text-sm font-semibold tracking-wide text-theme-700 my-4 uppercase">
						Coming Up
					</h3>
					<h4 class="mt-1 block text-lg leading-tight font-medium my-4 text-black">
						Spring Revival with Evangelist Scott Pauley
					</h4>
					<p class="mt-2 text-mono-500 text-base md:text-[0.9rem]">
						For nearly twenty years Scott Pauley served as an assistant pastor, college
						administrator, and Bible instructor. He now travels extensively as an evangelist across
						America and in several foreign countries. His passion is to preach the gospel, teach the
						Word of God, and reach this generation for Christ. Scott can be heard daily on the
						Enjoying the Journey podcast and radio program. He and his wife Tammy have been blessed
						with three children, Morgan, Lauren, and Grant and make their home in the mountains of
						West Virginia. Join us for revival services at Emmanuel Baptist Church in La Grange, NC
						from March 7th through 9th!
					</p>
				</div>
			</div>
		</div>
		<!-- CALENDAR COMPONENT -->
		<SmallCalendar />
	</section>
	<!-- /**********/ GIVE SECTION /**********/ -->
	<section id="give" class="items-center py-20 w-screen bg-sky-300">
		<div class="flex-col items-center mx-auto mb-16 w-screen text-center md:w-1/2 lg:w-2/3">
			<h2 class="mt-8 text-3xl font-bold text-mono-700 md:text-4xl">Giving</h2>
			<h3 class="my-8 text-2xl text-mono-700">Your obedience and generosity is changing lives.</h3>
			<p class="px-4 my-8 text-mono-700">
				Our church's mission is funded solely by the giving of her members and regular attenders. <br
				/>
				You can give by cash or check in any of our services or at our church office throughout the week.
			</p>
		</div>
		<div
			class="flex-col justify-center items-center mx-auto mb-16 space-y-8 w-full text-center md:w-1/3"
		>
			<h4 class="text-xl font-semibold text-center">Ways to give</h4>
			<div class="flex items-center p-6 rounded-lg border-2 border-mono-800">
				<div class="flex justify-center items-center p-2 w-10 h-10 bg-mono-800 rounded-full">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="w-6 h-6 text-white"
						width="auto"
						height="auto"
						viewBox="0 0 256 256"
					>
						<path
							fill="currentColor"
							d="M227.09 146.86L190 124.6V104a6 6 0 0 0-3-5.21l-53-30.27V46h18a6 6 0 0 0 0-12h-18V16a6 6 0 0 0-12 0v18h-18a6 6 0 0 0 0 12h18v22.52L69 98.79a6 6 0 0 0-3 5.21v20.6l-37.09 22.26A6 6 0 0 0 26 152v64a6 6 0 0 0 6 6h80a6 6 0 0 0 6-6v-48a10 10 0 0 1 20 0v48a6 6 0 0 0 6 6h80a6 6 0 0 0 6-6v-64a6 6 0 0 0-2.91-5.14M38 155.4l28-16.8V210H38Zm90-9.4a22 22 0 0 0-22 22v42H78V107.48l50-28.57l50 28.57V210h-28v-42a22 22 0 0 0-22-22m90 64h-28v-71.4l28 16.8Z"
						/>
					</svg>
				</div>
				<h2 class="ml-4 text-lg font-black md:text-2xl">On Campus</h2>
			</div>
			<div class="flex items-center p-6 rounded-lg border-2 border-mono-600">
				<div class="flex justify-center items-center p-2 w-10 h-10 bg-mono-600 rounded-full">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="w-6 h-6 text-white"
						width="24"
						height="24"
						viewBox="0 0 24 24"
					>
						<path
							fill="currentColor"
							d="M8 12h2a1 1 0 0 0 0-2H8a1 1 0 0 0 0 2m9-6h-5V4h1a1 1 0 0 0 0-2h-2a1 1 0 0 0-1 1v3H7a4 4 0 0 0-4 4v6a1 1 0 0 0 1 1h6v4a1 1 0 0 0 2 0v-4h8a1 1 0 0 0 1-1v-6a4 4 0 0 0-4-4m-4 4v5H5v-5a2 2 0 0 1 2-2h6.56a3.9 3.9 0 0 0-.56 2m6 5h-4v-5a2 2 0 0 1 4 0Z"
						/>
					</svg>
				</div>
				<h2 class="ml-4 text-2xl font-black text-mono-800">By Mail</h2>
			</div>
			<div class="flex items-center p-6 rounded-lg border-2 border-mono-400">
				<div class="flex justify-center items-center p-2 w-10 h-10 bg-mono-400 rounded-full">
					<svg
						class="w-6 h-6 text-black"
						xmlns="http://www.w3.org/2000/svg"
						width="16"
						height="16"
						viewBox="0 0 16 16"
					>
						<path
							fill="currentColor"
							d="M16 7.38A7.82 7.82 0 0 0 8 .5a7.82 7.82 0 0 0-8 6.88v1.24a7.82 7.82 0 0 0 8 6.88a7.82 7.82 0 0 0 8-6.88zm-1.25 0h-3a11.3 11.3 0 0 0-.43-2.54a7.6 7.6 0 0 0 1.75-1a6 6 0 0 1 1.65 3.54zm-9.18 0a9.7 9.7 0 0 1 .37-2.14A8.4 8.4 0 0 0 8 5.5a8.5 8.5 0 0 0 2.09-.26a10.2 10.2 0 0 1 .37 2.14zm4.92 1.24a9.6 9.6 0 0 1-.37 2.14a8.5 8.5 0 0 0-4.18 0a9.7 9.7 0 0 1-.37-2.14zm.4-5A12 12 0 0 0 10 2a6.9 6.9 0 0 1 2 1a6.6 6.6 0 0 1-1.14.66zm-2.6-1.86a10 10 0 0 1 1.38 2.3A7.6 7.6 0 0 1 8 4.25a7.6 7.6 0 0 1-1.67-.19a9.8 9.8 0 0 1 1.38-2.3zm-3.15 1.9A6.6 6.6 0 0 1 4 3a6.9 6.9 0 0 1 2-1a10.4 10.4 0 0 0-.86 1.66M3 3.83a7.6 7.6 0 0 0 1.75 1a11 11 0 0 0-.43 2.54h-3A6 6 0 0 1 3 3.83M1.28 8.62h3a11 11 0 0 0 .43 2.54a7.6 7.6 0 0 0-1.75 1a6 6 0 0 1-1.68-3.54m3.86 3.72A10.4 10.4 0 0 0 6 14a6.9 6.9 0 0 1-2-1a6.6 6.6 0 0 1 1.14-.66m2.57 1.9a9.8 9.8 0 0 1-1.38-2.3a7.4 7.4 0 0 1 3.34 0a9.8 9.8 0 0 1-1.38 2.3zm3.15-1.9a6.6 6.6 0 0 1 1.19.66a7.2 7.2 0 0 1-2 1a11.5 11.5 0 0 0 .81-1.66m2.14-.17a7.6 7.6 0 0 0-1.75-1a10.8 10.8 0 0 0 .43-2.54h3A6 6 0 0 1 13 12.17"
						/>
					</svg>
				</div>
				<h2 class="ml-4 text-2xl font-black text-mono-700">Online (Coming Soon)</h2>
			</div>
		</div>
	</section>
</div>
