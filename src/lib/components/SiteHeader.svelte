<script lang="ts">
  import { isMenuOpen, toggleMenu, closeMenu } from '$lib/stores/nav.store';
  import { get } from 'svelte/store';
  export let class: string = '';

  // If you want these links reusable:
  const links = [
    { href: '/#discover', label: 'Discover' },
    { href: '/#media',    label: 'Media' },
    { href: '/#events',   label: 'Events' },
    { href: '/#give',     label: 'Give' }
  ];
</script>

<nav class={`w-full border-b border-black/5 lg:border-transparent ${class}`}>
  <div class="container-content">
    <div class="flex items-center justify-between py-3 md:py-4">
      <!-- Logo -->
      <a href="/#home" class="flex items-center h-12">
        <img
          src="https://ik.imagekit.io/bip1v395ybp/Emmanuel%20Baptist%20Church/ebc-logo-new-large_WrsHKgywk.png?updatedAt=1730625294622"
          alt="logo"
          class="w-11 h-11"
        />
        <!-- Inline SVG kept; consider extracting to a separate component -->
        <svg class="h-12 w-auto text-neutral-900 md:ml-2 p-1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 204 57" fill="none" aria-hidden="true">
          <!-- ... your existing <path> nodes unchanged ... -->
        </svg>
      </a>

      <!-- Desktop Nav -->
      <ul class="hidden lg:flex gap-1 text-neutral-700 dark:text-neutral-200 font-extralight">
        {#each links as l}
          <li>
            <a href={l.href}
               class="block px-3 py-2 relative hover:text-blue-900 after:content-[''] after:absolute after:left-0 after:bottom-0 after:h-[2px] after:w-full after:bg-blue-900 after:rounded-md after:scale-x-0 hover:after:scale-x-100 after:translate-y-2 after:transition-transform after:duration-300">
              {l.label}
            </a>
          </li>
        {/each}
      </ul>

      <!-- Mobile Hamburger -->
      <button
        aria-label="Open menu"
        class="lg:hidden p-4"
        on:click={toggleMenu}>
        <div class="w-5 h-0.5 bg-sky-900 rounded transition-transform"
             class:rotate-45={$isMenuOpen}
             class:translate-y-[4px]={$isMenuOpen}
             class:bg-amber-400={$isMenuOpen} />
        <div class="w-5 h-0.5 bg-sky-900 rounded mt-2 transition-transform"
             class:rotate-[-45deg]={$isMenuOpen}
             class:-translate-y-[6px]={$isMenuOpen}
             class:bg-amber-400={$isMenuOpen} />
      </button>
    </div>
  </div>

  <!-- Mobile Overlay Layer -->
  <div
    aria-hidden="true"
    class="fixed inset-0 z-10 backdrop-blur-2xl transition duration-300 lg:hidden"
    class:scale-y-100={$isMenuOpen}
    class:scale-y-0={!$isMenuOpen}
    class:bg-white/70
    on:click={closeMenu}
  />

  <!-- Mobile Drawer -->
  <div class={`absolute left-0 top-full z-20 w-full lg:hidden transition-all duration-300
               ${get(isMenuOpen) ? 'opacity-100 translate-y-0' : 'opacity-0 -translate-y-1 pointer-events-none'}`}>
    <div class="container-content">
      <div class="rounded-3xl border border-neutral-100 bg-white p-8 shadow-2xl dark:border-neutral-700 dark:bg-neutral-800">
        <ul class="flex flex-col gap-6">
          {#each links as l}
            <li>
              <a href={l.href} on:click={closeMenu} class="block hover:text-blue-900">
                {l.label}
              </a>
            </li>
          {/each}
        </ul>
      </div>
    </div>
  </div>
</nav>
