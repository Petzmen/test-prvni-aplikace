<script lang="ts">
  let lastPick: string | null = null;
  let selectedCategory: string | null = null;

  const challenges: Record<string, string[]> = {
    discipline: [
      "Udělej tolik dřepů, kolik zvládneš",
      "Udělej co nejdelší plank",
      "60 minut režim letadlo",
      "Začti se do knihy aspoň 30 minut",
      "Udělěj 10 kliků",
      "Napiš jednu věc, kterou odkládáš a proč",
      "Na 30 vteřin zavři oči a soustřeď se na dech",
      "Udělej jednu věc, kterou odkládáš"
    ],
    mindset: [
      "Napiš jednu věc, za kterou jsi vděčný",
      "Napiš dnešní afirmaci",
      "Napiš, co dnes uděláš pro svůj růst",
      "Napiš někomu něco pěkného",
      "Napiš, za koho si v životě vděčný a proč",
      "Napiš jednu věc, které chceš dosáhnout"
    ],
    energie: [
      "10 hlubokých nádechů",
      "Na 3O sekund ponoř tvář do studené vody",
    ],
    klid: [
      "Sleduj jeden objekt minutu a pak ho detailně popiš",
      "Soustřeď se 1 minutu na zvuky kolem",
      "Zavři oči a medituj aspoň 5 minut"
    ],
    sebevedomi: [
      "30 sekund pozice superhrdiny",
      "Napiš jednu věc, ve které jsi dobrý",
      "Řekni nahlas 3x: Jsem schopný a silný"
    ],
  };

  function pickCard() {
    if (!selectedCategory) return "Vyber kategorii nejdřív";

    const list = challenges[selectedCategory];
    let pick: string;

    do {
      pick = list[Math.floor(Math.random() * list.length)];
    } while (pick === lastPick && list.length > 1);

    lastPick = pick;
    return pick;
  }

  let cardText = "Vyber kategorii a klikni na Míchat";
</script>

<!-- HLAVNÍ KONTEJNER -->
<div class="min-h-screen w-full bg-[#1e3a8a] flex justify-center">
  <div class="w-full max-w-4xl px-4 py-20 flex flex-col items-center">

    <!-- NADPIS -->
    <div class="text-center mb-10">
      <h1 class="text-5xl font-extrabold text-gray-50 drop-shadow-md">Grow Yourself</h1>
      <p class="text-lg text-gray-50 mt-2">through small steps</p>
    </div>

    <!-- KATEGORIE -->
    <div class="flex flex-wrap gap-4 justify-center mb-8">
      {#each Object.keys(challenges) as cat}
        <button
          class="px-4 py-2 rounded-xl text-lg font-medium shadow-md transition
                 {selectedCategory === cat 
                  ? 'bg-blue-600 text-white shadow-lg scale-105' 
                  : 'bg-white text-gray-800 hover:bg-blue-300'}"
          on:click={() => {
            selectedCategory = cat;
            cardText = `Kategorie: ${cat}`;
          }}
        >
          {cat.charAt(0).toUpperCase() + cat.slice(1)}
        </button>
      {/each}
    </div>

    <!-- TLAČÍTKO -->
    <button
      class="px-8 py-3 bg-blue-600 hover:bg-blue-700 text-white rounded-xl text-xl font-semibold shadow-lg transition transform hover:scale-105 mb-6"
      on:click={() => (cardText = pickCard())}
    >
      Míchat karty
    </button>

    <!-- KARTA -->
    <div
      class="w-full max-w-lg min-h-[150px] bg-white rounded-2xl shadow-2xl p-8 text-center
             text-2xl font-semibold flex items-center justify-center
             border border-gray-100 transition
             hover:shadow-[0_0_25px_rgba(99,102,241,0.4)]"
    >
      {cardText}
    </div>

  </div>
</div>
