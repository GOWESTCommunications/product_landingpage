<script setup lang="ts">
definePageMeta({
})

useSeoMeta({
  title: 'KInsights – Sichtbar in ChatGPT, Gemini & Co.',
  ogTitle: 'KInsights – Sichtbar in ChatGPT, Gemini & Co.',
  description: 'KInsights zeigt, wie sichtbar Ihr Unternehmen in ChatGPT, Gemini, Google AI und anderen KI-Systemen ist – mit konkreten Handlungsempfehlungen.',
  ogDescription: 'KInsights zeigt, wie sichtbar Ihr Unternehmen in ChatGPT, Gemini, Google AI und anderen KI-Systemen ist – mit konkreten Handlungsempfehlungen.'
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

// Report visualization data
const presenceData = { present: 38, notPresent: 62 }

const competitivePresence = [
  { name: 'Hotel Sonnenberg', share: 18, isOwn: true },
  { name: 'Alpenresort Bergblick', share: 26, isOwn: false },
  { name: 'Panorama Lodge', share: 21, isOwn: false },
  { name: 'Wellness Hotel Talgrund', share: 14, isOwn: false },
  { name: 'Andere', share: 21, isOwn: false }
]

const citations = {
  brand: 24,
  thirdParty: 31,
  competitor: 7
}

const topicsOverview = [
  { topic: 'Wellnesshotel Tirol', prompts: 32, presence: 72, citations: 14 },
  { topic: 'Familienurlaub Alpen', prompts: 28, presence: 46, citations: 11 },
  { topic: 'Wanderhotel Österreich', prompts: 24, presence: 38, citations: 9 },
  { topic: 'Romantikhotel Innsbruck', prompts: 22, presence: 27, citations: 8 },
  { topic: 'Skihotel Tirol', prompts: 26, presence: 19, citations: 4 },
  { topic: 'Nachhaltiges Hotel', prompts: 16, presence: 12, citations: 2 }
]

</script>

<template>
  <div class="relative">
    <!-- Background dot grid overlay -->
    <div
      class="pointer-events-none fixed inset-0 opacity-[0.03] z-0"
      style="background-image: radial-gradient(rgba(6, 182, 212, 0.8) 1px, transparent 1px); background-size: 32px 32px;"
    />

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
        <div class="pointer-events-none absolute top-0 left-1/2 -translate-x-1/2 w-2/3 h-1/2" style="background: radial-gradient(ellipse at center, rgba(6, 182, 212, 0.12) 0%, transparent 70%);" />
        <div class="pointer-events-none absolute -top-20 -left-32 w-[400px] h-[400px] rounded-full blur-[100px] bg-cyan-500/[0.07]" />
        <div class="pointer-events-none absolute -top-10 -right-40 w-[300px] h-[300px] rounded-full blur-[80px] bg-sky-500/[0.06]" />
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
          KI-Sichtbarkeit wird zum neuen Google-Ranking. KInsights zeigt Ihnen, wie sichtbar Ihr Unternehmen in ChatGPT, Gemini, Google AI und anderen KI-Systemen wirklich ist – und warum Mitbewerber möglicherweise häufiger empfohlen werden als Sie.
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

    <!-- Warum KInsights -->
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
          Warum KInsights?
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
          Mit KInsights analysieren wir, wie Ihr Unternehmen in modernen KI-Systemen dargestellt wird und welche Faktoren Ihre Präsenz beeinflussen. Dabei vergleichen wir Ihre Sichtbarkeit direkt mit relevanten Mitbewerbern und zeigen auf, wo Ihre Chancen liegen.
        </p>
      </Motion>
    </UPageSection>

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-48 right-[-5%] w-[600px] h-[600px] rounded-full blur-[100px] bg-cyan-500/[0.08]" />
      <div class="absolute -top-20 left-[-10%] w-[350px] h-[350px] rounded-full blur-[80px] bg-sky-400/[0.06]" />
    </div>

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
          <div
            class="rounded-2xl border border-default bg-default p-6 h-full hover:border-cyan-500/30 transition-colors duration-300"
            style="background-image: linear-gradient(to top, rgba(6, 182, 212, 0.07) 0%, transparent 60%)"
          >
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

      <Motion v-bind="scrollMotion(0.4)">
        <div class="flex justify-center mt-10">
          <UButton
            label="Jetzt KI-Sichtbarkeit prüfen"
            class="bg-gradient-to-r from-cyan-500 to-sky-500 hover:from-cyan-400 hover:to-sky-400 text-white shadow-[0_0_20px_rgba(6,182,212,0.25)] hover:shadow-[0_0_30px_rgba(6,182,212,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
            size="xl"
            to="#kontakt"
          />
        </div>
      </Motion>
    </UPageSection>

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-48 left-[-8%] w-[700px] h-[500px] rounded-full blur-[120px] bg-sky-500/[0.07]" />
      <div class="absolute -top-20 right-[5%] w-[300px] h-[300px] rounded-full blur-[80px] bg-cyan-400/[0.05]" />
    </div>

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
          KInsights eignet sich besonders für Unternehmen mit hohem Wettbewerbsdruck und starker digitaler Sichtbarkeit.
        </Motion>
      </template>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 mt-2">
        <Motion
          v-for="(item, index) in useCases"
          :key="item.title"
          v-bind="staggerMotion(index)"
        >
          <div
            class="rounded-2xl border border-cyan-500/[0.12] bg-default p-8 h-full hover:border-cyan-500/30 hover:shadow-[0_0_30px_rgba(6,182,212,0.1)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(6, 182, 212, 0.1) 0%, rgba(6, 182, 212, 0.02) 50%, transparent 80%)"
          >
            <div class="mb-4 flex size-12 items-center justify-center rounded-xl bg-cyan-500/15 ring-1 ring-cyan-500/10">
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

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-40 right-[5%] w-[500px] h-[400px] rounded-full blur-[100px] bg-cyan-400/[0.06]" />
    </div>

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
          KInsights analysiert Ihre digitale Präsenz aus Sicht moderner KI-Systeme.
        </Motion>
      </template>

      <div class="grid grid-cols-1 sm:grid-cols-2 gap-6 mt-2">
        <Motion
          v-for="(step, index) in steps"
          :key="step.number"
          v-bind="staggerMotion(index)"
        >
          <div
            class="rounded-2xl border border-cyan-500/[0.12] bg-default p-6 h-full hover:border-cyan-500/30 hover:shadow-[0_0_30px_rgba(6,182,212,0.1)] transition-all duration-300 relative overflow-hidden"
            style="background-image: linear-gradient(to top, rgba(6, 182, 212, 0.1) 0%, rgba(6, 182, 212, 0.02) 50%, transparent 80%)"
          >
            <span class="absolute top-4 right-4 text-4xl font-black text-cyan-500/15 font-mono">
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

      <Motion v-bind="scrollMotion(0.4)">
        <div class="flex flex-wrap justify-center gap-3 mt-10">
          <UButton
            label="Analyse starten"
            class="bg-gradient-to-r from-cyan-500 to-sky-500 hover:from-cyan-400 hover:to-sky-400 text-white shadow-[0_0_20px_rgba(6,182,212,0.25)] hover:shadow-[0_0_30px_rgba(6,182,212,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
            size="lg"
            to="#kontakt"
          />
          <UButton
            label="Was wird analysiert?"
            size="lg"
            color="neutral"
            variant="soft"
            to="#analyse"
          />
        </div>
      </Motion>
    </UPageSection>

    <!-- Report Visualization -->
    <UPageSection
      id="report"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-6xl',
        headline: 'font-mono font-medium text-xs text-cyan-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-md mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Report-Vorschau
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          So sieht Ihr KInsights Report aus.
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          Individuelle KI-Sichtbarkeitsanalyse – datenbasiert und handlungsorientiert.
        </Motion>
      </template>

      <Motion v-bind="scrollMotion(0.3)">
        <div
          class="rounded-2xl border border-cyan-500/[0.12] bg-default overflow-hidden shadow-2xl shadow-cyan-500/[0.05]"
          style="background-image: linear-gradient(to top, rgba(6, 182, 212, 0.06) 0%, transparent 40%)"
        >
          <!-- Report Header -->
          <div class="flex items-center justify-between px-6 py-4 border-b border-cyan-500/10">
            <div class="flex items-center gap-3">
              <div class="flex size-8 items-center justify-center rounded-lg bg-cyan-500/15">
                <UIcon name="i-lucide-scan-eye" class="size-4 text-cyan-400" />
              </div>
              <div>
                <p class="text-sm font-semibold tracking-tight">Hotel Sonnenberg</p>
                <p class="text-[11px] text-dimmed font-mono">AI Visibility Report · Mai 2026</p>
              </div>
            </div>
            <span class="inline-flex items-center gap-1.5 px-2.5 py-1 rounded-md bg-cyan-500/10 text-[10px] font-mono text-cyan-400">
              <UIcon name="i-lucide-file-text" class="size-3" />
              PDF Export
            </span>
          </div>

          <!-- Stat Figures Row -->
          <div class="grid grid-cols-3 gap-px bg-cyan-500/5">
            <div class="bg-default px-5 py-5">
              <p class="text-[11px] text-dimmed font-mono uppercase tracking-wider mb-1">Custom Prompts</p>
              <p class="text-2xl sm:text-3xl font-bold tracking-tight text-default leading-none">148</p>
            </div>
            <div class="bg-default px-5 py-5">
              <p class="text-[11px] text-dimmed font-mono uppercase tracking-wider mb-1">Responses</p>
              <p class="text-2xl sm:text-3xl font-bold tracking-tight text-default leading-none">592</p>
            </div>
            <div class="bg-default px-5 py-5">
              <p class="text-[11px] text-dimmed font-mono uppercase tracking-wider mb-1">Platforms</p>
              <div class="flex items-center gap-3 mt-1">
                <span class="flex items-center gap-1.5 text-xs font-medium text-default">
                  <UIcon name="i-lucide-message-square" class="size-4 text-cyan-400" />
                  ChatGPT
                </span>
                <span class="flex items-center gap-1.5 text-xs font-medium text-default">
                  <UIcon name="i-lucide-sparkles" class="size-4 text-sky-400" />
                  Gemini
                </span>
                <span class="flex items-center gap-1.5 text-xs font-medium text-default">
                  <UIcon name="i-lucide-search" class="size-4 text-violet-400" />
                  Perplexity
                </span>
                <span class="flex items-center gap-1.5 text-xs font-medium text-default">
                  <UIcon name="i-lucide-bot" class="size-4 text-blue-400" />
                  Copilot
                </span>
              </div>
            </div>
          </div>

          <!-- Presence Pie + Competitive Presence -->
          <div class="grid grid-cols-1 lg:grid-cols-3 gap-px bg-cyan-500/5">
            <!-- AI Presence (Pie Chart) -->
            <div class="bg-default p-6 flex flex-col items-center">
              <div class="w-full mb-4">
                <h4 class="text-sm font-semibold tracking-tight">AI Presence</h4>
                <p class="text-[11px] text-dimmed">Präsent in KI-Antworten</p>
              </div>

              <div class="relative size-36 mb-4">
                <svg viewBox="0 0 120 120" class="w-full h-full -rotate-90">
                  <!-- Not present arc -->
                  <circle cx="60" cy="60" r="48" fill="none" stroke="currentColor" class="text-cyan-500/10" stroke-width="18" />
                  <!-- Present arc -->
                  <circle
                    cx="60" cy="60" r="48" fill="none" stroke="url(#presenceGrad)" stroke-width="18"
                    stroke-linecap="round"
                    :stroke-dasharray="2 * Math.PI * 48"
                    :stroke-dashoffset="2 * Math.PI * 48 * (1 - presenceData.present / 100)"
                  />
                  <defs>
                    <linearGradient id="presenceGrad" x1="0%" y1="0%" x2="100%" y2="0%">
                      <stop offset="0%" stop-color="#06b6d4" />
                      <stop offset="100%" stop-color="#0ea5e9" />
                    </linearGradient>
                  </defs>
                </svg>
                <div class="absolute inset-0 flex flex-col items-center justify-center">
                  <span class="text-2xl font-bold tracking-tight">{{ presenceData.present }}%</span>
                  <span class="text-[10px] text-dimmed font-mono">Present</span>
                </div>
              </div>

              <div class="flex items-center gap-4 text-[11px]">
                <span class="flex items-center gap-1.5">
                  <span class="size-2 rounded-full bg-cyan-400" />
                  <span class="text-dimmed">Ja ({{ presenceData.present }}%)</span>
                </span>
                <span class="flex items-center gap-1.5">
                  <span class="size-2 rounded-full bg-cyan-500/10" />
                  <span class="text-dimmed">Nein ({{ presenceData.notPresent }}%)</span>
                </span>
              </div>
            </div>

            <!-- Competitive Presence -->
            <div class="lg:col-span-2 bg-default p-6">
              <div class="flex items-center justify-between mb-4">
                <div>
                  <h4 class="text-sm font-semibold tracking-tight">Competitive Presence</h4>
                  <p class="text-[11px] text-dimmed">Anteil an KI-Erwähnungen im Wettbewerb</p>
                </div>
                <span class="text-[10px] font-mono text-dimmed px-2 py-1 rounded bg-cyan-500/5">% of total</span>
              </div>

              <div class="space-y-3.5">
                <div v-for="comp in competitivePresence" :key="comp.name">
                  <div class="flex items-center justify-between mb-1.5">
                    <span class="text-xs font-medium" :class="comp.isOwn ? 'text-cyan-400' : 'text-default'">
                      {{ comp.isOwn ? '● ' : '' }}{{ comp.name }}
                    </span>
                    <span class="text-xs font-mono" :class="comp.isOwn ? 'text-cyan-400 font-bold' : 'text-dimmed'">{{ comp.share }}%</span>
                  </div>
                  <div class="h-2 rounded-full bg-cyan-500/5 overflow-hidden">
                    <div
                      class="h-full rounded-full transition-all duration-700"
                      :style="{ width: comp.share + '%' }"
                      :class="comp.isOwn ? 'bg-gradient-to-r from-cyan-500 to-sky-400' : 'bg-white/10'"
                    />
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Citations -->
          <div class="grid grid-cols-1 gap-px bg-cyan-500/5">
            <div class="bg-default p-6">
              <div class="mb-4">
                <h4 class="text-sm font-semibold tracking-tight">Citations</h4>
                <p class="text-[11px] text-dimmed">Quellen in KI-Antworten</p>
              </div>

              <div class="space-y-4">
                <div class="p-3.5 rounded-xl bg-cyan-500/5">
                  <div class="flex items-center justify-between mb-1">
                    <span class="text-xs font-medium text-cyan-400">Your Brand</span>
                    <span class="text-lg font-bold font-mono text-cyan-400">{{ citations.brand }}</span>
                  </div>
                  <div class="h-1.5 rounded-full bg-cyan-500/10 overflow-hidden">
                    <div class="h-full rounded-full bg-cyan-400" :style="{ width: (citations.brand / (citations.brand + citations.thirdParty + citations.competitor) * 100) + '%' }" />
                  </div>
                </div>

                <div class="p-3.5 rounded-xl bg-sky-500/5">
                  <div class="flex items-center justify-between mb-1">
                    <span class="text-xs font-medium text-sky-400">Third Party</span>
                    <span class="text-lg font-bold font-mono text-sky-400">{{ citations.thirdParty }}</span>
                  </div>
                  <div class="h-1.5 rounded-full bg-sky-500/10 overflow-hidden">
                    <div class="h-full rounded-full bg-sky-400" :style="{ width: (citations.thirdParty / (citations.brand + citations.thirdParty + citations.competitor) * 100) + '%' }" />
                  </div>
                </div>

                <div class="p-3.5 rounded-xl bg-amber-500/5">
                  <div class="flex items-center justify-between mb-1">
                    <span class="text-xs font-medium text-amber-400">Competitors</span>
                    <span class="text-lg font-bold font-mono text-amber-400">{{ citations.competitor }}</span>
                  </div>
                  <div class="h-1.5 rounded-full bg-amber-500/10 overflow-hidden">
                    <div class="h-full rounded-full bg-amber-400" :style="{ width: (citations.competitor / (citations.brand + citations.thirdParty + citations.competitor) * 100) + '%' }" />
                  </div>
                </div>
              </div>

              <div class="mt-4 pt-3 border-t border-cyan-500/5">
                <div class="flex items-center justify-between text-[11px]">
                  <span class="text-dimmed font-mono">Total Citations</span>
                  <span class="font-mono font-bold">{{ citations.brand + citations.thirdParty + citations.competitor }}</span>
                </div>
              </div>
            </div>
          </div>

          <!-- Topics Overview -->
          <div class="bg-default p-6 border-t border-cyan-500/5">
            <div class="mb-4">
              <h4 class="text-sm font-semibold tracking-tight">Topics Overview</h4>
              <p class="text-[11px] text-dimmed">Prompts, Präsenz und Zitierungen pro Thema</p>
            </div>

            <div class="overflow-hidden rounded-xl border border-cyan-500/10">
              <table class="w-full text-left">
                <thead>
                  <tr class="bg-cyan-500/5">
                    <th class="px-4 py-2.5 text-[11px] font-mono uppercase tracking-wider text-dimmed">Topic</th>
                    <th class="px-4 py-2.5 text-[11px] font-mono uppercase tracking-wider text-dimmed text-right">Prompts</th>
                    <th class="px-4 py-2.5 text-[11px] font-mono uppercase tracking-wider text-dimmed text-right">Presence</th>
                    <th class="px-4 py-2.5 text-[11px] font-mono uppercase tracking-wider text-dimmed text-right">Citations</th>
                  </tr>
                </thead>
                <tbody>
                  <tr
                    v-for="topic in topicsOverview"
                    :key="topic.topic"
                    class="border-t border-cyan-500/5"
                  >
                    <td class="px-4 py-2.5 text-sm font-medium">{{ topic.topic }}</td>
                    <td class="px-4 py-2.5 text-sm text-right font-mono text-dimmed">{{ topic.prompts }}</td>
                    <td class="px-4 py-2.5 text-right">
                      <span
                        class="text-sm font-mono font-bold"
                        :class="topic.presence >= 60 ? 'text-cyan-400' : topic.presence >= 30 ? 'text-sky-400' : 'text-amber-400'"
                      >{{ topic.presence }}%</span>
                    </td>
                    <td class="px-4 py-2.5 text-sm text-right font-mono text-dimmed">{{ topic.citations }}</td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>

          <!-- Report Footer -->
          <div class="flex items-center justify-between px-6 py-3 border-t border-cyan-500/10 bg-cyan-500/[0.02]">
            <span class="text-[10px] text-dimmed font-mono">KInsights × GO WEST Communications</span>
            <span class="text-[10px] text-dimmed font-mono">Beispieldaten – Hotel Sonnenberg</span>
          </div>
        </div>

        <p class="text-center text-xs text-dimmed mt-4">
          Beispiel-Report mit fiktiven Daten – Ihr Report wird individuell auf Ihr Unternehmen zugeschnitten.
        </p>
      </Motion>
    </UPageSection>

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-48 left-[10%] w-[500px] h-[500px] rounded-full blur-[100px] bg-cyan-500/[0.08]" />
      <div class="absolute -top-20 right-[-3%] w-[300px] h-[300px] rounded-full blur-[80px] bg-sky-400/[0.05]" />
    </div>

    <!-- Was analysiert KInsights? -->
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
          Was analysiert KInsights?
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
          <div
            class="rounded-2xl border border-cyan-500/[0.12] bg-default p-8 h-full hover:border-cyan-500/30 hover:shadow-[0_0_30px_rgba(6,182,212,0.1)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(6, 182, 212, 0.1) 0%, rgba(6, 182, 212, 0.02) 50%, transparent 80%)"
          >
            <div class="mb-4 flex size-12 items-center justify-center rounded-xl bg-cyan-500/15 ring-1 ring-cyan-500/10">
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

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-32 right-[15%] w-[400px] h-[400px] rounded-full blur-[100px] bg-sky-500/[0.06]" />
    </div>

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
          <div
            class="rounded-2xl border border-default bg-default p-6 h-full hover:border-cyan-500/30 transition-colors duration-300"
            style="background-image: linear-gradient(to top, rgba(6, 182, 212, 0.07) 0%, transparent 60%)"
          >
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

      <Motion v-bind="scrollMotion(0.4)">
        <div class="flex justify-center mt-10">
          <UButton
            label="Kostenlose Erstberatung anfragen"
            class="bg-gradient-to-r from-cyan-500 to-sky-500 hover:from-cyan-400 hover:to-sky-400 text-white shadow-[0_0_20px_rgba(6,182,212,0.25)] hover:shadow-[0_0_30px_rgba(6,182,212,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
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
        <div class="pointer-events-none absolute bottom-0 left-1/2 -translate-x-1/2 w-2/3 h-1/2" style="background: radial-gradient(ellipse at center, rgba(6, 182, 212, 0.12) 0%, transparent 70%);" />
        <div class="pointer-events-none absolute -bottom-20 -left-20 w-[350px] h-[350px] rounded-full blur-[80px] bg-cyan-500/[0.06]" />
        <div class="pointer-events-none absolute -bottom-10 -right-32 w-[300px] h-[300px] rounded-full blur-[80px] bg-sky-500/[0.05]" />
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
              label="Jetzt KInsights Analyse anfragen"
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
