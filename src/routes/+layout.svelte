<script lang="ts">
  import { page } from '$app/stores';
  let menuOpen = false;

  const links = [
    { href: "/", label: "Domů" },
    { href: "/about", label: "O aplikaci" },
    { href: "/settings", label: "Nastavení" }
  ];
</script>

<div class="min-h-screen w-full bg-[#1e3a8a]"><nav class="sticky top-0 bg-white/80 backdrop-blur shadow z-50">
  <div class="w-full px-4 py-4 flex items-center justify-between">

    <!-- Logo -->
    <a href="/" class="text-2xl font-bold text-blue-600">
      Grow
    </a>

    <!-- Desktop menu -->
    <div class="hidden md:flex gap-6 text-lg">
      {#each links as link}
        <a 
          href={link.href}
          class="pb-1 border-b-2 transition
                 { $page.url.pathname === link.href
                   ? 'border-blue-600 text-blue-600'
                   : 'border-transparent text-gray-700 hover:border-gray-300' }"
        >
          {link.label}
        </a>
      {/each}
    </div>

    <!-- Hamburger -->
    <!-- svelte-ignore a11y_consider_explicit_label -->
    <button class="md:hidden" on:click={() => (menuOpen = !menuOpen)}>
      <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
           stroke-width="1.5" stroke="currentColor" class="w-8 h-8">
        <path stroke-linecap="round" stroke-linejoin="round"
          d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
      </svg>
    </button>

  </div>

  <!-- Mobilní menu -->
  {#if menuOpen}
    <div class="md:hidden bg-white shadow-inner flex flex-col p-4 text-lg space-y-4">
      {#each links as link}
        <a 
          href={link.href}
          class="pb-1 border-b-2 transition
                 { $page.url.pathname === link.href
                   ? 'border-blue-600 text-blue-600'
                   : 'border-transparent text-gray-700 hover:border-gray-300' }"
          on:click={() => (menuOpen = false)}
        >
          {link.label}
        </a>
      {/each}
    </div>
  {/if}
</nav>

<!-- Obsah stránek -->
<main class="w-full px-4 py-8">
  <slot />
</main></div>
