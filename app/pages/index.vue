<script setup lang="ts">
definePageMeta({
})

useSeoMeta({
  title: 'Unsere Produkte – Digitale Tools für mehr Performance',
  ogTitle: 'Unsere Produkte – Digitale Tools für mehr Performance',
  description: 'PromoHero, TriGuest und TopAccess: Drei spezialisierte Tools für Conversion-Optimierung, Booking Analytics und Barrierefreiheit.',
  ogDescription: 'PromoHero, TriGuest und TopAccess: Drei spezialisierte Tools für Conversion-Optimierung, Booking Analytics und Barrierefreiheit.'
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
    transition: { duration: 0.5, delay: index * 0.12 }
  }
}

const products = [
  {
    name: 'PromoHero',
    tagline: 'Aus Absprüngen Abschlüsse machen',
    description: 'Exit-Intent Overlays, die im perfekten Moment ein starkes Angebot ausspielen. Mehr Conversions, weniger verlorene Besucher – ganz automatisch.',
    icon: 'P',
    iconClass: 'bg-gradient-to-br from-violet-500 to-fuchsia-500',
    accentClass: 'text-fuchsia-400',
    borderHover: 'hover:border-fuchsia-500/40',
    to: '/promohero',
    features: ['Exit-Intent-Technologie', 'Individuelle Overlay-Designs', 'Performance-Tracking in Echtzeit']
  },
  {
    name: 'TriGuest',
    tagline: 'Booking Analytics für den Tourismus',
    description: 'Fundierte Antworten auf essenzielle Erfolgsfragen rund um das Buchungsverhalten. E-Commerce-Tracking für Seekda, OnePageBooking und Vioma.',
    icon: 'T',
    iconClass: 'bg-teal-500',
    accentClass: 'text-teal-400',
    borderHover: 'hover:border-teal-500/40',
    to: '/triguest',
    features: ['Gästeverhalten analysieren', 'Marketingbudgets optimieren', 'Buchungsstrecke verbessern']
  },
  {
    name: 'TopAccess',
    tagline: 'Website für alle',
    description: 'Smartes Accessibility Widget mit KI-generierten Alt-Texten. Mehr Reichweite, bessere SEO und Barrierefreiheit – ohne Pflegeaufwand.',
    icon: 'T',
    iconClass: 'bg-gradient-to-br from-amber-500 to-orange-500',
    accentClass: 'text-amber-400',
    borderHover: 'hover:border-amber-500/40',
    to: '/topaccess',
    features: ['Accessibility Widget', 'KI-generierte Alt-Texte', 'DSGVO-konform']
  }
]

const stats = [
  { value: '3', label: 'Spezialisierte Tools', accent: 'text-fuchsia-400' },
  { value: '< 15 min', label: 'Integration', accent: 'text-teal-400' },
  { value: '100%', label: 'DSGVO-konform', accent: 'text-amber-400' },
  { value: '48h', label: 'Antwortzeit', accent: 'text-emerald-400' }
]

const values = [
  { icon: 'i-lucide-zap', title: 'Schnell integriert', description: 'Alle Tools sind in wenigen Minuten eingebunden – ohne aufwendige Entwicklung.' },
  { icon: 'i-lucide-shield-check', title: 'DSGVO-konform', description: 'Datenschutz hat Priorität. Alle Lösungen arbeiten datenschutzkonform.' },
  { icon: 'i-lucide-headset', title: 'Persönlicher Support', description: 'Individuelle Beratung und schnelle Hilfe – kein Bot, echte Menschen.' },
  { icon: 'i-lucide-settings', title: 'Individuell anpassbar', description: 'Farben, Schriften und Funktionen lassen sich an Ihr Branding anpassen.' }
]
</script>

