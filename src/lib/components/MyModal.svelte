<script lang="ts">
  import { onMount, tick } from 'svelte';

  // --- Props and State ---
  export let open = false;
  export let heading = '';
  export let body: string | string[] = [];
  export let primaryCta: { href: string; label: string; external?: boolean } | undefined;
  export let triggerElement: HTMLElement | null = null; 

  const close = () => (open = false);
  const ext = (c?: { external?: boolean }) => (c?.external ? '_blank' : undefined);
  const rel = (c?: { external?: boolean }) => (c?.external ? 'noopener noreferrer' : undefined);

  $: lines = Array.isArray(body) ? body : body ? [body] : [];

  // --- DOM References for Focus Management ---
  let closeButton: HTMLButtonElement;
  let modalDialogElement: HTMLDivElement;

  // --- Focus Management Logic ---
  $: if (open) {
    tick().then(() => {
      closeButton?.focus();
    });
  }

  $: if (!open) {
    requestAnimationFrame(() => {
      if (triggerElement) {
        triggerElement.focus();
        triggerElement = null; 
      }
    });
  }

  function onBackdrop(e: MouseEvent) {
    if (e.target === e.currentTarget) close();
  }

  function handleKeydown(e: KeyboardEvent) {
    if (e.key === 'Escape') {
      close();
      return;
    }
    
    if (e.key === 'Tab' && modalDialogElement) {
      const focusableElements = Array.from(
        modalDialogElement.querySelectorAll(
          'a[href], button, input, textarea, select, details, [tabindex]:not([tabindex="-1"])'
        )
      ).filter((el: Element) => !el.hasAttribute('disabled'));

      const first = focusableElements[0] as HTMLElement;
      const last = focusableElements[focusableElements.length - 1] as HTMLElement;

      if (e.shiftKey) {
        if (document.activeElement === first) {
          last.focus();
          e.preventDefault();
        }
      } else {
        if (document.activeElement === last) {
          first.focus();
          e.preventDefault();
        }
      }
    }
  }

  // --- Confetti Logic (unchanged) ---
  let confetti: any = null;
  let hasFired = false;

  onMount(async () => {
    const mod = await import('canvas-confetti');
    confetti = mod.default;
    if (open) fireConfettiOnce();
  });

  $: if (!open) hasFired = false;
  $: if (open && confetti && !hasFired) fireConfettiOnce();

  function fireConfettiOnce() {
    if (!confetti || window.matchMedia('(prefers-reduced-motion: reduce)').matches) return;
    hasFired = true;
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

{#if open}
  <div 
    class="fixed inset-0 z-[60]" 
    on:click={onBackdrop} 
    on:keydown={handleKeydown}
    role="presentation"
    tabindex="-1"
  >
    <div class="absolute inset-0 bg-black/60 backdrop-blur-[2px]"></div>

    <div class="relative mx-auto flex min-h-screen items-center justify-center p-4">
      <div
        bind:this={modalDialogElement}
        role="dialog"
        aria-modal="true"
        aria-labelledby="promo-title"
        class="relative w-full max-w-md overflow-hidden rounded-3xl bg-white shadow-[0_6px_24px_rgba(0,0,0,.15)]"
      >
        <div class="relative w-full h-44 sm:h-52">
          <img
            src="https://ik.imagekit.io/bip1v395ybp/Emmanuel%20Baptist%20Church/mini-ebc-building_41eFlI4MT.webp?updatedAt=1729401487644"
            alt="" aria-hidden="true" loading="lazy"
            class="absolute inset-0 h-full w-full object-cover object-center"
          />

          <div class="absolute inset-0 bg-gradient-to-br from-blue-400/60 via-blue-300/30 to-blue-200/10"></div>
          <div
            class="pointer-events-none absolute inset-0 bg-[radial-gradient(120px_60px_at_30%_15%,rgba(255,255,255,.7),transparent_60%),radial-gradient(160px_80px_at_80%_0%,rgba(255,255,255,.6),transparent_60%)] opacity-70"
          ></div>

          <button
            bind:this={closeButton}
            aria-label="Close"
            on:click={close}
            class="absolute right-3 top-3 rounded-xl bg-white/80 p-2 text-blue-700 ring-1 ring-blue-200 backdrop-blur hover:bg-white focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-blue-400"
          >
            <svg class="h-4 w-4" viewBox="0 0 14 14" fill="none" aria-hidden="true">
              <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                    d="m1 1 6 6m0 0 6 6M7 7l6-6M7 7l-6 6" />
            </svg>
          </button>
        </div>

        <div class="px-6 py-12 text-center space-y-4">
          <h2 id="promo-title" class="text-2xl font-semibold text-blue-900 capitalize">{heading}</h2>

          {#if lines.length}
            <p class="mx-auto mt-2 max-w-xs text-lg leading-7 text-blue-900/90">
              {#each lines as p, i}
                <span>{p}{i < lines.length - 1 ? ' ' : ''}</span>
              {/each}
            </p>
          {/if}

          {#if primaryCta}
            <a
              href={primaryCta.href}
              target={ext(primaryCta)}
              rel={rel(primaryCta)}
              class="mt-5 inline-flex items-center justify-center rounded-full bg-blue-600 px-12 py-3 text-lg font-semibold text-white transition hover:bg-blue-700 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-blue-400 capitalize"
              on:click={close}
            >{primaryCta.label}</a>
          {/if}
        </div>
      </div>
    </div>
  </div>
{/if}