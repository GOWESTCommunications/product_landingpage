<script setup lang="ts">
definePageMeta({
})

useSeoMeta({
  title: 'TriGuest – Booking Analytics für den Tourismus',
  ogTitle: 'TriGuest – Booking Analytics für den Tourismus',
  description: 'TriGuest liefert fundierte Antworten auf essenzielle Erfolgsfragen rund um das Buchungsverhalten im Tourismus. E-Commerce-Tracking für Ihre Buchungsstrecke.',
  ogDescription: 'TriGuest liefert fundierte Antworten auf essenzielle Erfolgsfragen rund um das Buchungsverhalten im Tourismus. E-Commerce-Tracking für Ihre Buchungsstrecke.'
})

function enterMotion(delay: number = 0) {
  return {
    initial: { opacity: 0, y: 16 },
    animate: { opacity: 1, y: 0 },
    transition: { duration: 0.6, delay }
  }
}

function scrollMotion(delay: number = 0) {
  return {
    initial: { opacity: 0, y: 16 },
    whileInView: { opacity: 1, y: 0 },
    inViewOptions: { once: true, amount: 0.3 },
    transition: { duration: 0.6, delay }
  }
}

function staggerMotion(index: number = 0) {
  return {
    initial: { opacity: 0, y: 12 },
    whileInView: { opacity: 1, y: 0 },
    inViewOptions: { once: true, amount: 0.2 },
    transition: { duration: 0.5, delay: index * 0.1 }
  }
}

const analysisAreas = [
  {
    icon: 'i-lucide-binoculars',
    number: '01',
    title: 'Nachfrage & Gästeverhalten verstehen',
    description: 'Erfahren Sie, wann gebucht wird, wie weit im Voraus und über welchen Kanal. Verstehen Sie, woher Ihre Gäste kommen, welche Märkte am besten performen und wie lange der durchschnittliche Aufenthalt dauert.',
    questions: [
      'Wann wird gebucht, wie weit im Voraus und über welchen Kanal?',
      'Woher kommen die Gäste und welche Märkte performen am besten?',
      'Wie weit im Voraus wird gebucht und wie lange bleiben Gäste?'
    ]
  },
  {
    icon: 'i-lucide-target',
    number: '02',
    title: 'Marketing & Budget effizient steuern',
    description: 'Identifizieren Sie, welche Kampagnen tatsächlich zu Buchungen führen, wo Potenzial ungenutzt bleibt und wie Sie mit minimalem Budgeteinsatz maximalen Buchungserfolg erzielen.',
    questions: [
      'Welche Kampagnen führen tatsächlich zu Buchungen?',
      'Wo bleibt Potenzial ungenutzt?',
      'Wie erzielen Sie maximalen Buchungserfolg mit minimalem Budget?'
    ]
  },
  {
    icon: 'i-lucide-git-pull-request-arrow',
    number: '03',
    title: 'Buchungsstrecke & Angebot optimieren',
    description: 'Finden Sie heraus, welche Zimmer häufig angesehen aber selten gebucht werden und an welchen Stellen Nutzer:innen die Buchung abbrechen – und optimieren Sie gezielt.',
    questions: [
      'Welche Zimmer werden häufig angesehen, aber selten gebucht?',
      'An welchen Stellen brechen Nutzer die Buchung ab?',
      'Welche Angebote konvertieren am besten?'
    ]
  }
]

const bookingEngines = [
  { name: 'Seekda', tagline: 'Booking Engine' },
  { name: 'OnePageBooking', tagline: 'Booking Solution' },
  { name: 'Vioma', tagline: 'Hotel Software' }
]

const requirements = [
  { icon: 'i-simple-icons-googleanalytics', name: 'Google Analytics 4', short: 'Google Analytics 4', description: 'Nutzerdaten und Ereignis-Tracking als Datenbasis.' },
  { icon: 'i-simple-icons-googletagmanager', name: 'Google Tag Manager', short: 'Google Tag Manager', description: 'Für die Einbindung der Tracking-Tags ohne Entwickler.' },
  { icon: 'i-simple-icons-googleads', name: 'Google Ads', short: 'Google Ads', description: 'Kampagnen-Performance direkt mit Buchungsdaten verknüpfen.' },
  { icon: 'i-simple-icons-googlesearchconsole', name: 'Google Search Console', short: 'Google Search Console', description: 'SEO-Sichtbarkeit und organische Performance auswerten.' }
]

const dashboardStats = [
  { label: 'Buchungen', value: '1.284', change: '+12,4%', positive: true },
  { label: 'Umsatz', value: '€ 387.420', change: '+18,7%', positive: true },
  { label: 'Ø Aufenthalt', value: '3,2 Nächte', change: '+0,4', positive: true },
  { label: 'Conversion Rate', value: '4,8%', change: '+0,6%', positive: true }
]

