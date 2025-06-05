<script lang="ts">
	import { Input, Label, Helper, Textarea, Button } from 'flowbite-svelte';

	// FORMSUBMIT, NUCLEUS GIVING, WEB3FORMS,
	// ASTRO: https://preview.tailus.io/astrolus-free/

	const ACCESS_KEY: string = '1c04b16d-a4be-488d-a296-6261812c7378';

	// Define a type for FAQ items
	type FAQ = {
		question: string;
		answer: string;
		icon: string;
	};

	// Define the array of FAQs using the FAQ type
	const faqs: FAQ[] = [
		{
			question: 'What time are your services?',
			answer: `We meet on Sunday morning for Bible study groups at 10:00 AM, 
               at 11:00 AM for congregational worship and Bible preaching, 
               and Wednesday evening at 7:00 PM for congregational Bible study and prayer.`,
			icon: `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
              <g fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2">
                <circle cx="12" cy="12" r="10" />
                <path d="M12 6v6l4 2" />
              </g>
            </svg>`
		},
		{
			question: "What's a typical church service like?",
			answer: `Our services last just over an hour and include congregational singing, Bible reading, special music, a practical message from the Bible, and a time to respond to the message`,
			icon: `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
              
	<path fill="currentColor" fill-rule="evenodd" d="M12 3a1 1 0 0 1 1 1v1h1a1 1 0 1 1 0 2h-1v1.5l7.6 5.7A1 1 0 0 1 20 16h-1v3h2a1 1 0 1 1 0 2h-7v-3a2 2 0 1 0-4 0v3H3a1 1 0 1 1 0-2h2v-3H4a1 1 0 0 1-.6-1.8L11 8.5V7h-1a1 1 0 0 1 0-2h1V4a1 1 0 0 1 1-1" clip-rule="evenodd" />
            </svg>`
		},
		{
			question: 'Are all your services the same?',
			answer: `Our Sunday 10:00 AM service focuses on small-group Bible study. The 11:00 AM and 6:30 PM Sunday services are distinct worship services, each featuring unique Bible preaching. On Wednesdays at 7:00 PM, we gather for a large-group Bible study and a time of communal prayer.`,
			icon: `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
              <path fill="currentColor" d="M13 3C9.23 3 6.19 5.95 6 9.66l-1.92 2.53c-.24.31 0 .81.42.81H6v3c0 1.11.89 2 2 2h1v3h7v-4.69c2.37-1.12 4-3.51 4-6.31c0-3.86-3.12-7-7-7m1 11h-2v-2h2zm1.75-5.19c-.29.4-.66.69-1.11.93c-.25.16-.42.33-.51.52c-.09.18-.13.43-.13.74h-2c0-.5.11-.92.31-1.18c.19-.27.54-.57 1.05-.91c.26-.16.47-.36.61-.59c.16-.23.23-.5.23-.82c0-.3-.08-.56-.26-.75c-.18-.18-.44-.28-.75-.28a1 1 0 0 0-.66.23c-.18.16-.27.39-.28.69h-1.93l-.01-.03c-.01-.79.25-1.36.77-1.77c.54-.39 1.24-.59 2.11-.59c.93 0 1.66.23 2.19.68c.54.45.81 1.06.81 1.82c0 .5-.15.91-.44 1.31" />
            </svg>`
		},
		{
			question: 'Am I expected to give an offering?',
			answer: `No, as our guest, we want our service to be a gift to you. While we believe the Bible teaches that the church should support itself financially, giving is a responsibility for our members and regular attenders—not our visitors.`,
			icon: `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
				<path fill="currentColor" d="M12 12.5a3.5 3.5 0 1 0 0 7a3.5 3.5 0 0 0 0-7M10.5 16a1.5 1.5 0 1 1 3 0a1.5 1.5 0 0 1-3 0" />
				<path fill="currentColor" d="M17.526 5.116L14.347.659L2.658 9.997L2.01 9.99V10H1.5v12h21V10h-.962l-1.914-5.599zM19.425 10H9.397l7.469-2.546l1.522-.487zM15.55 5.79L7.84 8.418l6.106-4.878zM3.5 18.169v-4.34A3 3 0 0 0 5.33 12h13.34a3 3 0 0 0 1.83 1.83v4.34A3 3 0 0 0 18.67 20H5.332A3.01 3.01 0 0 0 3.5 18.169" />
			</svg>`
		},
		{
			question: 'How should I dress?',
			answer: `Come as you are! There’s no dress code for visitors or members at EBC. While many of our ministry leaders and church family choose more traditional ‘Sunday’ attire, our priority is that you feel comfortable and welcome during your visit.`,
			icon: `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 512 512">
				<path fill="currentColor" d="M133.3 33.41L77.89 47.25L34.6 148.3l33.29 22.2l27.46-54.9l17.05 4.9l-15.07 150.1H245.2l9.2-87.9l.9-8.1h4.5l-5.4-54.1l17.1-4.9l27.4 54.9l33.3-22.2l-43.3-101.05l-55.4-13.84c-5.5 3.87-12.2 6.21-19.5 7.95c-9.4 2.21-20 3.24-30.6 3.24s-21.2-1.03-30.6-3.24c-7.3-1.74-14-4.07-19.5-7.95M271.5 192.6l-1.5 14h178.8l-1.5-14zm-3.4 32l-26.7 254h62.7l46.5-216.9h17.6l46.5 216.9h62.7l-26.7-254z" />
			</svg>`
		},
		{
			question: 'What your worship style?',
			answer: `Our church sings traditional hymns accompanied by piano and a church choir.`,
			icon: `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
				<path fill="currentColor" d="M18.5 5A1.5 1.5 0 1 1 17 6.5A1.5 1.5 0 0 1 18.5 5m0 6a1.5 1.5 0 1 1-1.5 1.5a1.5 1.5 0 0 1 1.5-1.5M10 4a5 5 0 0 0-5 5v1a2 2 0 1 0 2.18-2A3 3 0 0 1 10 6a4 4 0 0 1 4 4c0 3.59-2.23 6.19-7 8.2l.76 1.84C13.31 17.72 16 14.43 16 10a6 6 0 0 0-6-6" />
			</svg>`
		}
	];
