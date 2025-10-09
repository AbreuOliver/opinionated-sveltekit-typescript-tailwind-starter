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
			question: 'What is your worship style?',
			answer: `Our church sings traditional hymns accompanied by piano and a church choir.`,
			icon: `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
				<path fill="currentColor" d="M18.5 5A1.5 1.5 0 1 1 17 6.5A1.5 1.5 0 0 1 18.5 5m0 6a1.5 1.5 0 1 1-1.5 1.5a1.5 1.5 0 0 1 1.5-1.5M10 4a5 5 0 0 0-5 5v1a2 2 0 1 0 2.18-2A3 3 0 0 1 10 6a4 4 0 0 1 4 4c0 3.59-2.23 6.19-7 8.2l.76 1.84C13.31 17.72 16 14.43 16 10a6 6 0 0 0-6-6" />
			</svg>`
		}
	];
</script>

<div id="main" class="relative grow pt-10 sm:pt-12 overflow-x-hidden">
	<!-- Page background -->
	<div
		aria-hidden="true"
		class="absolute inset-0 -z-10 bg-gradient-to-br from-sky-50 via-sky-50 to-white"
	></div>
	<!-- soft blobs -->
	<div aria-hidden="true" class="pointer-events-none absolute inset-0 -z-10 opacity-40">
		<div
			class="absolute left-[-10%] top-10 h-48 w-80 blur-[106px] bg-gradient-to-br from-sky-200 to-sky-300"
		></div>
		<div
			class="absolute right-[-6%] top-28 h-36 w-72 blur-[106px] bg-gradient-to-r from-sky-200 to-sky-100"
		></div>
	</div>

	<!-- HERO -->
	<section class="w-full pb-20">
		<div class="mx-auto max-w-7xl px-6 md:px-12 xl:px-6">
			<div class="mx-auto mt-6 text-center">
				<h1 class="py-8 text-4xl font-extrabold text-zinc-900 md:text-5xl">Plan Your Visit</h1>

				<p class="mx-auto max-w-3xl text-lg leading-7 text-zinc-700">
					Welcome! We’re so glad you’re considering visiting our church. Our goal is to make your
					experience as smooth and spiritually uplifting as possible. We’ve gathered answers to
					common questions below. If you don’t find what you need, <a
						href="/plan-your-visit#form"
						class="underline decoration-sky-400 underline-offset-2">reach out with the form</a
					> — we’d love to hear from you!
				</p>
			</div>
		</div>
	</section>

	<!-- FAQS -->
	<section id="faqs" class="w-full">
		<div class="mx-auto max-w-7xl px-6 md:px-12 xl:px-6">
			<div class="mt-16 text-center">
				<h2 class="text-3xl font-bold text-zinc-900 md:text-4xl pb-12">
					Frequently Asked Questions
				</h2>
			</div>

			<div class="mt-10 grid gap-6 sm:gap-8 sm:grid-cols-2 lg:grid-cols-3">
				{#each faqs as { question, answer, icon }}
					<article
						class="rounded-xl border border-zinc-200 bg-white p-8 shadow-sm transition hover:-translate-y-0.5 hover:shadow-md focus-within:ring-2 focus-within:ring-sky-300"
					>
						<div class="flex justify-evenly items-center gap-4">
							<span
								class="inline-flex p-2 w-12 items-center justify-center rounded-full bg-sky-600 grow-1 text-white"
							>
								{@html icon}
							</span>
							<h3 class="text-lg font-semibold text-zinc-900 grow">{question}</h3>
						</div>
						<p class="mt-6 text-zinc-700">{answer}</p>
					</article>
				{/each}
			</div>
		</div>
	</section>

	<!-- CONTACT FORM -->
	<section id="form" class="w-full pt-12">
		<div class="mx-auto max-w-7xl px-6 md:px-12 xl:px-6 pb-20">
			<div class="mt-20 text-center">
				<h2 class="text-3xl font-bold text-zinc-900 md:text-4xl">Reach Out Directly</h2>
				<p class="mx-auto mt-6 max-w-2xl text-lg text-zinc-700">
					Visiting a new church can feel intimidating, but we’re here to help you feel at home. Use
					the form below to ask us anything!
				</p>
			</div>

			<div
				class="mx-auto mt-10 max-w-2xl rounded-xl border border-zinc-200 bg-white p-6 sm:p-8 shadow-sm"
			>
				<form class="mx-auto max-w-xl" action="https://api.web3forms.com/submit" method="POST">
					<input type="hidden" name="subject" value="New Submission from EBC Contact Form" />
					<input type="hidden" name="access_key" value={ACCESS_KEY} />

					<!-- Name -->
					<Label class="space-y-2 pb-4">
						<span class="capitalize text-zinc-900">Your Name*</span>
						<Input
							type="text"
							placeholder="First Last"
							required
							class="appearance-none h-12 md:h-14 w-full rounded-xl border border-zinc-300 px-4
           text-base leading-6 placeholder:text-zinc-400
           focus:border-sky-400 focus:outline-none focus:ring-2 focus:ring-sky-300"
						/>
					</Label>

					<!-- Email -->
					<Label class="space-y-2 pb-4">
						<span class="capitalize text-zinc-900">Your Email Address*</span>
						<Input
							type="email"
							placeholder="name@provider.com"
							required
							class="appearance-none h-12 md:h-14 w-full rounded-xl border border-zinc-300 px-4
           text-base leading-6 placeholder:text-zinc-400 focus:border-sky-400 focus:outline-none focus:ring-2 focus:ring-sky-300"
						/>
					</Label>

					<!-- Message -->
					<Label for="message" class="mb-2 capitalize text-zinc-900">Your Question/Comment*</Label>

					<!-- Wrapper handles border/ring; footer stays attached -->
					<div
						class="group overflow-hidden rounded-xl border border-zinc-300
         focus-within:border-sky-400 focus-within:ring-2 focus-within:ring-sky-300"
					>
						<textarea
							id="message"
							name="message"
							required
							placeholder="Do you have visitor parking?"
							aria-describedby="message-help"
							class="block w-full resize-y min-h-[9.5rem] border-0 rounded-none
           px-4 py-3 text-[16px] leading-6 placeholder:text-zinc-400
           focus:outline-none focus:ring-0"
						></textarea>

						<div id="message-help" class="border-t bg-zinc-50 px-4 py-2 text-sm text-zinc-600">
							We’ll never share your details. Read our
							<a href="/legal#privacy-policy" class="font-medium text-sky-700 hover:underline">
								Privacy Policy
							</a>.
						</div>
					</div>

					<input type="checkbox" name="botcheck" class="hidden" style="display: none;" />

					<button
						type="submit"
						class="inline-flex h-14 md:w-1/2 items-center justify-center rounded-full bg-sky-600 px-6 text-base font-semibold text-white shadow-sm transition hover:bg-sky-700 w-full focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-sky-300 md:h-14 mt-6"
					>
						Send Question/Comment
					</button>
				</form>
			</div>
		</div>
	</section>
</div>
