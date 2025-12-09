<script lang="ts">
  let skills = [
    { title: "Silný mindset", icon: "🧠" },
    { title: "Empatie", icon: "💛" },
    { title: "Leadership", icon: "🚀" },
    { title: "Kreativita", icon: "🎨" },
    { title: "Analytické myšlení", icon: "📊" },
    { title: "Motivace", icon: "🔥" }
  ];

  let experiences = [
    {
      role: "Mistr PREFA kompletací / Projektový koordinátor výroby",
      period: "SRP 2024 – Současnost",
      description: `
        Řízení a koordinace výrobního úseku nejmodernější linky na kompletaci prefabrikovaných dílců.
        Plánování práce týmu, rozdělování úkolů a sledování jejich plnění.
        Analýza příčin chybovosti a návrh nápravných opatření.
        Implementace procesních zlepšení s cílem zvýšit kvalitu a efektivitu výroby.
        Spolupráce s dalšími odděleními na řešení technických problémů.
        Klíčové kompetence: projektová koordinace, vedení týmu, procesní analýza.
      `,
      open: false
    },
    {
      role: "Technik kontroly kvality",
      period: "ČRC 2024 – SRP 2024",
      description: `
        Kontrola kvality prefabrikovaných betonových panelů.
        Spolupráce s mistrem při odstraňování chyb.
        Zodpovědnost za správnost výrobní dokumentace a kontrolních procesů.
      `,
      open: false
    },
    {
      role: "Marketingový konzultant (na volné noze)",
      period: "LED 2020 – Současnost",
      description: `
        Správa sociálních sítí a e‑shopů menších prodejců.
        Tvorba grafického obsahu a propagačních materiálů.
        Konzultace k marketingovým strategiím.
        Projekty: milujumotorky, motocykly mladá boleslav, bikeangel, speeddiet aj.
      `,
      open: false
    },
    {
      role: "Operátor řídícího centra fyzické ochrany",
      period: "LIST 2020 – ČER 2024",
      description: `
        Zajištění provozu Technického systému fyzické ochrany (TSFO) Jaderné elektrárny Dukovany.
        Vyhodnocování technického stavu a provozních údajů.
        Řízení, koordinace a kontrola provozu systému TSFO.
        Vedení směny fyzické ochrany a řešení nestandardních a poruchových stavů.
        Koordinace činností bezpečnostní služby a Policie ČR.
        Návrhy a řízení realizace náhradních bezpečnostních opatření.
      `,
      open: false
    },
    {
      role: "Produktový manažer",
      period: "ÚNR 2018 – DUB 2020",
      description: `
        Správa portfolia produktů v oblasti autodílů.
        Prodej sortimentu na Amazonu a jednání s Amazon vendorem.
        Správa e‑shopu, kontrola skladových zásob a řízení kampaní.
        Fakturace a každodenní komunikace s obchodními partnery.
      `,
      open: false
    },
    {
      role: "Policista",
      period: "LED 2014 – ZÁŘ 2018",
      description: `
        Ochrana osob a bezpečnostní dohled.
        Řešení krizových situací a spolupráce s dalšími složkami.
        Státní a veřejná bezpečnost, střelecká příprava.
      `,
      open: false
    },
    {
      role: "Stavební mistr",
      period: "ZÁŘ 2010 – ÚNR 2012",
      description: `
        Řízení dílčích stavebních operací a koordinace pracovníků.
        Spolupráce se stavbyvedoucím na plánování a kontrole průběhu stavby.
      `,
      open: false
    }
  ];

  function toggle(index: number) {
    experiences[index].open = !experiences[index].open;
  }
</script>

<div class="w-full flex justify-center px-4 py-16">
  <div class="w-full max-w-5xl">

    <section class="text-center mb-20 mt-20">
      <h1 class="text-5xl font-extrabold text-gray-50 drop-shadow-md">Tomáš Petz</h1>
      <p class="text-lg text-gray-50 mt-2">začínající developer</p>
      
      <div class="mt-8">
        <a href="/projects" class="px-8 py-3 bg-blue-600 hover:bg-blue-700 text-white rounded-xl text-lg shadow transition">Moje projekty</a>
      </div>
    </section>

    <section class="mb-20">
      <h2 class="text-3xl font-semibold text-gray-50 drop-shadow-md mb-6 text-center mt-20">Moje silné stránky</h2>
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
        {#each skills as skill}
          <div class="bg-white shadow rounded-xl p-8 text-center hover:shadow-md transition border border-gray-100">
            <div class="text-5xl mb-3">{skill.icon}</div>
            <p class="text-lg font-medium text-gray-700">{skill.title}</p>
          </div>
        {/each}
      </div>
    </section>

    <section>
      <h2 class="text-3xl font-semibold text-gray-50 drop-shadow-md mb-6 text-center mt-20">Pracovní zkušenosti</h2>

      <div class="space-y-4">
        {#each experiences as exp, i}
          <div class="bg-white shadow rounded-xl overflow-hidden border border-gray-100">
            <button class="w-full flex justify-between items-center p-5 text-left hover:bg-gray-50 transition" on:click={() => toggle(i)}>
              <div>
                <span class="font-semibold text-gray-900 text-lg">{exp.role}</span>
                <p class="text-sm text-gray-500">{exp.period}</p>
              </div>
              <span class="text-gray-600 text-2xl">{exp.open ? "▲" : "▼"}</span>
            </button>

            {#if exp.open}
              <div class="px-5 pb-5 text-gray-600 whitespace-pre-line leading-relaxed">
                {exp.description}
              </div>
            {/if}
          </div>
        {/each}
      </div>
    </section>

    <!-- KONTAKT SEKCE -->
    <section class="mt-20 mb-10">
      <h2 class="text-3xl font-semibold text-gray-50 drop-shadow-md mb-6 text-center mt-20">Kontakt</h2>

      <div class="flex justify-center gap-8 text-4xl text-gray-700">
        <a href="https://www.linkedin.com" target="_blank" class="hover:text-blue-600 transition" aria-label="LinkedIn">🔗</a>
        <a href="https://www.instagram.com" target="_blank" class="hover:text-pink-500 transition" aria-label="Instagram">📸</a>
        <a href="https://www.github.com" target="_blank" class="hover:text-gray-900 transition" aria-label="GitHub">🐙</a>
        <a href="mailto:tvoje@email.cz" class="hover:text-red-600 transition" aria-label="Email">✉️</a>
        <a href="tel:+420123456789" class="hover:text-green-600 transition" aria-label="Telefon">📞</a>
      </div>
    </section>

    <footer class="text-center mt-20 text-gray-500 text-sm">
      © {new Date().getFullYear()} [Tvé jméno] – Vytvořeno ve SvelteKitu
    </footer>
  </div>
</div>