</script>

<div id="main" class="flex overflow-x-hidden flex-col justify-center mt-0 grow min-h-80">
	<section
		class="data-[size=md]:scale-[0.8] data-[size=sm]:scale-75 w-screen relative z-10 ease-in-out flex transition-all duration-700 will-change-auto items-center flex-col"
	>
		<div class="relative flex-col items-center mb-20 max-w-8xl" id="home">
			<!-- GRADIENTS -->
			<div aria-hidden="true" class="grid absolute inset-0 grid-cols-2 -space-x-52 opacity-40">
				<div class="blur-[106px] h-56 bg-gradient-to-br from-theme-800 to-purple-400"></div>
				<div class="blur-[106px] h-32 bg-gradient-to-r from-cyan-400 to-sky-300"></div>
			</div>
			<!-- HERO SECTION -->
			<div class="flex-col items-center px-6 mx-auto w-full max-w-7xl md:px-12 xl:px-6">
				<div class="relative flex-col items-center pt-36 ml-auto">
					<div class="flex-col items-center mx-auto w-full text-center md:w-1/2 lg:w-2/3">
						<h1 class="text-5xl font-bold text-neutral-900 md:text-6xl xl:text-7xl">
							<div class="m-auto mt-6 space-y-6 md:w-8/12 lg:w-full">
								<h1 class="text-4xl font-black md:text-5xl">Plan Your Visit</h1>
							</div>
						</h1>

						<h3 class="mt-8 text-lg text-neutral-700">
							Welcome! We’re so glad you’re considering visiting our church. Our goal is to make
							your experience as smooth and spiritually uplifting as possible. To help with that,
							we’ve gathered answers to some of the most common questions right here. If you don’t
							find what you're looking for or simply want to connect, please don’t hesitate to reach
							out through the <a href="/plan-your-visit#form" class="underline">form below</a> — we’d
							love to hear from you!
						</h3>
					</div>
				</div>
			</div>
		</div>
		<div class="my-20 text-neutral-600 dark:text-neutral-300 max-w-8xl" id="faqs">
			<!-- <div class="px-6 mx-auto max-w-7xl md:px-12 xl:px-6">
				<div class="px-6 mb-20 space-y-4 md:px-0">
					<h2 class="text-2xl font-bold text-center text-neutral-800 dark:text-white md:text-4xl">
						Frequently Asked Questions
					</h2>
				</div>
				<div class="gap-8 space-y-8 md:columns-2 lg:columns-3">
					<div
						class="p-8 bg-white rounded-3xl border border-neutral-100 shadow-2xl aspect-auto dark:bg-neutral-800 dark:border-neutral-700 shadow-neutral-600/10 dark:shadow-none"
					>
						<div class="flex gap-4 items-center">
							<svg xmlns="http://www.w3.org/2000/svg" class="text-theme-400" width="24" height="24" viewBox="0 0 24 24">
								<g fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2">
									<circle cx="12" cy="12" r="10" />
									<path d="M12 6v6l4 2" />
								</g>
							</svg>
							<div>
								<h6 class="text-lg font-medium text-neutral-700 dark:text-white">
									What time are your services?
								</h6>
							</div>
						</div>
						<p class="mt-8">
							We meet on Sunday morning for Bible study groups at 10:00 AM, at 11:00 AM for congrational worship and Bible preaching, and Wednesday evening at 7:00 PM for congrational Bible study and prayer.
						</p>
					</div>
					<div
						class="p-8 bg-white rounded-3xl border border-neutral-100 shadow-2xl aspect-auto dark:bg-neutral-800 dark:border-neutral-700 shadow-neutral-600/10 dark:shadow-none"
					>
						<div class="flex gap-4 items-center">
							<svg xmlns="http://www.w3.org/2000/svg" class="text-theme-400" width="24" height="24" viewBox="0 0 24 24">
								<g fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2">
									<circle cx="12" cy="12" r="10" />
									<path d="M12 6v6l4 2" />
								</g>
							</svg>
							<div>
								<h6 class="text-lg font-medium text-neutral-700 dark:text-white">
									What's a typical church service like?
								</h6>
							</div>
						</div>
						<p class="mt-8">
							Our church services are a little over an hour long and include congregational singing, 
						</p>
					</div>
					<div
						class="p-8 bg-white rounded-3xl border border-neutral-100 shadow-2xl aspect-auto dark:bg-neutral-800 dark:border-neutral-700 shadow-neutral-600/10 dark:shadow-none"
					>
						<div class="flex gap-4 items-center">
							<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
								<path fill="currentColor" d="M13 3C9.23 3 6.19 5.95 6 9.66l-1.92 2.53c-.24.31 0 .81.42.81H6v3c0 1.11.89 2 2 2h1v3h7v-4.69c2.37-1.12 4-3.51 4-6.31c0-3.86-3.12-7-7-7m1 11h-2v-2h2zm1.75-5.19c-.29.4-.66.69-1.11.93c-.25.16-.42.33-.51.52c-.09.18-.13.43-.13.74h-2c0-.5.11-.92.31-1.18c.19-.27.54-.57 1.05-.91c.26-.16.47-.36.61-.59c.16-.23.23-.5.23-.82c0-.3-.08-.56-.26-.75c-.18-.18-.44-.28-.75-.28a1 1 0 0 0-.66.23c-.18.16-.27.39-.28.69h-1.93l-.01-.03c-.01-.79.25-1.36.77-1.77c.54-.39 1.24-.59 2.11-.59c.93 0 1.66.23 2.19.68c.54.45.81 1.06.81 1.82c0 .5-.15.91-.44 1.31" />
							</svg>
							<div>
								<h6 class="text-lg font-medium text-neutral-700 dark:text-white">Are all your services the same?</h6>
							</div>
						</div>
						<p class="mt-8">
							We meet Sunday mornings at 10:00 AM and 11:00 AM, Sunday evenings at 6:30 PM and Wednesday evenings at 7:00 PM. Throughout the year we have additional services that may occur throught the week.
						</p>
					</div>
				
				</div>
			</div> -->
			<div class="px-6 mx-auto max-w-7xl md:px-12 xl:px-6">
				<div class="px-6 mb-20 space-y-4 md:px-0">
					<h2 class="text-2xl font-bold text-center text-neutral-800 dark:text-white md:text-4xl">
						Frequently Asked Questions
					</h2>
				</div>
				<div class="gap-8 space-y-8 md:columns-2 lg:columns-3">
					{#each faqs as { question, answer, icon }}
						<div
							class="p-8 bg-white rounded-3xl border border-neutral-100 shadow-2xl aspect-auto dark:bg-neutral-800 dark:border-neutral-700 shadow-neutral-600/10 dark:shadow-none"
						>
							<div class="flex gap-4 items-center">
								<span class="p-3 text-white rounded-full bg-theme-600">{@html icon}</span>

								<div>
									<h6 class="text-lg font-medium text-neutral-700 dark:text-white">{question}</h6>
								</div>
							</div>
							<p class="mt-8">{answer}</p>
						</div>
					{/each}
				</div>
			</div>
		</div>
	</section>
	<section id="form" class="p-4 mx-auto mb-20 max-w-2xl">
		<div class="flex-col items-center px-6 mx-auto w-full max-w-7xl md:px-12 xl:px-6">
			<div class="relative flex-col items-center pt-36 ml-auto">
				<div class="flex-col items-center mx-auto w-full text-center md:w-1/2 lg:w-2/3">
					<h2 class="text-2xl font-bold text-center text-neutral-800 dark:text-white md:text-4xl">
						Reach Out Directly
					</h2>
					<h3 class="mt-8 mb-20 text-lg text-neutral-700">
						Visiting a new church can feel intimidating, but we’re here to help you feel at home.
						Use the form below to ask us anything!
					</h3>
				</div>
			</div>
		</div>
		<form class="mx-auto max-w-xl" action="https://api.web3forms.com/submit" method="POST">
			<input type="hidden" name="subject" value="New Submission from EBC Contact Form" />
			<input type="hidden" name="access_key" value={ACCESS_KEY} />
			<div class="mb-5">
				<Label class="space-y-2">
					<span class="capitalize">Your Name*</span>
					<Input type="name" placeholder="First Last" size="lg" required />
				</Label>
			</div>
			<div class="mb-5">
				<Label class="space-y-2">
					<span class="capitalize">Your email address*</span>
					<Input type="email" placeholder="name@provider.com" size="lg" required>
						<!-- <EnvelopeSolid slot="right" class="w-5 h-5" /> -->
					</Input>
				</Label>
			</div>
			<div class="mb-5">
				<Label for="textarea-id" class="mb-2 capitalize">Your question/comment*</Label>
				<!-- <Textarea id="textarea-id" placeholder="Your message/question" rows="4" name="message" class="p-2" required /> -->
				<Textarea
					class="mb-4"
					id="textarea-id"
					name="message"
					rows="4"
					placeholder="Do you have visitor parking?"
				>
					<div slot="footer" class="flex justify-between items-center">
						<Helper class="text-sm text-neutral-600">
							We’ll never share your details. Read our <a
								href="/legal#privacy-policy"
								class="font-medium text-theme-600 hover:underline dark:text-theme-500"
							>
								Privacy Policy
							</a>
							.
						</Helper>
					</div>
				</Textarea>
			</div>
			<input type="checkbox" name="botcheck" class="hidden" style="display: none;" />
			<button
				type="submit"
				class="text-white rounded-full text-md md:text-lg py-2.5 px-6 text-center me-2 w-[95%] md:max-w-[300px] h-14 bg-theme-900 font-heading-medium focus:outline-none focus:ring-4 focus:ring-blue-300 transform transition-transform duration-300 ease-in-out hover:scale-105 hover:bg-gradient-to-tr hover:from-blue-600 hover:to-cyan-500 hover:text-white justify-center"
			>
				Send Question/Comment
			</button>
		</form>
	</section>
</div>
