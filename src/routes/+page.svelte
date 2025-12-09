<script lang="ts">
  // homepage nemá logiku, jen jednoduchý obsah
</script>

<div class="w-full flex justify-center px-4 py-16">
  <div class="w-full max-w-5xl text-center">

    <!-- HLAVNÍ NADPIS -->
    <h1 class="text-5xl font-extrabold text-gray-50 drop-shadow-md text-center mt-20 mb-2">
      Vítejte
    </h1>
    <p class="text-xl text-gray-200 text-center mb-12">
      Objevte něco o mně a podívejte se na moje projekty
    </p>

    <!-- DLAŽDICE -->
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mt-16">

      <!-- KDO JSEM -->
      <a href="/about" class="bg-white shadow-xl rounded-2xl p-10 hover:shadow-2xl transition border border-gray-100 flex flex-col items-center">
        <div class="text-6xl mb-4">👤</div>
        <h2 class="text-3xl font-semibold text-gray-900 mb-2">Kdo jsem</h2>
        <p class="text-gray-600">Zjistěte více o mé cestě, zkušenostech a dovednostech.</p>
      </a>

      <!-- PROJEKTY / APPKY -->
      <a href="/apps" class="bg-white shadow-xl rounded-2xl p-10 hover:shadow-2xl transition border border-gray-100 flex flex-col items-center">
        <div class="text-6xl mb-4">💡</div>
        <h2 class="text-3xl font-semibold text-gray-900 mb-2">Projekty</h2>
        <p class="text-gray-600">Podívejte se na moje aplikace a experimenty ve SvelteKitu.</p>
      </a>

    </div>

  </div>
</div>