const monthlyBookings = [
  { month: 'Jan', value: 62 },
  { month: 'Feb', value: 78 },
  { month: 'Mär', value: 95 },
  { month: 'Apr', value: 124 },
  { month: 'Mai', value: 156 },
  { month: 'Jun', value: 189 },
  { month: 'Jul', value: 210 },
  { month: 'Aug', value: 198 },
  { month: 'Sep', value: 142 },
  { month: 'Okt', value: 118 },
  { month: 'Nov', value: 74 },
  { month: 'Dez', value: 88 }
]

const channelData = [
  { name: 'Direkt', value: 42, color: '#ef4444' },
  { name: 'Google Ads', value: 28, color: '#fb923c' },
  { name: 'Organic', value: 18, color: '#f87171' },
  { name: 'Social', value: 8, color: '#fca5a5' },
  { name: 'Sonstige', value: 4, color: '#fecaca' }
]

const topMarkets = [
  { country: 'Deutschland', bookings: 482, share: 37.5 },
  { country: 'Österreich', bookings: 318, share: 24.8 },
  { country: 'Schweiz', bookings: 196, share: 15.3 },
  { country: 'Italien', bookings: 158, share: 12.3 },
  { country: 'Niederlande', bookings: 130, share: 10.1 }
]

const benefits = [
  { icon: 'i-lucide-funnel', title: 'Datenbasierte Sales-Funnels', description: 'Bauen Sie leistungsfähige Funnels auf tatsächlichen Buchungs- und Nutzerdaten auf – statt auf Vermutungen.' },
  { icon: 'i-lucide-wallet', title: 'Budgets optimal einsetzen', description: 'Jeder Euro zählt. Erkennen Sie, welche Kanäle und Kampagnen den besten ROI liefern.' },
  { icon: 'i-lucide-check-circle', title: 'Kampagnen zielsicher bewerten', description: 'Schluss mit Bauchgefühl: Bewerten Sie jede Maßnahme anhand echter Conversion-Daten.' },
  { icon: 'i-lucide-search', title: 'Optimierungspotenziale erkennen', description: 'Finden Sie Schwachstellen in der Buchungsstrecke und verwandeln Sie Abbrüche in Abschlüsse.' },
  { icon: 'i-lucide-line-chart', title: 'Transparente Performance', description: 'Live-Dashboards geben Ihnen jederzeit volle Kontrolle über alle relevanten KPIs.' },
  { icon: 'i-lucide-shield-check', title: 'DSGVO-konform', description: 'Alle Daten werden datenschutzkonform erhoben und verarbeitet – für rechtssicheres Tracking.' }
]
</script>

