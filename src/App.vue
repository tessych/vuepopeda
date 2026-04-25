<script setup>
const victorySites = [
  {
    title: 'Питонпобеда',
    domain: 'питонпобеда.рф',
    badge: 'скрипты идут строем',
  },
  {
    title: 'Растпобеда',
    domain: 'растпобеда.рф',
    badge: 'borrow checker одобрил',
  },
  {
    title: 'Гопобеда',
    domain: 'гопобеда.рф',
    badge: 'goroutine наступление',
  },
  {
    title: 'Кубыпобеда',
    domain: 'кубыпобеда.рф',
    badge: 'кластер взят',
  },
  {
    title: 'Никспобеда',
    domain: 'никспобеда.рф',
    badge: 'конфиг воспроизводим',
  },
];

const shockwaves = Array.from({ length: 18 }, (_, index) => ({
  id: index,
  delay: `${index * 0.09}s`,
  x: `${(index % 6) * 15 - 36}px`,
  y: `${Math.floor(index / 6) * 18 - 18}px`,
}));
</script>

<template>
  <main class="page-shell">
    <section class="hero" aria-labelledby="main-title">
      <div class="hero-copy">
        <p class="eyebrow">официальный фронтендный разгром</p>
        <h1 id="main-title">Вьюпобеда.рф</h1>
        <p class="lead">
          Vue.js пришел, увидел, реактивно переписал: компоненты поют, шаблоны
          сияют, а React-логотип рассыпается от одного вида Composition API.
        </p>

        <div class="status-row" aria-label="Статус победы">
          <span>Vue заряжен</span>
          <span>React демонтирован</span>
          <span>Deploy ready</span>
        </div>
      </div>

      <div class="arena" aria-label="Vue.js разрушает логотип React">
        <div class="react-zone">
          <svg class="react-logo" viewBox="-55 -50 110 100" aria-hidden="true">
            <g class="react-orbits">
              <ellipse rx="48" ry="18" />
              <ellipse rx="48" ry="18" transform="rotate(60)" />
              <ellipse rx="48" ry="18" transform="rotate(120)" />
            </g>
            <circle r="7" />
          </svg>
          <span
            v-for="wave in shockwaves"
            :key="wave.id"
            class="fragment"
            :style="{ '--delay': wave.delay, '--x': wave.x, '--y': wave.y }"
          />
          <p class="react-caption">useEffect не выдержал</p>
        </div>

        <div class="vue-emblem" aria-hidden="true">
          <svg viewBox="0 0 256 221" role="img">
            <path fill="#42b883" d="M204.8 0H256L128 220.8 0 0h97.9L128 52.1 158.1 0h46.7Z" />
            <path fill="#35495e" d="M158.1 0 128 52.1 97.9 0H51.2L128 132.5 204.8 0h-46.7Z" />
          </svg>
          <div class="impact-beam" />
        </div>
      </div>
    </section>

    <section class="manifest">
      <div>
        <p class="section-kicker">протокол победы</p>
        <h2>React был силен, но Vue был понятнее.</h2>
      </div>
      <p>
        На этом сайте ни один виртуальный DOM серьезно не пострадал. Просто Vue
        вежливо пришел с однофайловыми компонентами и забрал главную сцену.
      </p>
    </section>

    <section class="victories" aria-labelledby="victory-title">
      <div class="section-heading">
        <p class="section-kicker">союзные сайты</p>
        <h2 id="victory-title">Другие территории победы</h2>
      </div>

      <div class="site-grid">
        <a
          v-for="site in victorySites"
          :key="site.domain"
          class="site-card"
          :href="`https://${site.domain}`"
          target="_blank"
          rel="noreferrer"
        >
          <span class="site-title">{{ site.title }}</span>
          <span class="site-domain">{{ site.domain }}</span>
          <span class="site-badge">{{ site.badge }}</span>
        </a>
      </div>
    </section>

    <footer class="footer">
      <span>Собрано на Vue.js</span>
      <span>Готово к GitHub Pages</span>
    </footer>
  </main>
</template>
