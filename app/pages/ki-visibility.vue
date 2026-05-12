<script setup lang="ts">
definePageMeta({
})

useSeoMeta({
  title: 'KI Visibility – Sichtbar in ChatGPT, Gemini & Co.',
  ogTitle: 'KI Visibility – Sichtbar in ChatGPT, Gemini & Co.',
  description: 'KI Visibility zeigt, wie sichtbar Ihr Unternehmen in ChatGPT, Gemini, Google AI und anderen KI-Systemen ist – mit konkreten Handlungsempfehlungen.',
  ogDescription: 'KI Visibility zeigt, wie sichtbar Ihr Unternehmen in ChatGPT, Gemini, Google AI und anderen KI-Systemen ist – mit konkreten Handlungsempfehlungen.'
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

const vorteile = [
  { icon: 'i-lucide-eye', title: 'Sichtbarkeit analysieren', description: 'Wie präsent ist Ihr Unternehmen in ChatGPT, Gemini & Google AI?' },
  { icon: 'i-lucide-users', title: 'Mitbewerber vergleichen', description: 'Direkte Gegenüberstellung Ihrer Sichtbarkeit mit relevanten Wettbewerbern.' },
  { icon: 'i-lucide-target', title: 'Potenziale erkennen', description: 'Wo liegen Ihre Chancen für mehr KI-Reichweite und Relevanz?' },
  { icon: 'i-lucide-file-text', title: 'ONPAGE & OFFPAGE', description: 'Konkrete Empfehlungen für Content, Struktur und externe Plattformen.' },
  { icon: 'i-lucide-trending-up', title: 'Relevanz aufbauen', description: 'Mehr Erwähnungen und bessere Positionierung in KI-Antworten.' },
  { icon: 'i-lucide-check-circle', title: 'Klare Empfehlungen', description: 'Handlungsempfehlungen statt Vermutungen – datenbasiert und priorisiert.' }
]

const useCases = [
  {
    icon: 'i-lucide-hotel',
    title: 'Tourismus & Hotellerie',
    questions: [
      'Wie sichtbar ist Ihr Hotel bei Empfehlungen in ChatGPT & Co.?',
      'Welche Mitbewerber dominieren bestimmte Themen?'
    ]
  },
  {
    icon: 'i-lucide-building-2',
    title: 'Unternehmen & Dienstleistungen',
    questions: [
      'Wie wird Ihre Marke in KI-Systemen wahrgenommen?',
      'Welche Inhalte fehlen für mehr Sichtbarkeit?'
    ]
  },
  {
    icon: 'i-lucide-shopping-bag',
    title: 'E-Commerce & Marken',
    questions: [
      'Welche Produkte werden von KI-Systemen bevorzugt genannt?',
      'Wie kann die Markenpräsenz verbessert werden?'
    ]
  }
]

const steps = [
  { number: '01', title: 'Personas, Themen & Prompts definieren', description: 'Wir analysieren relevante Fragestellungen rund um Ihre Branche, Leistungen und Zielgruppen.' },
  { number: '02', title: 'KI-Systeme auswerten', description: 'ChatGPT, Gemini und weitere Systeme werden mit definierten Suchanfragen getestet.' },
  { number: '03', title: 'Sichtbarkeit analysieren', description: 'Wir prüfen, wie oft Ihr Unternehmen genannt wird, wie es positioniert ist und welche Quellen die KI verwendet.' },
  { number: '04', title: 'Handlungsempfehlungen ableiten', description: 'Sie erhalten konkrete Empfehlungen für Content, Struktur, Plattformen und Sichtbarkeit.' }
]

const analyseAreas = [
  {
    icon: 'i-lucide-scan-eye',
    title: 'Sichtbarkeit & Erwähnungen',
    points: [
      'Wie oft wird Ihr Unternehmen in KI-Antworten erwähnt?',
      'Wie sichtbar sind Ihre Mitbewerber?',
      'Erscheinen Sie bei relevanten Themen überhaupt?'
    ]
  },
  {
    icon: 'i-lucide-compass',
    title: 'Positionierung & Wahrnehmung',
    points: [
      'Wird Ihre Marke aktiv empfohlen oder nur nebenbei erwähnt?',
      'Welche Stimmung herrscht rund um Ihr Unternehmen?',
      'Welche Themen werden mit Ihrer Marke verbunden?'
    ]
  },
  {
    icon: 'i-lucide-link',
    title: 'Quellen & Plattformen',
    points: [
      'Welche Webseiten nutzt die KI als Informationsquelle?',
      'Wie stark sind Booking-Plattformen, Branchenportale oder externe Websites?',
      'Wie präsent ist Ihre eigene Website wirklich?'
    ]
  }
]

const deliverables = [
  { icon: 'i-lucide-bar-chart-3', title: 'Individuelle Sichtbarkeitsanalyse', description: 'Auswertung Ihrer Präsenz in ChatGPT, Gemini, Google AI und weiteren KI-Systemen.' },
  { icon: 'i-lucide-git-compare', title: 'Vergleich mit Mitbewerbern', description: 'Analyse Ihrer Positionierung im direkten Wettbewerbsumfeld.' },
  { icon: 'i-lucide-message-circle-question', title: 'Themen- & Promptanalyse', description: 'Welche Themen funktionieren bereits gut – und bei welchen Suchanfragen fehlt Sichtbarkeit?' },
  { icon: 'i-lucide-file-code', title: 'ONPAGE-Handlungsempfehlungen', description: 'Empfehlungen zu Content, Struktur, interner Verlinkung, Themenaufbau und KI-verständlichen Inhalten.' },
  { icon: 'i-lucide-external-link', title: 'OFFPAGE-Empfehlungen', description: 'Optimierungspotenziale auf externen Plattformen, Branchenverzeichnissen, Bewertungsseiten und relevanten Quellen.' },
  { icon: 'i-lucide-list-checks', title: 'Priorisierte Maßnahmen', description: 'Klare Handlungsempfehlungen mit Fokus auf Sichtbarkeit, Relevanz und Reichweite.' }
]
</script>

<template>
  <div>
    <!-- Hero -->
    <UPageHero
      :ui="{
        container: 'relative z-10 lg:py-20',
        wrapper: 'flex flex-col items-center',
        title: 'sm:text-6xl lg:text-7xl xl:text-[80px] tracking-tighter leading-[1.05]',
        description: 'mt-5 max-w-2xl mx-auto text-base sm:text-lg leading-relaxed text-default',
        links: 'gap-3'
      }"
    >
      <template #top>
        <div class="pointer-events-none absolute top-0 left-1/2 -translate-x-1/2 w-2/3 h-1/2" style="background: radial-gradient(ellipse at center, rgba(6, 182, 212, 0.08) 0%, transparent 70%);" />
      </template>

      <template #headline>
        <Motion v-bind="enterMotion(0.2)">
          <UBadge
            color="neutral"
            variant="soft"
            label="KI-Sichtbarkeit analysieren"
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
          Von null auf sichtbar in
          <span
            class="animate-shimmer bg-size-[200%_auto] bg-clip-text text-transparent"
            :style="{
              backgroundImage: 'linear-gradient(135deg, var(--color-cyan-400), var(--color-sky-400), var(--color-cyan-300), var(--color-sky-500))',
              animationDuration: '8s'
            }"
          >
            ChatGPT & Co.
          </span>
        </Motion>
      </template>

      <template #description>
        <Motion
          as="span"
          v-bind="enterMotion(0.5)"
          class="inline-block"
        >
          KI-Sichtbarkeit wird zum neuen Google-Ranking. KI Visibility zeigt Ihnen, wie sichtbar Ihr Unternehmen in ChatGPT, Gemini, Google AI und anderen KI-Systemen wirklich ist – und warum Mitbewerber möglicherweise häufiger empfohlen werden als Sie.
        </Motion>
      </template>

      <template #links>
        <Motion v-bind="enterMotion(0.65)">
          <div class="flex flex-wrap gap-3">
            <UButton
              label="Jetzt Analyse anfragen"
              class="bg-gradient-to-r from-cyan-500 to-sky-500 hover:from-cyan-400 hover:to-sky-400 text-white shadow-[0_0_20px_rgba(6,182,212,0.25)] hover:shadow-[0_0_30px_rgba(6,182,212,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
              size="xl"
              to="#kontakt"
            />
            <UButton
              label="Demo ansehen"
              color="neutral"
              variant="soft"
              size="xl"
              to="#so-funktionierts"
            />
          </div>
        </Motion>
      </template>
    </UPageHero>

    <!-- Intro -->
    <UPageSection
      :ui="{
        root: 'py-8 sm:py-12',
        container: 'max-w-3xl text-center'
      }"
    >
      <Motion v-bind="scrollMotion()">
        <p class="text-lg leading-relaxed text-dimmed">
          Wir analysieren, wie KI-Modelle Ihre Marke wahrnehmen, welche Themen mit Ihrem Unternehmen verbunden werden und wo Potenziale für mehr Sichtbarkeit liegen. Aus Daten werden konkrete Handlungsempfehlungen – für mehr Erwähnungen, mehr Relevanz und mehr Anfragen.
        </p>
      </Motion>
    </UPageSection>

    <!-- Warum KI Visibility -->
    <UPageSection
      id="warum"
      :ui="{
        root: 'py-12 sm:py-16 scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-cyan-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-xl mx-auto',
        description: 'max-w-xl mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Warum KI Visibility?
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          Sichtbar sein, wo morgen gesucht wird.
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          Menschen suchen nicht mehr nur über Google. Sie fragen ChatGPT nach Hotels, Dienstleistern, Produkten oder Empfehlungen. Genau dort entscheidet sich zunehmend, wer sichtbar ist – und wer nicht.
        </Motion>
      </template>

      <Motion v-bind="scrollMotion(0.3)">
        <p class="text-center text-dimmed leading-relaxed max-w-2xl mx-auto mt-4">
          Mit KI Visibility analysieren wir, wie Ihr Unternehmen in modernen KI-Systemen dargestellt wird und welche Faktoren Ihre Präsenz beeinflussen. Dabei vergleichen wir Ihre Sichtbarkeit direkt mit relevanten Mitbewerbern und zeigen auf, wo Ihre Chancen liegen.
        </p>
      </Motion>
    </UPageSection>

    <!-- Vorteile -->
    <UPageSection
      id="vorteile"
      :ui="{
        root: 'py-12 sm:py-16 scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-cyan-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Ihre Vorteile
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          Ihre Vorteile auf einen Blick
        </Motion>
      </template>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 mt-2">
        <Motion
          v-for="(item, index) in vorteile"
          :key="item.title"
          v-bind="staggerMotion(index)"
        >
          <div class="rounded-2xl border border-default bg-default p-6 h-full hover:border-cyan-500/30 transition-colors duration-300">
            <div class="mb-4 flex size-10 items-center justify-center rounded-lg bg-cyan-500/10">
              <UIcon :name="item.icon" class="size-5 text-cyan-400" />
            </div>
            <h3 class="text-sm font-semibold tracking-tight mb-1.5">
              {{ item.title }}
            </h3>
            <p class="text-sm text-dimmed leading-relaxed">
              {{ item.description }}
            </p>
          </div>
        </Motion>
      </div>
    </UPageSection>

    <!-- Einsatzbereiche -->
    <UPageSection
      id="einsatzbereiche"
      :ui="{
        root: 'py-12 sm:py-16 scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-cyan-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-xl mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Einsatzbereiche
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          Typische Einsatzbereiche
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          KI Visibility eignet sich besonders für Unternehmen mit hohem Wettbewerbsdruck und starker digitaler Sichtbarkeit.
        </Motion>
      </template>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 mt-2">
        <Motion
          v-for="(item, index) in useCases"
          :key="item.title"
          v-bind="staggerMotion(index)"
        >
          <div class="rounded-2xl border border-default bg-default p-8 h-full hover:border-cyan-500/30 transition-colors duration-300">
            <div class="mb-4 flex size-12 items-center justify-center rounded-xl bg-cyan-500/10">
              <UIcon :name="item.icon" class="size-6 text-cyan-400" />
            </div>
            <h3 class="text-lg font-semibold tracking-tight mb-4">
              {{ item.title }}
            </h3>
            <ul class="space-y-2">
              <li
                v-for="q in item.questions"
                :key="q"
                class="flex items-start gap-2 text-sm text-dimmed leading-relaxed"
              >
                <UIcon name="i-lucide-help-circle" class="size-4 shrink-0 text-sky-400 mt-0.5" />
                <span>{{ q }}</span>
              </li>
            </ul>
          </div>
        </Motion>
      </div>
    </UPageSection>

    <!-- So funktioniert's -->
    <UPageSection
      id="so-funktionierts"
      :ui="{
        root: 'py-12 sm:py-16 scroll-mt-(--ui-header-height)',
        container: 'max-w-4xl',
        headline: 'font-mono font-medium text-xs text-cyan-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-xl mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          So funktioniert's
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          In vier Schritten zur KI-Sichtbarkeit
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          KI Visibility analysiert Ihre digitale Präsenz aus Sicht moderner KI-Systeme.
        </Motion>
      </template>

      <div class="grid grid-cols-1 sm:grid-cols-2 gap-6 mt-2">
        <Motion
          v-for="(step, index) in steps"
          :key="step.number"
          v-bind="staggerMotion(index)"
        >
          <div class="rounded-2xl border border-default bg-default p-6 h-full hover:border-cyan-500/30 transition-colors duration-300 relative overflow-hidden">
            <span class="absolute top-4 right-4 text-4xl font-black text-cyan-500/10 font-mono">
              {{ step.number }}
            </span>
            <h3 class="text-base font-semibold tracking-tight mb-2">
              {{ step.title }}
            </h3>
            <p class="text-sm text-dimmed leading-relaxed">
              {{ step.description }}
            </p>
          </div>
        </Motion>
      </div>
    </UPageSection>

    <!-- Was analysiert KI Visibility? -->
    <UPageSection
      id="analyse"
      :ui="{
        root: 'py-12 sm:py-16 scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-cyan-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-xl mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Analyse
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          Was analysiert KI Visibility?
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          Nicht nur Rankings sind entscheidend. Moderne KI-Systeme bewerten Marken ganzheitlich.
        </Motion>
      </template>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 mt-2">
        <Motion
          v-for="(area, index) in analyseAreas"
          :key="area.title"
          v-bind="staggerMotion(index)"
        >
          <div class="rounded-2xl border border-default bg-default p-8 h-full hover:border-cyan-500/30 transition-colors duration-300">
            <div class="mb-4 flex size-12 items-center justify-center rounded-xl bg-cyan-500/10">
              <UIcon :name="area.icon" class="size-6 text-cyan-400" />
            </div>
            <h3 class="text-lg font-semibold tracking-tight mb-4">
              {{ area.title }}
            </h3>
            <ul class="space-y-2">
              <li
                v-for="point in area.points"
                :key="point"
                class="flex items-start gap-2 text-sm text-dimmed leading-relaxed"
              >
                <UIcon name="i-lucide-check" class="size-4 shrink-0 text-sky-400 mt-0.5" />
                <span>{{ point }}</span>
              </li>
            </ul>
          </div>
        </Motion>
      </div>
    </UPageSection>

    <!-- Das erhalten Sie -->
    <UPageSection
      id="ergebnis"
      :ui="{
        root: 'py-12 sm:py-16 scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-cyan-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-xl mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Ergebnis
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          Das erhalten Sie nach der Analyse
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          Konkrete Erkenntnisse und umsetzbare Empfehlungen – keine allgemeinen SEO-Floskeln.
        </Motion>
      </template>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 mt-2">
        <Motion
          v-for="(item, index) in deliverables"
          :key="item.title"
          v-bind="staggerMotion(index)"
        >
          <div class="rounded-2xl border border-default bg-default p-6 h-full hover:border-cyan-500/30 transition-colors duration-300">
            <div class="mb-4 flex size-10 items-center justify-center rounded-lg bg-cyan-500/10">
              <UIcon :name="item.icon" class="size-5 text-cyan-400" />
            </div>
            <h3 class="text-sm font-semibold tracking-tight mb-1.5">
              {{ item.title }}
            </h3>
            <p class="text-sm text-dimmed leading-relaxed">
              {{ item.description }}
            </p>
          </div>
        </Motion>
      </div>
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
        <div class="pointer-events-none absolute bottom-0 left-1/2 -translate-x-1/2 w-2/3 h-1/2" style="background: radial-gradient(ellipse at center, rgba(6, 182, 212, 0.06) 0%, transparent 70%);" />
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block text-4xl lg:text-5xl tracking-tighter">
          Bereit für mehr Sichtbarkeit in KI-Systemen?
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block max-w-lg mx-auto leading-relaxed text-dimmed">
          Die Art, wie Menschen suchen, verändert sich gerade grundlegend. Unternehmen, die heute sichtbar sind, werden morgen empfohlen. Nutzen Sie die Chancen moderner KI-Systeme – bevor es Ihre Mitbewerber tun.
        </Motion>
      </template>

      <template #links>
        <Motion
          class="w-full max-w-md mx-auto mt-8"
          v-bind="scrollMotion(0.2)"
        >
          <form class="flex flex-col gap-4" @submit.prevent>
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
              placeholder="Unternehmen"
              size="xl"
              :ui="{ base: 'bg-elevated' }"
            />
            <UInput
              placeholder="Website-URL"
              size="xl"
              :ui="{ base: 'bg-elevated' }"
            />
            <UTextarea
              placeholder="Ihre Nachricht (optional)"
              :rows="3"
              :ui="{ base: 'bg-elevated' }"
            />
            <UButton
              label="Jetzt KI Visibility Analyse anfragen"
              class="bg-gradient-to-r from-cyan-500 to-sky-500 hover:from-cyan-400 hover:to-sky-400 text-white shadow-[0_0_20px_rgba(6,182,212,0.25)] hover:shadow-[0_0_30px_rgba(6,182,212,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
              size="xl"
              block
              type="submit"
            />
            <p class="text-xs text-dimmed text-center">
              Wir melden uns innerhalb von 48h mit einem individuellen Angebot.
            </p>
          </form>
        </Motion>
      </template>
    </UPageCTA>
  </div>
</template>
