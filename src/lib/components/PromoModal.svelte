<script lang="ts">
	import { Modal } from 'flowbite-svelte';

	// parent controls this via bind:open
	export let open = false;

	// content inputs (UI only; no date logic here)
	export let heading = '';
	export let dateISO: string | undefined;
	export let body: string[] = [];

	// optional direct file video (CDN)
	export let videoSrc: string | undefined;
	export let poster: string | undefined;

	// CTAs
	export let primaryCta: { href: string; label: string; external?: boolean } | undefined;
	export let secondaryCta: { href: string; label: string; external?: boolean } | undefined;
</script>

<Modal
	bind:open
	placement="center"
	position="center"
	outsideClose
	backdrop={true}
	backdropClass="fixed inset-0 bg-black/60 z-[40]"
	class="z-[50] flex !items-center !justify-center"
>
	<h2
		slot="header"
		class="flex items-center justify-center gap-4 text-xl font-bold text-neutral-700 grow-1 pt-2"
	>
		<span>
			{heading}
			{#if dateISO}
				<time datetime={dateISO} class="ml-2 whitespace-nowrap">
					{new Date(dateISO).toLocaleDateString(undefined, {
						weekday: 'short',
						month: 'short',
						day: 'numeric'
					})}
				</time>
			{/if}
		</span>
		<span class="mr-32"></span>
	</h2>

	<div class="space-y-4">
		{#if videoSrc}
			<div class="aspect-video w-full overflow-hidden rounded-2xl">
				<!-- svelte-ignore a11y-media-has-caption -->
				<video class="h-full w-full object-cover" playsinline preload="metadata" {poster} autoplay>
					<source src={videoSrc} type="video/mp4" />
				</video>
			</div>
		{/if}

		{#each body as p}
			<p class="text-neutral-700 text-center">{p}</p>
		{/each}
	</div>

	<div slot="footer" class="flex gap-3">
		{#if primaryCta}
			<a
				href={primaryCta.href}
				target={primaryCta.external ? '_blank' : undefined}
				rel={primaryCta.external ? 'noopener noreferrer' : undefined}
				class="inline-flex items-center justify-center px-6 py-2 font-medium text-black bg-yellow-300 hover:bg-yellow-200 rounded-3xl"
				on:click={() => (open = false)}
			>
				{primaryCta.label}
			</a>
		{/if}

		{#if secondaryCta}
			<a
				href={secondaryCta.href}
				target={secondaryCta.external ? '_blank' : undefined}
				rel={secondaryCta.external ? 'noopener noreferrer' : undefined}
				class="inline-flex items-center justify-center rounded-3xl px-6 py-2 font-medium text-neutral-700 bg-neutral-100 hover:bg-neutral-200"
				on:click={() => (open = false)}
			>
				{secondaryCta.label}
			</a>
		{/if}
	</div>
</Modal>
