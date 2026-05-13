<script setup lang="ts">
definePageMeta({
})

useSeoMeta({
  title: 'TopAccess – Barrierefreiheit, die einfach funktioniert',
  ogTitle: 'TopAccess – Barrierefreiheit, die einfach funktioniert',
  description: 'TopAccess erweitert Ihre Website um ein smartes Accessibility Widget und generiert automatisch Alt-Texte für Bilder – unterstützt durch KI.',
  ogDescription: 'TopAccess erweitert Ihre Website um ein smartes Accessibility Widget und generiert automatisch Alt-Texte für Bilder – unterstützt durch KI.'
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
  { icon: 'i-lucide-users', title: 'Größere Zielgruppe', description: 'Bessere Zugänglichkeit bedeutet: mehr Menschen erreichen Ihre Inhalte.' },
  { icon: 'i-lucide-trending-up', title: 'Mehr Conversions', description: 'Ohne zusätzlichen Aufwand – barrierefreie Seiten konvertieren besser.' },
  { icon: 'i-lucide-image', title: 'KI-generierte Alt-Texte', description: 'Automatische Bildbeschreibungen für bessere Auffindbarkeit und Zugänglichkeit.' },
  { icon: 'i-lucide-search', title: 'Positive SEO-Effekte', description: 'Suchmaschinen bevorzugen barrierefreie, gut strukturierte Inhalte.' },
  { icon: 'i-lucide-globe', title: 'Suchmaschinen-Vorteile', description: 'Zugängliche Websites ranken besser – ein direkter Vorteil für Ihre Sichtbarkeit.' },
  { icon: 'i-lucide-heart', title: 'Bessere User Experience', description: 'Für alle Besucher:innen – nicht nur für Menschen mit Einschränkungen.' }
]

const steps = [
  { icon: 'i-lucide-toggle-right', number: '01', title: 'Widget aktivieren', description: 'Eine Zeile Code einbinden – in wenigen Sekunden ist das Accessibility Widget auf Ihrer Website live.' },
  { icon: 'i-lucide-sliders-horizontal', number: '02', title: 'Nutzer:innen passen an', description: 'Besucher:innen stellen Schriftgröße, Kontraste, Animationen und Lesemodi individuell ein – direkt im Frontend.' },
  { icon: 'i-lucide-sparkles', number: '03', title: 'KI optimiert automatisch', description: 'Im Hintergrund generiert die KI Alt-Texte für Bilder, optimiert für Screenreader und Suchmaschinen.' }
]

const widgetFeatures = [
  { icon: 'i-lucide-type', title: 'Schriftgröße anpassen', description: 'Individuelle Textgrößen für optimale Lesbarkeit.' },
  { icon: 'i-lucide-contrast', title: 'Kontraste optimieren', description: 'Hohe Kontraste und Farbmodi für bessere Sichtbarkeit.' },
  { icon: 'i-lucide-pause', title: 'Animationen steuern', description: 'Bewegungen pausieren oder reduzieren – für ein ruhiges Erlebnis.' },
  { icon: 'i-lucide-book-open', title: 'Lesemodus aktivieren', description: 'Fokussiertes Lesen ohne Ablenkung.' },
  { icon: 'i-lucide-settings-2', title: 'Persönliche Einstellungen', description: 'Darstellung an individuelle Bedürfnisse anpassen.' }
]

const aiFeatures = [
  { icon: 'i-lucide-image', title: 'Automatische Bildbeschreibungen', description: 'KI generiert Alt-Texte für alle Bilder – ohne manuellen Aufwand.' },
  { icon: 'i-lucide-headphones', title: 'Screenreader-optimiert', description: 'Beschreibungen speziell für assistive Technologien aufbereitet.' },
  { icon: 'i-lucide-search', title: 'Bessere Auffindbarkeit', description: 'Alt-Texte verbessern die Bild-Suche und SEO-Performance.' },
  { icon: 'i-lucide-refresh-cw', title: 'Kein Pflegeaufwand', description: 'Läuft automatisch im Hintergrund – neue Bilder werden erkannt und beschriftet.' }
]

const besonders = [
  { icon: 'i-lucide-layers', title: 'Sichtbar + unsichtbar', description: 'Widget im Frontend für Nutzer:innen, KI-Optimierung unsichtbar im Hintergrund.' },
  { icon: 'i-lucide-bot', title: 'Automatisiert statt manuell', description: 'Kein Pflegeaufwand – die KI übernimmt die Arbeit.' },
  { icon: 'i-lucide-bar-chart-3', title: 'Performance-Faktor', description: 'Mehr Reichweite und bessere Conversion durch bessere Zugänglichkeit.' }
]

const integration = [
  { icon: 'i-lucide-code', title: 'Eine Zeile Code', description: 'Integration mit nur einem Script-Tag.' },
  { icon: 'i-lucide-globe', title: 'Jedes CMS & Framework', description: 'WordPress, Shopify, React, Vue – überall einsetzbar.' },
  { icon: 'i-lucide-paintbrush', title: 'CI-konform', description: 'Farben und Schriften passend zu Ihrem Branding.' },
  { icon: 'i-lucide-zap', title: 'Sofort einsatzbereit', description: 'Schnell implementiert, sofort aktiv.' }
]

const useCases = [
  { icon: 'i-lucide-building-2', title: 'Unternehmen & Dienstleister', description: 'Mehr Reichweite ohne Mehraufwand – Inhalte für alle zugänglich machen.', color: 'text-amber-400' },
  { icon: 'i-lucide-plane', title: 'Tourismus & Hotellerie', description: 'Inhalte für alle Zielgruppen zugänglich – international und barrierefrei.', color: 'text-orange-400' },
  { icon: 'i-lucide-shopping-cart', title: 'E-Commerce', description: 'Bessere Usability = mehr Abschlüsse. Barrierefreiheit zahlt sich direkt aus.', color: 'text-red-400' }
]

const isYearly = ref(true)

const activeDemo = ref(0)
const demoVideos = [
  { id: 'contrast', label: 'Kontraste', icon: 'i-lucide-contrast', src: '/top_access_contrast.mp4', description: 'Kontraste & Farbmodi anpassen – für bessere Lesbarkeit bei Sehschwäche.' },
  { id: 'text', label: 'Textanpassung', icon: 'i-lucide-type', src: '/top_access_text_manipulation.mp4', description: 'Schriftgröße, Zeilenabstand und Wortabstand individuell einstellen.' },
  { id: 'links', label: 'Titel & Links', icon: 'i-lucide-link', src: '/top_access_title_links.mp4', description: 'Überschriften und Links visuell hervorheben – für schnellere Orientierung.' }
]
</script>

<template>
  <div class="relative">
    <!-- Background dot grid overlay -->
    <div
      class="pointer-events-none fixed inset-0 opacity-[0.03] z-0"
      style="background-image: radial-gradient(rgba(245, 158, 11, 0.8) 1px, transparent 1px); background-size: 32px 32px;"
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
        <Motion v-bind="staggerMotion(0)">

        </Motion>
        <div class="pointer-events-none absolute top-0 left-1/2 -translate-x-1/2 w-2/3 h-1/2" style="background: radial-gradient(ellipse at center, rgba(245, 158, 11, 0.12) 0%, transparent 70%);" />
        <div class="pointer-events-none absolute -top-20 -left-32 w-[400px] h-[400px] rounded-full blur-[100px] bg-amber-500/[0.07]" />
        <div class="pointer-events-none absolute -top-10 -right-40 w-[300px] h-[300px] rounded-full blur-[80px] bg-orange-500/[0.06]" />
      </template>

      <template #headline>
        <Motion v-bind="enterMotion(0.2)">
          <UBadge
            color="neutral"
            variant="soft"
            label="Accessibility Widget + KI Alt-Texte"
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
          Barrierefreiheit für
          <span
            class="animate-shimmer bg-size-[200%_auto] bg-clip-text text-transparent"
            :style="{
              backgroundImage: 'linear-gradient(135deg, #fbbf24, #f59e0b, #f97316, #ef4444, #f97316, #f59e0b, #fbbf24)',
              animationDuration: '10s'
            }"
          >
            alle.
          </span>
        </Motion>
      </template>

      <template #description>
        <Motion
          as="span"
          v-bind="enterMotion(0.5)"
          class="inline-block"
        >
          Barrierefreiheit, die einfach funktioniert. TopAccess erweitert Ihre Website um ein smartes Accessibility Widget und generiert automatisch Alt-Texte für Bilder – unterstützt durch KI. So erreichen Sie mehr Menschen und verbessern die Usability ohne Mehraufwand.
        </Motion>
      </template>

      <template #links>
        <Motion
          class="flex flex-wrap justify-center gap-4"
          v-bind="enterMotion(0.65)"
        >
          <UButton
            label="Jetzt ausprobieren"
            class="bg-gradient-to-r from-amber-500 to-orange-500 hover:from-amber-400 hover:to-orange-400 text-white shadow-[0_0_20px_rgba(245,158,11,0.25)] hover:shadow-[0_0_30px_rgba(245,158,11,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
            size="xl"
            to="#kontakt"
          />
          <UButton
            label="Demo ansehen"
            size="xl"
            color="neutral"
            variant="soft"
            to="#demo"
          />
        </Motion>
      </template>
    </UPageHero>

    <!-- Warum Accessibility -->
    <UPageSection
      :ui="{
        container: 'max-w-3xl text-center'
      }"
    >
      <Motion v-bind="scrollMotion()">
        <p class="text-lg sm:text-xl leading-relaxed text-muted">
          Mit TopAccess öffnen Sie Ihre Website für eine deutlich größere Zielgruppe. Menschen mit unterschiedlichen Bedürfnissen können Ihre Inhalte besser nutzen – und das zahlt sich aus:
          <span class="text-amber-300 font-medium">mehr Reichweite, mehr Interaktion, mehr Abschlüsse.</span>
          Und das Beste: Sie müssen nichts zusätzlich pflegen. Die Optimierung läuft im Hintergrund.
        </p>
      </Motion>
    </UPageSection>

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-48 right-[-5%] w-[600px] h-[600px] rounded-full blur-[100px] bg-amber-500/[0.08]" />
      <div class="absolute -top-20 left-[-10%] w-[350px] h-[350px] rounded-full blur-[80px] bg-orange-400/[0.06]" />
    </div>

    <!-- Vorteile -->
    <UPageSection
      id="vorteile"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-amber-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-md mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Ihre Vorteile
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          Accessibility bringt mehr als nur Barrierefreiheit.
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          Zugängliche Websites performen besser – für alle Besucher:innen.
        </Motion>
      </template>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 mt-2">
        <Motion
          v-for="(item, index) in vorteile"
          :key="item.title"
          v-bind="staggerMotion(index)"
        >
          <div
            class="rounded-2xl border border-amber-500/[0.12] bg-default p-6 h-full hover:border-amber-500/30 hover:shadow-[0_0_30px_rgba(245,158,11,0.1)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(245, 158, 11, 0.1) 0%, rgba(245, 158, 11, 0.02) 50%, transparent 80%)"
          >
            <div class="mb-4 flex size-10 items-center justify-center rounded-lg bg-amber-500/15 ring-1 ring-amber-500/10">
              <UIcon :name="item.icon" class="size-5 text-amber-400" />
            </div>
            <h3 class="text-sm font-semibold tracking-tight mb-1.5">{{ item.title }}</h3>
            <p class="text-sm text-dimmed leading-relaxed">{{ item.description }}</p>
          </div>
        </Motion>
      </div>
    </UPageSection>

    <!-- So funktioniert's -->
    <UPageSection
      id="so-funktionierts"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-amber-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-md mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          So funktioniert's
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          In drei Schritten zur barrierefreien Website.
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          TopAccess integriert sich nahtlos und arbeitet im Hintergrund.
        </Motion>
      </template>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 mt-4">
        <Motion
          v-for="(step, index) in steps"
          :key="step.title"
          v-bind="staggerMotion(index)"
        >
          <div
            class="relative rounded-2xl border border-amber-500/[0.12] bg-default p-8 h-full hover:border-amber-500/25 hover:shadow-[0_0_30px_rgba(245,158,11,0.1)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(245, 158, 11, 0.1) 0%, rgba(245, 158, 11, 0.02) 50%, transparent 80%)"
          >
            <span class="absolute top-6 right-6 font-mono text-4xl font-black text-amber-500/15">{{ step.number }}</span>
            <div class="mb-5 flex size-12 items-center justify-center rounded-xl bg-amber-500/15 ring-1 ring-amber-500/10">
              <UIcon :name="step.icon" class="size-6 text-amber-400" />
            </div>
            <h3 class="text-base font-semibold tracking-tight mb-2">{{ step.title }}</h3>
            <p class="text-sm text-dimmed leading-relaxed">{{ step.description }}</p>
          </div>
        </Motion>
      </div>
    </UPageSection>

    <!-- Demo Videos -->
    <UPageSection
      id="demo"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-amber-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-md mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Demo
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          TopAccess Widget in Aktion.
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          Sehen Sie selbst, wie das Widget Ihre Website barrierefreier macht.
        </Motion>
      </template>

      <Motion v-bind="scrollMotion(0.3)">
        <!-- Tabs -->
        <div class="flex items-center justify-center gap-2 mb-6">
          <button
            v-for="(demo, index) in demoVideos"
            :key="demo.id"
            class="flex items-center gap-2 px-4 py-2.5 rounded-xl text-sm font-medium transition-all duration-300 cursor-pointer"
            :class="activeDemo === index
              ? 'bg-amber-500/15 text-amber-400 ring-1 ring-amber-500/25 shadow-[0_0_20px_rgba(245,158,11,0.1)]'
              : 'text-dimmed hover:text-default hover:bg-amber-500/5'"
            @click="activeDemo = index"
          >
            <UIcon :name="demo.icon" class="size-4" />
            {{ demo.label }}
          </button>
        </div>

        <!-- Browser Chrome -->
        <div
          class="rounded-2xl border border-amber-500/[0.12] bg-white dark:bg-[#1a1710] shadow-2xl shadow-amber-500/10 overflow-hidden"
          style="background-image: linear-gradient(to top, rgba(245, 158, 11, 0.06) 0%, transparent 40%)"
        >
          <!-- Browser Top Bar -->
          <div class="flex items-center gap-2 px-4 py-3 bg-gray-100 dark:bg-[#141210] border-b border-gray-200 dark:border-white/5">
            <!-- Traffic lights -->
            <div class="flex items-center gap-1.5 mr-2">
              <span class="size-3 rounded-full bg-[#ff5f57]" />
              <span class="size-3 rounded-full bg-[#febc2e]" />
              <span class="size-3 rounded-full bg-[#28c840]" />
            </div>
            <!-- Address bar -->
            <div class="flex-1 flex items-center gap-2 bg-white dark:bg-[#0d0c0a] rounded-lg px-3 py-1.5 text-xs text-gray-400 dark:text-white/50 border border-gray-200 dark:border-transparent">
              <UIcon name="i-lucide-lock" class="size-3 text-emerald-400 shrink-0" />
              <span class="text-gray-600 dark:text-white/70">topaccess.at</span>
            </div>
            <!-- Browser actions -->
            <div class="flex items-center gap-1 ml-2">
              <UIcon name="i-lucide-arrow-left" class="size-3.5 text-gray-300 dark:text-white/20" />
              <UIcon name="i-lucide-arrow-right" class="size-3.5 text-gray-300 dark:text-white/20" />
              <UIcon name="i-lucide-rotate-cw" class="size-3.5 text-gray-300 dark:text-white/20" />
            </div>
          </div>

          <!-- Video area with transition -->
          <div class="relative bg-black">
            <video
              v-for="(demo, index) in demoVideos"
              :key="demo.id"
              class="w-full block object-cover transition-opacity duration-500"
              :class="activeDemo === index ? 'relative opacity-100' : 'absolute inset-0 opacity-0 pointer-events-none'"
              autoplay
              loop
              muted
              playsinline
            >
              <source :src="demo.src" type="video/mp4">
            </video>
          </div>
        </div>

        <!-- Caption -->
        <p class="text-center text-xs text-dimmed mt-4 transition-all duration-300">
          {{ demoVideos[activeDemo]?.description }}
        </p>
      </Motion>
    </UPageSection>

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-48 left-[-8%] w-[700px] h-[500px] rounded-full blur-[120px] bg-orange-500/[0.07]" />
      <div class="absolute -top-20 right-[5%] w-[300px] h-[300px] rounded-full blur-[80px] bg-amber-400/[0.05]" />
    </div>

    <!-- Funktionen im Detail -->
    <UPageSection
      id="features"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-amber-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-md mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Features
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          Die Funktionen im Detail.
        </Motion>
      </template>

      <!-- Widget Features -->
      <div class="mt-8 mb-16">
        <Motion v-bind="scrollMotion()">
          <h3 class="text-center text-lg font-semibold mb-2">Accessibility Widget</h3>
          <p class="text-center text-sm text-dimmed mb-2 max-w-md mx-auto">Ihre Nutzer:innen entscheiden selbst, wie sie Ihre Website erleben möchten.</p>
          <div class="mx-auto w-16 h-0.5 rounded-full bg-gradient-to-r from-amber-500/60 to-orange-500/60 mb-8" />
        </Motion>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
          <Motion
            v-for="(feature, index) in widgetFeatures"
            :key="feature.title"
            v-bind="staggerMotion(index)"
          >
            <div
              class="rounded-2xl border border-amber-500/[0.12] bg-default p-6 h-full hover:border-amber-500/30 hover:shadow-[0_0_30px_rgba(245,158,11,0.1)] transition-all duration-300"
              style="background-image: linear-gradient(to top, rgba(245, 158, 11, 0.1) 0%, rgba(245, 158, 11, 0.02) 50%, transparent 80%)"
            >
              <div class="mb-4 flex size-9 items-center justify-center rounded-lg bg-amber-500/15 ring-1 ring-amber-500/10">
                <UIcon :name="feature.icon" class="size-4.5 text-amber-400" />
              </div>
              <h4 class="text-sm font-semibold tracking-tight mb-1">{{ feature.title }}</h4>
              <p class="text-sm text-dimmed leading-relaxed">{{ feature.description }}</p>
            </div>
          </Motion>
        </div>
      </div>

      <!-- AI Features -->
      <div>
        <Motion v-bind="scrollMotion()">
          <h3 class="text-center text-lg font-semibold mb-2">KI-gestützte Alt-Texte</h3>
          <p class="text-center text-sm text-dimmed mb-2 max-w-md mx-auto">Während das Widget im Frontend sichtbar ist, arbeitet die KI unsichtbar im Hintergrund.</p>
          <div class="mx-auto w-16 h-0.5 rounded-full bg-gradient-to-r from-orange-500/60 to-red-500/60 mb-8" />
        </Motion>

        <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
          <Motion
            v-for="(feature, index) in aiFeatures"
            :key="feature.title"
            v-bind="staggerMotion(index)"
          >
            <div
            class="rounded-2xl border border-orange-500/[0.12] bg-default p-6 h-full hover:border-orange-500/30 hover:shadow-[0_0_30px_rgba(249,115,22,0.1)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(249, 115, 22, 0.1) 0%, rgba(249, 115, 22, 0.02) 50%, transparent 80%)"
            >
              <div class="mb-4 flex size-10 items-center justify-center rounded-lg bg-orange-500/15 ring-1 ring-orange-500/10">
                <UIcon :name="feature.icon" class="size-5 text-orange-400" />
              </div>
              <h4 class="text-sm font-semibold tracking-tight mb-1.5">{{ feature.title }}</h4>
              <p class="text-sm text-dimmed leading-relaxed">{{ feature.description }}</p>
            </div>
          </Motion>
        </div>
      </div>
    </UPageSection>

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-40 right-[5%] w-[500px] h-[400px] rounded-full blur-[100px] bg-orange-400/[0.06]" />
    </div>

    <!-- Was macht TopAccess besonders -->
    <UPageSection
      :ui="{
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-amber-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-md mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Besonders
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          Barrierefreiheit als Performance-Faktor.
        </Motion>
      </template>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 mt-4">
        <Motion
          v-for="(item, index) in besonders"
          :key="item.title"
          v-bind="staggerMotion(index)"
        >
          <div
            class="rounded-2xl border border-amber-500/[0.12] bg-default p-8 h-full text-center hover:border-amber-500/25 hover:shadow-[0_0_30px_rgba(245,158,11,0.1)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(245, 158, 11, 0.1) 0%, rgba(245, 158, 11, 0.02) 50%, transparent 80%)"
          >
            <div class="mb-5 mx-auto flex size-14 items-center justify-center rounded-2xl bg-gradient-to-br from-amber-500/15 to-orange-500/15 ring-1 ring-amber-500/10">
              <UIcon :name="item.icon" class="size-7 text-amber-400" />
            </div>
            <h3 class="text-base font-semibold tracking-tight mb-2">{{ item.title }}</h3>
            <p class="text-sm text-dimmed leading-relaxed">{{ item.description }}</p>
          </div>
        </Motion>
      </div>
    </UPageSection>

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-24 left-[20%] w-[350px] h-[350px] rounded-full blur-[80px] bg-amber-400/[0.05]" />
    </div>

    <!-- Maximale Flexibilität -->
    <UPageSection
      :ui="{
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-amber-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-md mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Integration
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          Maximale Flexibilität. Minimale Hürde.
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          TopAccess passt sich Ihrer Website an – nicht umgekehrt.
        </Motion>
      </template>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 mt-2">
        <Motion
          v-for="(item, index) in integration"
          :key="item.title"
          v-bind="staggerMotion(index)"
        >
          <div class="text-center p-6">
            <div class="mb-4 mx-auto flex size-12 items-center justify-center rounded-xl bg-amber-500/15 ring-1 ring-amber-500/15">
              <UIcon :name="item.icon" class="size-6 text-amber-400" />
            </div>
            <h3 class="text-sm font-semibold tracking-tight mb-1.5">{{ item.title }}</h3>
            <p class="text-xs text-dimmed leading-relaxed">{{ item.description }}</p>
          </div>
        </Motion>
      </div>
    </UPageSection>

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-48 right-[-3%] w-[600px] h-[500px] rounded-full blur-[100px] bg-amber-500/[0.08]" />
      <div class="absolute -top-32 left-[10%] w-[250px] h-[250px] rounded-full blur-[60px] bg-orange-400/[0.06]" />
    </div>

    <!-- Einsatzbereiche -->
    <UPageSection
      id="einsatzbereiche"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-amber-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-md mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Einsatzbereiche
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          Für alle Branchen geeignet.
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          TopAccess eignet sich überall dort, wo Websites für Menschen gemacht sind.
        </Motion>
      </template>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 mt-4">
        <Motion
          v-for="(useCase, index) in useCases"
          :key="useCase.title"
          v-bind="staggerMotion(index)"
        >
          <div
            class="rounded-2xl border border-amber-500/[0.12] bg-default p-8 h-full hover:border-amber-500/30 hover:shadow-[0_0_30px_rgba(245,158,11,0.1)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(245, 158, 11, 0.1) 0%, rgba(245, 158, 11, 0.02) 50%, transparent 80%)"
          >
            <div class="mb-5 flex size-12 items-center justify-center rounded-xl bg-amber-500/[0.08] ring-1 ring-amber-500/10">
              <UIcon :name="useCase.icon" :class="['size-7', useCase.color]" />
            </div>
            <h3 class="text-base font-semibold tracking-tight mb-2">{{ useCase.title }}</h3>
            <p class="text-sm text-dimmed leading-relaxed">{{ useCase.description }}</p>
          </div>
        </Motion>
      </div>
    </UPageSection>

    <!-- Ambient glow -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-32 left-[15%] w-[400px] h-[400px] rounded-full blur-[100px] bg-amber-500/[0.06]" />
    </div>

    <!-- Pricing -->
    <UPageSection
      id="preise"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-7xl',
        headline: 'font-mono font-medium text-xs text-amber-400 uppercase tracking-[0.12em] text-center',
        title: 'max-w-lg mx-auto',
        description: 'max-w-md mx-auto text-dimmed'
      }"
    >
      <template #headline>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block">
          Preise
        </Motion>
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block">
          Transparent und fair.
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          Wählen Sie das Paket, das zu Ihnen passt. Mindestlaufzeit 12 Monate.
        </Motion>
      </template>

      <!-- Billing Toggle -->
      <Motion v-bind="scrollMotion(0.25)" class="flex justify-center mt-6 mb-10">
        <div class="inline-flex items-center gap-3 rounded-full border border-default bg-default px-4 py-2">
          <span :class="['text-sm transition-colors', !isYearly ? 'text-default font-medium' : 'text-dimmed']">Monatlich</span>
          <USwitch v-model="isYearly" size="xl" :ui="{base:  'data-[state=checked]:bg-amber-400'}" />
          <span :class="['text-sm transition-colors', isYearly ? 'text-default font-medium' : 'text-dimmed']">
            Jährlich
            <span class="text-amber-400 text-xs ml-1">2 Monate gratis</span>
          </span>
        </div>
      </Motion>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
        <!-- Widget Plan -->
        <Motion v-bind="staggerMotion(0)">
          <div
            class="rounded-2xl border border-amber-500/[0.12] bg-default p-8 h-full hover:border-amber-500/25 hover:shadow-[0_0_30px_rgba(245,158,11,0.08)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(245, 158, 11, 0.1) 0%, rgba(245, 158, 11, 0.02) 50%, transparent 80%)"
          >
            <div class="mb-6">
              <span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-medium bg-amber-500/15 text-amber-400 mb-4">
                Widget
              </span>
              <h3 class="text-xl font-bold tracking-tight mb-1">Accessibility Widget</h3>
              <p class="text-sm text-dimmed">Barrierefreiheit zum Anfassen – direkt im Frontend.</p>
            </div>

            <div class="mb-6">
              <div class="flex items-baseline gap-1">
                <span class="text-4xl font-bold tracking-tight">
                  {{ isYearly ? '41,58' : '49,90' }}
                </span>
                <span class="text-dimmed text-sm">€ / Monat</span>
              </div>
              <p v-if="isYearly" class="text-xs text-amber-400 mt-1">
                499,00 € / Jahr (statt 598,80 €)
              </p>
              <p v-else class="text-xs text-dimmed mt-1">
                oder 499,00 € / Jahr (2 Monate gratis)
              </p>
            </div>

            <ul class="space-y-3 mb-8">
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-amber-400 shrink-0 mt-0.5" />
                <span>Schriftgröße, Kontrast, Animationen anpassen</span>
              </li>
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-amber-400 shrink-0 mt-0.5" />
                <span>Lesemodi und persönliche Einstellungen</span>
              </li>
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-amber-400 shrink-0 mt-0.5" />
                <span>Design an Ihre CI anpassbar</span>
              </li>
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-amber-400 shrink-0 mt-0.5" />
                <span>Integration mit einer Zeile Code</span>
              </li>
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-amber-400 shrink-0 mt-0.5" />
                <span>Funktioniert mit jedem CMS</span>
              </li>
            </ul>

            <UButton
              label="Widget buchen"
              class="bg-gradient-to-r from-amber-500 to-orange-500 hover:from-amber-400 hover:to-orange-400 text-white shadow-[0_0_20px_rgba(245,158,11,0.2)] hover:shadow-[0_0_30px_rgba(245,158,11,0.3)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
              size="lg"
              block
              to="#kontakt"
            />
          </div>
        </Motion>

        <!-- AI Plan -->
        <Motion v-bind="staggerMotion(0)">
          <div
            class="rounded-2xl border border-amber-500/[0.12] bg-default p-8 h-full hover:border-amber-500/25 hover:shadow-[0_0_30px_rgba(245,158,11,0.08)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(245, 158, 11, 0.1) 0%, rgba(245, 158, 11, 0.02) 50%, transparent 80%)"
          >
            <div class="mb-6">
              <span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-medium bg-amber-500/15 text-amber-400 mb-4">
                KI
              </span>
              <h3 class="text-xl font-bold tracking-tight mb-1">KI Alt-Texte</h3>
              <p class="text-sm text-dimmed">Alt-Texte automatisch im Hintergrund generieren lassen</p>
            </div>

            <div class="mb-6">
              <div class="flex items-baseline gap-1">
                <span class="text-4xl font-bold tracking-tight">
                  {{ isYearly ? '39,90' : '39,90' }}
                </span>
                <span class="text-dimmed text-sm">€ / Monat</span>
              </div>
              <p v-if="isYearly" class="text-xs text-amber-400 mt-1">
                Einrichtung inklusive
              </p>
              <p v-else class="text-xs text-dimmed mt-1">
                zzgl. 499 € Einrichtung · Bei Jahreszahlung: Einrichtung kostenlos
              </p>
            </div>

            <ul class="space-y-3 mb-8">
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-orange-400 shrink-0 mt-0.5" />
                <span>KI-generierte Alt-Texte für alle Bilder</span>
              </li>
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-orange-400 shrink-0 mt-0.5" />
                <span>Screenreader-Optimierung</span>
              </li>
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-orange-400 shrink-0 mt-0.5" />
                <span>Automatische Erkennung neuer Bilder</span>
              </li>
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-orange-400 shrink-0 mt-0.5" />
                <span>SEO-Boost durch beschriftete Bilder</span>
              </li>
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-orange-400 shrink-0 mt-0.5" />
                <span>Kein manueller Pflegeaufwand</span>
              </li>
            </ul>

            <UButton
              label="KI Alt-Texte buchen"
              class="bg-gradient-to-r from-amber-500 to-orange-500 hover:from-amber-400 hover:to-orange-400 text-white shadow-[0_0_20px_rgba(245,158,11,0.2)] hover:shadow-[0_0_30px_rgba(245,158,11,0.3)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
              size="lg"
              block
              to="#kontakt"
            />
          </div>
        </Motion>

        <!-- Widget + AI Plan -->
        <Motion v-bind="staggerMotion(1)">
          <div
            class="rounded-2xl border-2 border-amber-500/40 bg-default p-8 h-full relative hover:shadow-[0_0_40px_rgba(245,158,11,0.12)] transition-all duration-300"
            style="background-image: linear-gradient(to top, rgba(245, 158, 11, 0.12) 0%, rgba(245, 158, 11, 0.03) 50%, transparent 80%)"
          >
            <span class="absolute -top-3 left-1/2 -translate-x-1/2 inline-flex items-center gap-1 px-3 py-1 rounded-full text-xs font-semibold bg-gradient-to-r from-amber-500 to-orange-500 text-white">
              Empfohlen
            </span>

            <div class="mb-6">
              <span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-medium bg-orange-500/10 text-orange-400 mb-4">
                Widget + KI
              </span>
              <h3 class="text-xl font-bold tracking-tight mb-1">Widget + KI Alt-Texte</h3>
              <p class="text-sm text-dimmed">Das Komplettpaket: Widget im Frontend, KI im Hintergrund.</p>
            </div>

            <div class="mb-6">
              <div class="flex items-baseline gap-1">
                <span class="text-4xl font-bold tracking-tight">
                  {{ isYearly ? '81,48' : '89,80' }}
                </span>
                <span class="text-dimmed text-sm">€ / Monat</span>
              </div>
              <p v-if="isYearly" class="text-xs text-amber-400 mt-1">
                977,80 € / Jahr (statt 1.077,60 €) · Einrichtung inklusive
              </p>
              <p v-else class="text-xs text-dimmed mt-1">
                zzgl. 499 € Einrichtung · Bei Jahreszahlung: Einrichtung kostenlos
              </p>
            </div>

            <ul class="space-y-3 mb-8">
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-amber-400 shrink-0 mt-0.5" />
                <span>Alles aus dem Widget-Paket</span>
              </li>
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-orange-400 shrink-0 mt-0.5" />
                <span>KI-generierte Alt-Texte für alle Bilder</span>
              </li>
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-orange-400 shrink-0 mt-0.5" />
                <span>Screenreader-Optimierung</span>
              </li>
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-orange-400 shrink-0 mt-0.5" />
                <span>Automatische Erkennung neuer Bilder</span>
              </li>
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-orange-400 shrink-0 mt-0.5" />
                <span>SEO-Boost durch beschriftete Bilder</span>
              </li>
              <li class="flex items-start gap-2.5 text-sm">
                <UIcon name="i-lucide-check" class="size-4 text-orange-400 shrink-0 mt-0.5" />
                <span>Kein manueller Pflegeaufwand</span>
              </li>
            </ul>

            <UButton
              label="Komplettpaket buchen"
              class="bg-gradient-to-r from-amber-500 to-orange-500 hover:from-amber-400 hover:to-orange-400 text-white shadow-[0_0_20px_rgba(245,158,11,0.25)] hover:shadow-[0_0_30px_rgba(245,158,11,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
              size="lg"
              block
              to="#kontakt"
            />
          </div>
        </Motion>
      </div>

      <Motion v-bind="scrollMotion(0.3)">
        <p class="text-center text-xs text-dimmed">
          Alle Preise zzgl. MwSt. · Mindestlaufzeit 12 Monate · Bei jährlicher Zahlung: 2 Monate gratis + kostenlose KI-Einrichtung.
        </p>
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
        <div class="pointer-events-none absolute bottom-0 left-1/2 -translate-x-1/2 w-2/3 h-1/2" style="background: radial-gradient(ellipse at center, rgba(245, 158, 11, 0.12) 0%, transparent 70%);" />
        <div class="pointer-events-none absolute -bottom-20 -left-20 w-[350px] h-[350px] rounded-full blur-[80px] bg-amber-500/[0.06]" />
        <div class="pointer-events-none absolute -bottom-10 -right-32 w-[300px] h-[300px] rounded-full blur-[80px] bg-orange-500/[0.05]" />
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block text-4xl lg:text-5xl tracking-tighter">
          Bereit für mehr Reichweite?
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block max-w-md mx-auto leading-relaxed text-dimmed">
          Machen Sie Ihre Website zugänglicher – und profitieren Sie direkt davon. Mehr Besucher:innen, bessere Conversions, stärkere SEO.
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
              placeholder="Website-URL"
              size="xl"
              :ui="{ base: 'bg-elevated' }"
            />
            <USelect
              placeholder="Gewünschtes Paket"
              size="xl"
              :items="['Widget (49,90 €/Monat)', 'Widget + KI Alt-Texte (89,80 €/Monat)', 'Noch unsicher – bitte beraten']"
              :ui="{ base: 'bg-elevated' }"
            />
            <UTextarea
              placeholder="Ihre Nachricht (optional)"
              :rows="3"
              :ui="{ base: 'bg-elevated' }"
            />
            <UButton
              label="Jetzt mit TopAccess durchstarten"
              class="bg-gradient-to-r from-amber-500 to-orange-500 hover:from-amber-400 hover:to-orange-400 text-white shadow-[0_0_20px_rgba(245,158,11,0.25)] hover:shadow-[0_0_30px_rgba(245,158,11,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
              size="xl"
              block
              type="submit"
            />
            <p class="text-xs text-dimmed text-center">
              Wir melden uns innerhalb von 24h mit einem individuellen Angebot.
            </p>
          </form>
        </Motion>
      </template>
    </UPageCTA>
  </div>
</template>
