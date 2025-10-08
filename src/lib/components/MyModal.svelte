<script lang="ts">
  import { onMount } from 'svelte';

  // visibility controlled by parent: bind:open
  export let open = false;

  // content
  export let heading = '';
  export let dateISO: string | undefined;
  export let body: string | string[] = [];

  // optional media
  export let videoSrc: string | undefined;
  export let poster: string | undefined;

  // NEW: optional image (e.g., church photo)
  export let imageSrc: string | undefined;
  export let imageAlt: string = 'Church photo';
  export let badgeText: string | undefined; // e.g., '40 Years'

  // CTAs (kept for future use; commented markup below if needed)
  export let primaryCta:
    | { href: string; label: string; external?: boolean }
    | undefined;
  export let secondaryCta:
    | { href: string; label: string; external?: boolean }
    | undefined;

  const close = () => (open = false);

  // copy handling
  $: lines = Array.isArray(body) ? body : body ? [body] : [];

  // backdrop close
  function onBackdrop(e: MouseEvent) {
    if (e.target === e.currentTarget) close();
  }

  // --- Confetti (lazy loaded; respects reduced motion) ---
  let confetti: any = null;
  let hasFired = false;

  onMount(async () => {
    // only load in the browser
    const mod = await import('canvas-confetti');
    confetti = mod.default;
    if (open) fireConfettiOnce();
  });

  $: if (!open) hasFired = false;
  $: if (open && confetti && !hasFired) fireConfettiOnce();

  function fireConfettiOnce() {
    if (!confetti || window.matchMedia('(prefers-reduced-motion: reduce)').matches) return;
    hasFired = true;

    // two side bursts + a short flutter stream
    confetti({ particleCount: 70, angle: 60, spread: 55, origin: { x: 0, y: 0.2 } });
    confetti({ particleCount: 70, angle: 120, spread: 55, origin: { x: 1, y: 0.2 } });

    const end = Date.now() + 600;
    (function frame() {
      confetti({
        particleCount: 20,
        startVelocity: 45,
        spread: 70,
        ticks: 120,
        scalar: 0.9,
        origin: { y: 0.2 }
      });
      if (Date.now() < end) requestAnimationFrame(frame);
    })();
  }
</script>

<svelte:window on:keydown={(e) => e.key === 'Escape' && open && (open = false)} />

{#if open}
  <!-- svelte-ignore a11y-no-static-element-interactions -->
  <div class="fixed inset-0 z-[60]" on:click={onBackdrop}>
    <!-- Backdrop -->
    <div class="absolute inset-0 bg-black/60 backdrop-blur-[2px]"></div>

    <!-- Dialog -->
    <div class="relative mx-auto flex min-h-screen items-center justify-center p-4">
      <div
        role="dialog"
        aria-modal="true"
        aria-labelledby="promo-title"
        class="w-full max-w-lg rounded-2xl border border-zinc-200 bg-white shadow-xl"
      >
        <!-- Image / Video card top -->
        {#if videoSrc}
          <div class="aspect-[16/9] w-full overflow-hidden rounded-t-2xl">
            <!-- svelte-ignore a11y-media-has-caption -->
            <video class="h-full w-full object-cover" playsinline preload="metadata" {poster} muted autoplay>
              <source src={videoSrc} type="video/mp4" />
            </video>
          </div>
        {:else if imageSrc}
          <div class="relative aspect-[16/9] w-full overflow-hidden rounded-t-2xl">
            <img src={imageSrc} alt={imageAlt} class="h-full w-full object-cover" />
            {#if badgeText}
              <div
                class="absolute left-3 top-3 rounded-full bg-white/90 px-3 py-1 text-xs font-semibold text-amber-700 ring-1 ring-amber-300"
              >
                {badgeText}
              </div>
            {/if}
          </div>
        {/if}

        <!-- Body -->
        <div class="px-6 py-6 sm:px-8">
          <!-- Header row -->
          <div class="flex items-start justify-between gap-4">
            <h2 id="promo-title" class="text-lg sm:text-xl font-bold text-zinc-900">
              {heading}
              {#if dateISO}
                <time datetime={dateISO} class="ml-2 whitespace-nowrap text-sm text-zinc-500">
                  {new Date(dateISO).toLocaleDateString(undefined, {
                    weekday: 'short',
                    month: 'short',
                    day: 'numeric'
                  })}
                </time>
              {/if}
            </h2>

            <button
              aria-label="Close"
              on:click={close}
              class="rounded-full p-2 text-zinc-500 hover:bg-zinc-100 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-sky-300"
            >
              <svg class="h-4 w-4" viewBox="0 0 14 14" fill="none" aria-hidden="true">
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

          {#if lines.length}
            <div class="mt-3 space-y-3">
              {#each lines as p}
                <p class="text-center text-zinc-700">{p}</p>
              {/each}
            </div>
          {/if}

          <!-- Actions (optional) -->
          <!--
          <div class="mt-6 flex flex-wrap items-center justify-center gap-3">
            {#if primaryCta}
              <a
                href={primaryCta.href}
                target={primaryCta.external ? '_blank' : undefined}
                rel={primaryCta.external ? 'noopener noreferrer' : undefined}
                class="inline-flex h-11 items-center justify-center rounded-full bg-sky-600 px-6 text-sm font-semibold text-white shadow-sm hover:bg-sky-700 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-sky-300"
                on:click={close}
                >{primaryCta.label}</a
              >
            {/if}
            {#if secondaryCta}
              <a
                href={secondaryCta.href}
                target={secondaryCta.external ? '_blank' : undefined}
                rel={secondaryCta.external ? 'noopener noreferrer' : undefined}
                class="inline-flex h-11 items-center justify-center rounded-full border border-zinc-300 bg-white px-6 text-sm font-semibold text-zinc-900 hover:bg-zinc-50 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-sky-300"
                on:click={close}
                >{secondaryCta.label}</a
              >
            {/if}
          </div>
          -->
        </div>
      </div>
    </div>
  </div>
{/if}