<template>
  <div>
    <!-- Hero -->
    <UPageHero
      :ui="{
        container: 'relative z-10 lg:py-28',
        wrapper: 'flex flex-col items-center',
        title: 'sm:text-5xl lg:text-6xl xl:text-7xl tracking-tighter leading-[1.1]',
        description: 'mt-5 max-w-2xl mx-auto text-base sm:text-lg leading-relaxed text-default',
        links: 'gap-3'
      }"
    >
      <template #top>
        <Motion v-bind="staggerMotion(0)">

        </Motion>
        <GradientGlow class="top-0 w-2/3 h-1/2" />
      </template>

      <template #headline>
        <Motion v-bind="enterMotion(0.2)">
          <UBadge
            color="neutral"
            variant="soft"
            label="Digitale Tools für mehr Performance"
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
          Unsere
          <span
            class="animate-shimmer bg-size-[200%_auto] bg-clip-text text-transparent"
            :style="{
              backgroundImage: 'linear-gradient(135deg, var(--color-violet-400), var(--color-teal-400), var(--color-amber-400), var(--color-violet-400))',
              animationDuration: '12s'
            }"
          >
            Produkte.
          </span>
        </Motion>
      </template>

      <template #description>
        <Motion
          as="span"
          v-bind="enterMotion(0.5)"
          class="inline-block"
        >
          Drei spezialisierte Tools, ein gemeinsames Ziel: Ihre digitale Performance messbar steigern. Von Conversion-Optimierung über Booking Analytics bis Barrierefreiheit.
        </Motion>
      </template>
    </UPageHero>

    <!-- Products -->
    <UPageSection
      :ui="{
        container: 'max-w-5xl'
      }"
    >
      <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
        <Motion
          v-for="(product, index) in products"
          :key="product.name"
          v-bind="staggerMotion(index)"
        >
          <NuxtLink
            :to="product.to"
            class="block group h-full"
          >
            <div
              :class="['rounded-2xl border border-default bg-default p-8 h-full transition-all duration-300 group-hover:-translate-y-1', product.borderHover]"
            >
              <!-- Logo -->
              <div class="flex items-center gap-3 mb-6">
                <span :class="['flex items-center flex-shrink-0 justify-center size-10 rounded-xl text-white text-base font-black', product.iconClass]">
                  {{ product.icon }}
                </span>
                <div>
                  <h3 class="text-lg font-bold tracking-tight">{{ product.name }}</h3>
                  <p :class="['text-xs font-mono uppercase tracking-wider', product.accentClass]">{{ product.tagline }}</p>
                </div>
              </div>

              <!-- Description -->
              <p class="text-sm text-dimmed leading-relaxed mb-6">
                {{ product.description }}
              </p>

              <!-- Features -->
              <ul class="space-y-2 mb-8">
                <li
                  v-for="feature in product.features"
                  :key="feature"
                  class="flex items-center gap-2 text-sm"
                >
                  <UIcon name="i-lucide-check" :class="['size-4 shrink-0', product.accentClass]" />
                  <span>{{ feature }}</span>
                </li>
              </ul>

              <!-- Link -->
              <span :class="['inline-flex items-center gap-1.5 text-sm font-medium transition-colors', product.accentClass]">
                Mehr erfahren
                <UIcon name="i-lucide-arrow-right" class="size-4 transition-transform group-hover:translate-x-1" />
              </span>
            </div>
          </NuxtLink>
        </Motion>
      </div>
    </UPageSection>

    <!-- Stats -->
    <UPageSection
      :ui="{
        container: 'max-w-5xl'
      }"
    >
      <div class="rounded-2xl border border-default bg-default overflow-hidden">
        <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-px">
          <Motion
            v-for="(stat, index) in stats"
            :key="stat.label"
            v-bind="staggerMotion(index)"
          >
            <div class="p-8 text-center">
              <p v-if="stat.value" :class="['text-3xl sm:text-4xl font-bold tracking-tight leading-none mb-2', stat.accent]">{{ stat.value }}</p>
              <p class="font-mono text-xs uppercase tracking-[0.06em] text-dimmed">{{ stat.label }}</p>
            </div>
          </Motion>
        </div>
      </div>
    </UPageSection>

    <!-- Why us -->
    <UPageSection
      :ui="{
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-primary uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-md mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Warum wir
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          Tools, die einfach funktionieren.
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          Alle unsere Produkte sind auf schnelle Integration und messbaren Mehrwert ausgelegt.
        </Motion>
      </template>

      <div class="grid grid-cols-1 sm:grid-cols-2 gap-6 mt-2">
        <Motion
          v-for="(item, index) in values"
          :key="item.title"
          v-bind="staggerMotion(index)"
        >
          <div class="rounded-2xl border border-default bg-default p-6 h-full hover:border-primary/30 transition-colors duration-300">
            <div class="mb-4 flex size-10 items-center justify-center rounded-lg bg-primary/10">
              <UIcon :name="item.icon" class="size-5 text-primary" />
            </div>
            <h3 class="text-sm font-semibold tracking-tight mb-1.5">{{ item.title }}</h3>
            <p class="text-sm text-dimmed leading-relaxed">{{ item.description }}</p>
          </div>
        </Motion>
      </div>
    </UPageSection>

    <!-- CTA -->
    <UPageCTA
      variant="naked"
      :ui="{
        container: 'max-w-3xl text-center'
      }"
    >
      <template #top>
        <GradientGlow class="bottom-0 w-2/3 h-1/2" />
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block text-4xl lg:text-5xl tracking-tighter">
          Welches Tool passt zu Ihnen?
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block max-w-md mx-auto leading-relaxed text-dimmed">
          Lassen Sie sich individuell beraten – wir finden gemeinsam die richtige Lösung für Ihre digitale Performance.
        </Motion>
      </template>

      <template #links>
        <Motion
          class="flex flex-wrap justify-center gap-4 mt-6"
          v-bind="scrollMotion(0.2)"
        >
          <UButton
            label="PromoHero entdecken"
            class="bg-gradient-to-r from-violet-500 to-fuchsia-500 hover:from-violet-400 hover:to-fuchsia-400 text-white transition-all duration-200 font-semibold"
            size="lg"
            to="/promohero"
          />
          <UButton
            label="TriGuest entdecken"
            class="bg-teal-500 hover:bg-teal-400 text-white transition-all duration-200 font-semibold"
            size="lg"
            to="/triguest"
          />
          <UButton
            label="TopAccess entdecken"
            class="bg-gradient-to-r from-amber-500 to-orange-500 hover:from-amber-400 hover:to-orange-400 text-white transition-all duration-200 font-semibold"
            size="lg"
            to="/topaccess"
          />
        </Motion>
      </template>
    </UPageCTA>
  </div>
</template>