<template>
  <div class="triguest-theme relative">
    <!-- Background dot grid overlay -->
    <div
      class="pointer-events-none fixed inset-0 opacity-[0.03] z-0"
      style="background-image: radial-gradient(rgba(239, 68, 68, 0.8) 1px, transparent 1px); background-size: 32px 32px;"
    />

    <!-- Hero -->
    <UPageHero
      :ui="{
        container: 'relative z-10 lg:py-28',
        wrapper: 'flex flex-col items-center',
        title: 'sm:text-6xl lg:text-7xl xl:text-[80px] tracking-tighter leading-[1.05]',
        description: 'mt-5 max-w-2xl mx-auto text-base sm:text-lg leading-relaxed text-default',
        links: 'gap-3'
      }"
    >
      <template #top>
        <Motion v-bind="staggerMotion(0)" />
        <div
          class="pointer-events-none absolute top-0 left-1/2 -translate-x-1/2 w-2/3 h-1/2"
          style="background: radial-gradient(ellipse at center, rgba(239, 68, 68, 0.12) 0%, transparent 70%);"
        />
        <div class="pointer-events-none absolute -top-20 -left-32 w-[400px] h-[400px] rounded-full blur-[100px] bg-red-500/[0.07]" />
        <div class="pointer-events-none absolute -top-10 -right-40 w-[300px] h-[300px] rounded-full blur-[80px] bg-orange-500/[0.06]" />
      </template>

      <template #headline>
        <Motion v-bind="enterMotion(0.2)">
          <UBadge
            color="neutral"
            variant="soft"
            label="Booking Analytics für den Tourismus"
            class="rounded-full px-3 py-1.5 gap-1.5 bg-white/5 backdrop-blur"
          >
            <template #leading>
              <UChip
                inset
                standalone
                :ui="{ base: 'animate-pulse ring-0' }"
              />
            </template>
          </UBadge>
        </Motion>
      </template>

      <template #title>
        <Motion
          as="span"
          v-bind="enterMotion(0.35)"
          class="inline-block"
        >
          All you need
          <br>
          <span
            class="animate-shimmer bg-size-[200%_auto] bg-clip-text text-transparent"
            :style="{
              backgroundImage: 'linear-gradient(135deg, #f87171, #ef4444, #fb923c, #fdba74, #fb923c, #ef4444, #f87171)',
              animationDuration: '10s'
            }"
          >
            is data.
          </span>
        </Motion>
      </template>

      <template #description>
        <Motion
          as="span"
          v-bind="enterMotion(0.5)"
          class="inline-block"
        >
          TriGuest liefert fundierte Antworten auf essenzielle Erfolgsfragen rund um das Buchungsverhalten im Tourismus – damit Sie Entscheidungen auf Daten statt auf Vermutungen treffen.
        </Motion>
      </template>

      <template #links>
        <Motion
          class="flex flex-wrap justify-center gap-4"
          v-bind="enterMotion(0.65)"
        >
          <UButton
            label="Jetzt Angebot anfragen"
            class="bg-red-500 hover:bg-red-400 text-white shadow-[0_0_20px_rgba(239,68,68,0.25)] hover:shadow-[0_0_30px_rgba(239,68,68,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
            size="xl"
            to="#kontakt"
          />
          <UButton
            label="Mehr erfahren"
            size="xl"
            color="neutral"
            variant="soft"
            to="#analyse"
          />
        </Motion>
      </template>
    </UPageHero>

    <!-- Intro Text -->
    <UPageSection
      :ui="{
        container: 'max-w-3xl text-center'
      }"
    >
      <Motion v-bind="scrollMotion()">
        <p class="text-lg sm:text-xl leading-relaxed text-muted">
          Buchungsstrecken erzeugen täglich wertvolle Daten – aber nur wenige nutzen sie.
          <span class="text-red-300 font-medium">TriGuest macht diese Daten sichtbar, verständlich und handlungsrelevant.</span>
          Durch E-Commerce-Tracking auf Ihrer Buchungsengine erkennen Sie, was funktioniert, was nicht – und wo das größte Potenzial liegt.
        </p>
      </Motion>
    </UPageSection>

    <!-- Kompatible Buchungsengines -->
    <UPageSection
      :ui="{
        container: 'max-w-4xl text-center'
      }"
    >
      <Motion v-bind="scrollMotion()">
        <p class="font-mono uppercase text-xs tracking-[0.12em] text-red-400 mb-10">
          Kompatibel mit führenden Booking Engines
        </p>
      </Motion>

      <div class="flex flex-wrap items-center justify-center gap-10 sm:gap-16">
        <Motion
          v-for="(engine, index) in bookingEngines"
          :key="engine.name"
          v-bind="staggerMotion(index)"
        >
          <div class="flex flex-col items-center gap-2 opacity-60 hover:opacity-100 transition-opacity duration-300">
            <span class="text-2xl sm:text-3xl font-bold tracking-tight text-default">{{ engine.name }}</span>
            <span class="text-xs text-dimmed font-mono uppercase tracking-wider">{{ engine.tagline }}</span>
          </div>
        </Motion>
      </div>
    </UPageSection>

    <!-- Dashboard Demo -->
    <UPageSection
      id="dashboard"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-6xl',
        headline: 'font-mono font-medium text-xs text-red-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-md mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Live Dashboard
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          So sieht Ihr TriGuest Report aus.
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          Echtzeit-Dashboards in Google Data Studio – individuell für Ihr Hotel.
        </Motion>
      </template>

      <Motion v-bind="scrollMotion(0.3)">
        <div
          class="rounded-2xl border border-red-500/[0.12] bg-default overflow-hidden shadow-2xl shadow-red-500/[0.05]"
          style="background-image: linear-gradient(to top, rgba(239, 68, 68, 0.06) 0%, transparent 40%)"
        >
          <!-- Dashboard Header -->
          <div class="flex items-center justify-between px-6 py-4 border-b border-red-500/10">
            <div class="flex items-center gap-3">
              <div class="flex size-8 items-center justify-center rounded-lg bg-red-500/15">
                <UIcon name="i-lucide-bar-chart-3" class="size-4 text-red-400" />
              </div>
              <div>
                <p class="text-sm font-semibold tracking-tight">Hotel Alpenpanorama</p>
                <p class="text-[11px] text-dimmed font-mono">Jan 2025 – Dez 2025</p>
              </div>
            </div>
            <div class="flex items-center gap-2">
              <span class="inline-flex items-center gap-1 px-2 py-1 rounded-md bg-red-500/10 text-[10px] font-mono text-red-400">
                <span class="size-1.5 rounded-full bg-red-400 animate-pulse" />
                Live
              </span>
            </div>
          </div>

          <!-- KPI Stats Row -->
          <div class="grid grid-cols-2 lg:grid-cols-4 gap-px bg-red-500/5">
            <div
              v-for="(stat, index) in dashboardStats"
              :key="stat.label"
              class="bg-default px-5 py-5"
            >
              <p class="text-[11px] text-dimmed font-mono uppercase tracking-wider mb-1">{{ stat.label }}</p>
              <p class="text-2xl sm:text-3xl font-bold tracking-tight text-default leading-none mb-1">{{ stat.value }}</p>
              <span class="inline-flex items-center gap-0.5 text-xs font-medium text-red-400">
                <UIcon name="i-lucide-trending-up" class="size-3" />
                {{ stat.change }}
              </span>
            </div>
          </div>

          <!-- Charts Area -->
          <div class="grid grid-cols-1 lg:grid-cols-3 gap-px bg-red-500/5">
            <!-- Bookings Over Time (Bar Chart) -->
            <div class="lg:col-span-2 bg-default p-6">
              <div class="flex items-center justify-between mb-5">
                <div>
                  <h4 class="text-sm font-semibold tracking-tight">Buchungen pro Monat</h4>
                  <p class="text-[11px] text-dimmed">Gesamtjahr 2025</p>
                </div>
                <span class="text-[10px] font-mono text-dimmed px-2 py-1 rounded bg-red-500/5">12 Monate</span>
              </div>

              <!-- SVG Bar Chart -->
              <div class="relative">
                <svg viewBox="0 0 600 200" class="w-full h-auto" preserveAspectRatio="xMidYMid meet">
                  <!-- Grid lines -->
                  <line v-for="i in 4" :key="'grid-'+i" x1="0" :y1="i * 40" x2="600" :y2="i * 40" stroke="currentColor" class="text-red-500/5" stroke-width="1" />

                  <!-- Bars -->
                  <g v-for="(item, index) in monthlyBookings" :key="item.month">
                    <rect
                      :x="index * 50 + 8"
                      :y="200 - (item.value / 210 * 170)"
                      width="34"
                      :height="item.value / 210 * 170"
                      rx="4"
                      class="transition-all duration-300"
                      :fill="item.value >= 180 ? '#ef4444' : item.value >= 120 ? '#f97316' : '#fbbf24'"
                      :opacity="0.8"
                    />
                    <!-- Value on top -->
                    <text
                      :x="index * 50 + 25"
                      :y="200 - (item.value / 210 * 170) - 6"
                      text-anchor="middle"
                      class="fill-orange-400 text-[9px] font-mono"
                    >{{ item.value }}</text>
                    <!-- Month label -->
                    <text
                      :x="index * 50 + 25"
                      y="196"
                      text-anchor="middle"
                      class="fill-current text-white text-[9px] font-mono"
                    >{{ item.month }}</text>
                  </g>
                </svg>
              </div>
            </div>

            <!-- Channel Breakdown (Horizontal bars) -->
            <div class="bg-default p-6">
              <div class="mb-5">
                <h4 class="text-sm font-semibold tracking-tight">Buchungskanäle</h4>
                <p class="text-[11px] text-dimmed">Anteil nach Kanal</p>
              </div>

              <div class="space-y-4">
                <div v-for="channel in channelData" :key="channel.name">
                  <div class="flex items-center justify-between mb-1.5">
                    <span class="text-xs font-medium">{{ channel.name }}</span>
                    <span class="text-xs font-mono text-red-400">{{ channel.value }}%</span>
                  </div>
                  <div class="h-2 rounded-full bg-red-500/5 overflow-hidden">
                    <div
                      class="h-full rounded-full transition-all duration-700"
                      :style="{ width: channel.value + '%', backgroundColor: channel.color }"
                    />
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Bottom Row: Markets Table + Donut -->
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-px bg-red-500/5">
            <!-- Top Markets Table -->
            <div class="bg-default p-6">
              <div class="mb-4">
                <h4 class="text-sm font-semibold tracking-tight">Top Herkunftsmärkte</h4>
                <p class="text-[11px] text-dimmed">Nach Buchungsanzahl</p>
              </div>

              <div class="overflow-hidden rounded-xl border border-red-500/10">
                <table class="w-full text-left">
                  <thead>
                    <tr class="bg-red-500/5">
                      <th class="px-4 py-2.5 text-[11px] font-mono uppercase tracking-wider text-dimmed">Land</th>
                      <th class="px-4 py-2.5 text-[11px] font-mono uppercase tracking-wider text-dimmed text-right">Buchungen</th>
                      <th class="px-4 py-2.5 text-[11px] font-mono uppercase tracking-wider text-dimmed text-right">Anteil</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr
                      v-for="(market, index) in topMarkets"
                      :key="market.country"
                      class="border-t border-red-500/5"
                    >
                      <td class="px-4 py-2.5 text-sm">
                        <span class="flex items-center gap-2">
                          <span class="size-2 rounded-full" :style="{ backgroundColor: channelData[index]?.color || '#ef4444' }" />
                          {{ market.country }}
                        </span>
                      </td>
                      <td class="px-4 py-2.5 text-sm text-right font-mono">{{ market.bookings }}</td>
                      <td class="px-4 py-2.5 text-sm text-right font-mono text-red-400">{{ market.share }}%</td>
                    </tr>
                  </tbody>
                </table>
              </div>
            </div>

            <!-- Mini Stats / Room Performance -->
            <div class="bg-default p-6">
              <div class="mb-4">
                <h4 class="text-sm font-semibold tracking-tight">Zimmerperformance</h4>
                <p class="text-[11px] text-dimmed">Buchungen nach Zimmerkategorie</p>
              </div>

              <div class="space-y-3">
                <div class="flex items-center gap-3 p-3 rounded-xl bg-red-500/5">
                  <div class="flex size-10 items-center justify-center rounded-lg bg-red-500/15">
                    <UIcon name="i-lucide-bed-double" class="size-5 text-red-400" />
                  </div>
                  <div class="flex-1 min-w-0">
                    <p class="text-sm font-medium">Doppelzimmer Superior</p>
                    <p class="text-[11px] text-dimmed">Ø € 189 / Nacht</p>
                  </div>
                  <div class="text-right">
                    <p class="text-sm font-bold font-mono text-red-400">412</p>
                    <p class="text-[10px] text-dimmed">Buchungen</p>
                  </div>
                </div>

                <div class="flex items-center gap-3 p-3 rounded-xl bg-red-500/5">
                  <div class="flex size-10 items-center justify-center rounded-lg bg-red-500/15">
                    <UIcon name="i-lucide-bed-double" class="size-5 text-red-400" />
                  </div>
                  <div class="flex-1 min-w-0">
                    <p class="text-sm font-medium">Suite Panorama</p>
                    <p class="text-[11px] text-dimmed">Ø € 329 / Nacht</p>
                  </div>
                  <div class="text-right">
                    <p class="text-sm font-bold font-mono text-red-400">286</p>
                    <p class="text-[10px] text-dimmed">Buchungen</p>
                  </div>
                </div>

                <div class="flex items-center gap-3 p-3 rounded-xl bg-red-500/5">
                  <div class="flex size-10 items-center justify-center rounded-lg bg-red-500/15">
                    <UIcon name="i-lucide-bed-single" class="size-5 text-red-400" />
                  </div>
                  <div class="flex-1 min-w-0">
                    <p class="text-sm font-medium">Einzelzimmer Komfort</p>
                    <p class="text-[11px] text-dimmed">Ø € 129 / Nacht</p>
                  </div>
                  <div class="text-right">
                    <p class="text-sm font-bold font-mono text-red-400">198</p>
                    <p class="text-[10px] text-dimmed">Buchungen</p>
                  </div>
                </div>

                <div class="flex items-center gap-3 p-3 rounded-xl bg-red-500/5">
                  <div class="flex size-10 items-center justify-center rounded-lg bg-red-500/15">
                    <UIcon name="i-lucide-house" class="size-5 text-red-400" />
                  </div>
                  <div class="flex-1 min-w-0">
                    <p class="text-sm font-medium">Familien-Apartment</p>
                    <p class="text-[11px] text-dimmed">Ø € 259 / Nacht</p>
                  </div>
                  <div class="text-right">
                    <p class="text-sm font-bold font-mono text-red-400">156</p>
                    <p class="text-[10px] text-dimmed">Buchungen</p>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Dashboard Footer -->
          <div class="flex items-center justify-between px-6 py-3 border-t border-red-500/10 bg-red-500/[0.02]">
            <span class="text-[10px] text-dimmed font-mono">Powered by TriGuest × Google Data Studio</span>
            <span class="text-[10px] text-dimmed font-mono">Beispieldaten – Hotel Alpenpanorama</span>
          </div>
        </div>

        <p class="text-center text-xs text-dimmed mt-4">
          Beispiel-Dashboard mit fiktiven Daten – Ihr Report wird individuell auf Ihr Hotel zugeschnitten.
        </p>
      </Motion>
    </UPageSection>

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-48 right-[-5%] w-[600px] h-[600px] rounded-full blur-[100px] bg-red-500/[0.08]" />
      <div class="absolute -top-20 left-[-10%] w-[350px] h-[350px] rounded-full blur-[80px] bg-orange-400/[0.06]" />
    </div>

    <!-- Analyse-Bereiche -->
    <UPageSection
      id="analyse"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-red-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-md mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion
          as="span"
          v-bind="scrollMotion()"
          class="inline-block"
        >
          Analyse
        </Motion>
      </template>

      <template #title>
        <Motion
          as="span"
          v-bind="scrollMotion(0.1)"
          class="inline-block"
        >
          Drei Dimensionen, ein Ziel: mehr Buchungen.
        </Motion>
      </template>

      <template #description>
        <Motion
          as="span"
          v-bind="scrollMotion(0.2)"
          class="inline-block"
        >
          TriGuest beantwortet die wichtigsten Fragen rund um Nachfrage, Marketing und Buchungsstrecke.
        </Motion>
      </template>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 mt-4">
        <Motion
          v-for="(area, index) in analysisAreas"
          :key="area.title"
          v-bind="staggerMotion(index)"
        >
          <div
            class="relative rounded-2xl border border-red-500/[0.12] bg-default p-8 h-full hover:border-red-500/25 hover:shadow-[0_0_30px_rgba(239,68,68,0.1)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(239, 68, 68, 0.1) 0%, rgba(239, 68, 68, 0.02) 50%, transparent 80%)"
          >
            <span class="absolute top-6 right-6 font-mono text-4xl font-black text-red-500/15">{{ area.number }}</span>
            <div class="mb-5 flex size-12 items-center justify-center rounded-xl bg-red-500/15 ring-1 ring-red-500/10">
              <UIcon
                :name="area.icon"
                class="size-6 text-red-400"
              />
            </div>
            <h3 class="text-base font-semibold tracking-tight mb-3">
              {{ area.title }}
            </h3>
            <ul class="space-y-2">
              <li
                v-for="question in area.questions"
                :key="question"
                class="flex items-start gap-2 text-sm text-dimmed leading-relaxed"
              >
                <UIcon
                  name="i-lucide-chevron-right"
                  class="size-4 text-red-400 shrink-0 mt-0.5"
                />
                <span>{{ question }}</span>
              </li>
            </ul>
          </div>
        </Motion>
      </div>

      <Motion v-bind="scrollMotion(0.4)">
        <div class="flex flex-wrap justify-center gap-3 mt-10">
          <UButton
            label="Analyse für mein Hotel anfragen"
            class="bg-gradient-to-r from-red-500 to-orange-500 hover:from-red-400 hover:to-orange-400 text-white shadow-[0_0_20px_rgba(239,68,68,0.25)] hover:shadow-[0_0_30px_rgba(239,68,68,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
            size="lg"
            to="#kontakt"
          />
          <UButton
            label="Voraussetzungen prüfen"
            size="lg"
            color="neutral"
            variant="soft"
            to="#voraussetzungen"
          />
        </div>
      </Motion>
    </UPageSection>

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-48 left-[-8%] w-[700px] h-[500px] rounded-full blur-[120px] bg-red-500/[0.07]" />
      <div class="absolute -top-20 right-[5%] w-[300px] h-[300px] rounded-full blur-[80px] bg-orange-400/[0.05]" />
    </div>

    <!-- Voraussetzungen -->
    <UPageSection
      id="voraussetzungen"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-red-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-md mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion
          as="span"
          v-bind="scrollMotion()"
          class="inline-block"
        >
          Setup
        </Motion>
      </template>

      <template #title>
        <Motion
          as="span"
          v-bind="scrollMotion(0.1)"
          class="inline-block"
        >
          Was wir für den Start benötigen.
        </Motion>
      </template>

      <template #description>
        <Motion
          as="span"
          v-bind="scrollMotion(0.2)"
          class="inline-block"
        >
          Für eine vollständige Analyse benötigen wir Zugriff auf folgende Google-Dienste.
        </Motion>
      </template>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 mt-2">
        <Motion
          v-for="(req, index) in requirements"
          :key="req.name"
          v-bind="staggerMotion(index)"
        >
          <div
            class="rounded-2xl border border-red-500/[0.12] bg-default p-6 h-full hover:border-red-500/30 hover:shadow-[0_0_30px_rgba(239,68,68,0.1)] transition-all duration-300 text-center"
            style="background-image: linear-gradient(to top, rgba(239, 68, 68, 0.1) 0%, rgba(239, 68, 68, 0.02) 50%, transparent 80%)"
          >
            <div class="mb-4 mx-auto flex size-12 items-center justify-center rounded-xl bg-red-500/15 ring-1 ring-red-500/10">
              <UIcon
                :name="req.icon"
                class="size-6 text-red-400"
              />
            </div>
            <h3 class="text-sm font-semibold tracking-tight mb-1">
              {{ req.short }}
            </h3>
            <p class="text-xs text-dimmed leading-relaxed">
              {{ req.description }}
            </p>
          </div>
        </Motion>
      </div>
    </UPageSection>

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-40 right-[5%] w-[500px] h-[400px] rounded-full blur-[100px] bg-orange-400/[0.06]" />
    </div>

    <!-- Vorteile / E-Commerce Tracking -->
    <UPageSection
      id="vorteile"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-red-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-lg mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion
          as="span"
          v-bind="scrollMotion()"
          class="inline-block"
        >
          Vorteile
        </Motion>
      </template>

      <template #title>
        <Motion
          as="span"
          v-bind="scrollMotion(0.1)"
          class="inline-block"
        >
          Datenbasiert entscheiden statt raten.
        </Motion>
      </template>

      <template #description>
        <Motion
          as="span"
          v-bind="scrollMotion(0.2)"
          class="inline-block"
        >
          Durch das TriGuest-E-Commerce-Tracking bauen Sie leistungsfähige Sales-Funnels auf tatsächlichen Buchungs- und Nutzerdaten auf.
        </Motion>
      </template>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 mt-2">
        <Motion
          v-for="(benefit, index) in benefits"
          :key="benefit.title"
          v-bind="staggerMotion(index)"
        >
          <div
            class="rounded-2xl border border-red-500/[0.12] bg-default p-6 h-full hover:border-red-500/30 hover:shadow-[0_0_30px_rgba(239,68,68,0.1)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(239, 68, 68, 0.1) 0%, rgba(239, 68, 68, 0.02) 50%, transparent 80%)"
          >
            <div class="mb-4 flex size-10 items-center justify-center rounded-lg bg-red-500/15 ring-1 ring-red-500/10">
              <UIcon
                :name="benefit.icon"
                class="size-5 text-red-400"
              />
            </div>
            <h3 class="text-sm font-semibold tracking-tight mb-1.5">
              {{ benefit.title }}
            </h3>
            <p class="text-sm text-dimmed leading-relaxed">
              {{ benefit.description }}
            </p>
          </div>
        </Motion>
      </div>

      <Motion v-bind="scrollMotion(0.4)">
        <div class="flex justify-center mt-10">
          <UButton
            label="Jetzt TriGuest Tracking einrichten"
            class="bg-gradient-to-r from-red-500 to-orange-500 hover:from-red-400 hover:to-orange-400 text-white shadow-[0_0_20px_rgba(239,68,68,0.25)] hover:shadow-[0_0_30px_rgba(239,68,68,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
            size="xl"
            to="#kontakt"
          />
        </div>
      </Motion>
    </UPageSection>

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-48 left-[10%] w-[500px] h-[500px] rounded-full blur-[100px] bg-red-500/[0.08]" />
      <div class="absolute -top-20 right-[-3%] w-[300px] h-[300px] rounded-full blur-[80px] bg-orange-400/[0.05]" />
    </div>

    <!-- So funktioniert's -->
    <UPageSection
      id="so-funktionierts"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-red-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-md mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion
          as="span"
          v-bind="scrollMotion()"
          class="inline-block"
        >
          Ablauf
        </Motion>
      </template>

      <template #title>
        <Motion
          as="span"
          v-bind="scrollMotion(0.1)"
          class="inline-block"
        >
          In vier Schritten zu datengetriebenen Buchungen.
        </Motion>
      </template>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 mt-4">
        <Motion v-bind="staggerMotion(0)">
          <div
            class="relative rounded-2xl border border-red-500/[0.12] bg-default p-6 h-full hover:border-red-500/25 hover:shadow-[0_0_30px_rgba(239,68,68,0.1)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(239, 68, 68, 0.1) 0%, rgba(239, 68, 68, 0.02) 50%, transparent 80%)"
          >
            <span class="absolute top-4 right-4 font-mono text-3xl font-black text-red-500/15">01</span>
            <div class="mb-4 flex size-10 items-center justify-center rounded-lg bg-red-500/15 ring-1 ring-red-500/10">
              <UIcon
                name="i-lucide-key-round"
                class="size-5 text-red-400"
              />
            </div>
            <h3 class="text-sm font-semibold tracking-tight mb-1.5">
              Zugänge bereitstellen
            </h3>
            <p class="text-xs text-dimmed leading-relaxed">
              GA4, GTM, Google Ads und Search Console Zugriff teilen.
            </p>
          </div>
        </Motion>
        <Motion v-bind="staggerMotion(1)">
          <div
            class="relative rounded-2xl border border-red-500/[0.12] bg-default p-6 h-full hover:border-red-500/25 hover:shadow-[0_0_30px_rgba(239,68,68,0.1)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(239, 68, 68, 0.1) 0%, rgba(239, 68, 68, 0.02) 50%, transparent 80%)"
          >
            <span class="absolute top-4 right-4 font-mono text-3xl font-black text-red-500/15">02</span>
            <div class="mb-4 flex size-10 items-center justify-center rounded-lg bg-red-500/15 ring-1 ring-red-500/10">
              <UIcon
                name="i-lucide-settings"
                class="size-5 text-red-400"
              />
            </div>
            <h3 class="text-sm font-semibold tracking-tight mb-1.5">
              Tracking einrichten
            </h3>
            <p class="text-xs text-dimmed leading-relaxed">
              Wir konfigurieren das E-Commerce-Tracking für Ihre Buchungsengine.
            </p>
          </div>
        </Motion>
        <Motion v-bind="staggerMotion(2)">
          <div
            class="relative rounded-2xl border border-red-500/[0.12] bg-default p-6 h-full hover:border-red-500/25 hover:shadow-[0_0_30px_rgba(239,68,68,0.1)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(239, 68, 68, 0.1) 0%, rgba(239, 68, 68, 0.02) 50%, transparent 80%)"
          >
            <span class="absolute top-4 right-4 font-mono text-3xl font-black text-red-500/15">03</span>
            <div class="mb-4 flex size-10 items-center justify-center rounded-lg bg-red-500/15 ring-1 ring-red-500/10">
              <UIcon
                name="i-lucide-bar-chart-3"
                class="size-5 text-red-400"
              />
            </div>
            <h3 class="text-sm font-semibold tracking-tight mb-1.5">
              Daten sammeln
            </h3>
            <p class="text-xs text-dimmed leading-relaxed">
              TriGuest sammelt und strukturiert alle Buchungs- und Nutzerdaten automatisch.
            </p>
          </div>
        </Motion>
        <Motion v-bind="staggerMotion(3)">
          <div
            class="relative rounded-2xl border border-red-500/[0.12] bg-default p-6 h-full hover:border-red-500/25 hover:shadow-[0_0_30px_rgba(239,68,68,0.1)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(239, 68, 68, 0.1) 0%, rgba(239, 68, 68, 0.02) 50%, transparent 80%)"
          >
            <span class="absolute top-4 right-4 font-mono text-3xl font-black text-red-500/15">04</span>
            <div class="mb-4 flex size-10 items-center justify-center rounded-lg bg-red-500/15 ring-1 ring-red-500/10">
              <UIcon
                name="i-lucide-lightbulb"
                class="size-5 text-red-400"
              />
            </div>
            <h3 class="text-sm font-semibold tracking-tight mb-1.5">
              Insights nutzen
            </h3>
            <p class="text-xs text-dimmed leading-relaxed">
              Optimieren Sie Kampagnen, Buchungsstrecke und Budget anhand echter Zahlen.
            </p>
          </div>
        </Motion>
      </div>

      <Motion v-bind="scrollMotion(0.4)">
        <div class="flex justify-center mt-10">
          <UButton
            label="Individuelles Angebot anfordern"
            class="bg-gradient-to-r from-red-500 to-orange-500 hover:from-red-400 hover:to-orange-400 text-white shadow-[0_0_20px_rgba(239,68,68,0.25)] hover:shadow-[0_0_30px_rgba(239,68,68,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
            size="xl"
            to="#kontakt"
          />
        </div>
      </Motion>
    </UPageSection>

    <!-- CTA / Kontaktformular -->
    <UPageCTA
      id="kontakt"
      variant="naked"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-3xl text-center'
      }"
    >
      <template #top>
        <div
          class="pointer-events-none absolute bottom-0 left-1/2 -translate-x-1/2 w-2/3 h-1/2"
          style="background: radial-gradient(ellipse at center, rgba(239, 68, 68, 0.12) 0%, transparent 70%);"
        />
        <div class="pointer-events-none absolute -bottom-20 -left-20 w-[350px] h-[350px] rounded-full blur-[80px] bg-red-500/[0.06]" />
        <div class="pointer-events-none absolute -bottom-10 -right-32 w-[300px] h-[300px] rounded-full blur-[80px] bg-orange-500/[0.05]" />
      </template>

      <template #title>
        <Motion
          as="span"
          v-bind="scrollMotion()"
          class="inline-block text-4xl lg:text-5xl tracking-tighter"
        >
          Bereit, Ihre Buchungsdaten zu nutzen?
        </Motion>
      </template>

      <template #description>
        <Motion
          as="span"
          v-bind="scrollMotion(0.1)"
          class="inline-block max-w-md mx-auto leading-relaxed text-dimmed"
        >
          Wir freuen uns, Ihnen jederzeit ein individuelles Angebot zu übermitteln. Kontaktieren Sie uns – und machen Sie Ihre Buchungsstrecke messbar erfolgreich.
        </Motion>
      </template>

      <template #links>
        <Motion
          class="w-full max-w-md mx-auto mt-8"
          v-bind="scrollMotion(0.2)"
        >
          <form
            class="flex flex-col gap-4"
            @submit.prevent
          >
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <UInput
                placeholder="Vorname"
                size="xl"
                :ui="{ base: 'bg-elevated' }"
              />
              <UInput
                placeholder="Nachname"
                size="xl"
                :ui="{ base: 'bg-elevated' }"
              />
            </div>
            <UInput
              type="email"
              placeholder="E-Mail-Adresse"
              size="xl"
              :ui="{ base: 'bg-elevated' }"
            />
            <UInput
              placeholder="Hotel / Unternehmen"
              size="xl"
              :ui="{ base: 'bg-elevated' }"
            />
            <UInput
              placeholder="Website-URL"
              size="xl"
              :ui="{ base: 'bg-elevated' }"
            />
            <USelect
              placeholder="Aktuelle Buchungsengine"
              size="xl"
              :items="['Seekda', 'OnePageBooking', 'Vioma', 'Andere']"
              :ui="{ base: 'bg-elevated' }"
            />
            <UTextarea
              placeholder="Ihre Nachricht (optional)"
              :rows="3"
              :ui="{ base: 'bg-elevated' }"
            />
            <UButton
              label="Individuelles Angebot anfragen"
              class="bg-red-500 hover:bg-red-400 text-white shadow-[0_0_20px_rgba(239,68,68,0.25)] hover:shadow-[0_0_30px_rgba(239,68,68,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
              size="xl"
              block
              type="submit"
            />
            <p class="text-xs text-dimmed text-center">
              Wir melden uns innerhalb von 24h mit einem individuellen Angebot für Ihr Haus.
            </p>
          </form>
        </Motion>
      </template>
    </UPageCTA>
  </div>
</template>
