<script setup lang="ts">
definePageMeta({
})

useSeoMeta({
  title: 'PromoHero – Aus Absprüngen Abschlüsse machen',
  ogTitle: 'PromoHero – Aus Absprüngen Abschlüsse machen',
  description: 'PromoHero erkennt, wenn Besucher:innen gehen wollen und spielt im perfekten Moment ein starkes Angebot aus. Exit-Intent Overlays für mehr Conversions.',
  ogDescription: 'PromoHero erkennt, wenn Besucher:innen gehen wollen und spielt im perfekten Moment ein starkes Angebot aus. Exit-Intent Overlays für mehr Conversions.'
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
  { icon: 'i-lucide-repeat', title: 'Absprünge in Abschlüsse verwandeln', description: 'Automatisch und in Echtzeit – ohne manuellen Aufwand.' },
  { icon: 'i-lucide-trending-up', title: 'Conversion Boost', description: 'Mehr Umsatz ohne zusätzliche Werbekosten.' },
  { icon: 'i-lucide-timer', title: 'Perfektes Timing', description: 'Exit-Intent-Technologie erkennt den richtigen Moment.' },
  { icon: 'i-lucide-users', title: 'Mehr Leads & Buchungen', description: 'Steigern Sie Anfragen, Buchungen und Umsatz messbar.' },
  { icon: 'i-lucide-zap', title: 'Sofort einsatzbereit', description: 'Schnell integriert – in wenigen Minuten live.' }
]

const steps = [
  { icon: 'i-lucide-pencil-ruler', number: '01', title: 'Popup erstellen', description: 'Definieren Sie Ihr Angebot – ob Rabattcode, Gutschein oder Lead-Magnet. Das Design passen Sie per Drag & Drop an Ihre CI an.' },
  { icon: 'i-lucide-mouse-pointer-click', number: '02', title: 'Trigger festlegen', description: 'Wählen Sie den perfekten Auslöser: Exit Intent, Scroll-Tiefe, Inaktivität oder zeitbasiert. Sie entscheiden, wann das Overlay erscheint.' },
  { icon: 'i-lucide-rocket', number: '03', title: 'Conversions steigern', description: 'Das Overlay erscheint im richtigen Moment mit einer attraktiven CTA – und holt User zurück, die eigentlich schon weg waren.' }
]

const features = [
  { icon: 'i-lucide-sparkles', title: 'Smarte Overlays', description: 'Keine nervigen Pop-ups, sondern intelligente Ausspielung im richtigen Moment.' },
  { icon: 'i-lucide-palette', title: 'Individuelles Design', description: 'Farben, Schriften und Layout perfekt auf Ihre Marke abgestimmt.' },
  { icon: 'i-lucide-user-check', title: 'Personalisierte Inhalte', description: 'Unterschiedliche Angebote je nach Nutzerverhalten und Seitenkontext.' },
  { icon: 'i-lucide-bar-chart-3', title: 'Echtzeit-Tracking', description: 'Volle Transparenz über Performance, Klicks und Conversion-Raten.' }
]

const integration = [
  { icon: 'i-lucide-code', title: 'Eine Zeile Code', description: 'Integration mit nur einem Script-Tag – fertig.' },
  { icon: 'i-lucide-globe', title: 'CMS-unabhängig', description: 'WordPress, Shopify, Custom – funktioniert überall.' },
  { icon: 'i-lucide-paintbrush', title: 'CI-konform', description: 'Farben, Schriften und Design passend zu Ihrem Branding.' },
  { icon: 'i-lucide-clock', title: 'Schnell live', description: 'Ohne aufwendige Entwicklung in Minuten eingebunden.' }
]

const useCases = [
  { icon: 'i-lucide-shopping-cart', title: 'E-Commerce', description: 'Warenkorbabbrüche reduzieren und Kaufabschlüsse steigern.', color: 'text-violet-400' },
  { icon: 'i-lucide-plane', title: 'Hotels & Tourismus', description: 'From Looking to Booking – Direktbuchungen maximieren.', color: 'text-sky-400' },
  { icon: 'i-lucide-headset', title: 'Dienstleistungen', description: 'Mehr Anfragen, mehr Kontakte, mehr Kunden generieren.', color: 'text-emerald-400' }
]
</script>

<template>
  <div>
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
        <GradientGlow class="top-0 w-2/3 h-1/2" />
      </template>

      <template #headline>
        <Motion v-bind="enterMotion(0.2)">
          <UBadge
            color="neutral"
            variant="soft"
            label="Exit-Intent Overlay Tool"
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
          From Zero to Hero.
          <br>
          <span
            class="animate-shimmer bg-size-[200%_auto] bg-clip-text text-transparent"
            :style="{
              backgroundImage: 'linear-gradient(135deg, #a78bfa, #e879f9, #f0abfc, #c084fc, #a78bfa, #d946ef, #a78bfa)',
              animationDuration: '10s'
            }"
          >
            Absprünge werden Abschlüsse.
          </span>
        </Motion>
      </template>

      <template #description>
        <Motion
          as="span"
          v-bind="enterMotion(0.5)"
          class="inline-block"
        >
          PromoHero erkennt, wenn Besucher:innen gehen wollen – und spielt im perfekten Moment ein starkes Angebot aus. Ein smartes Overlay, ein guter Deal, und aus „Ich bin dann mal weg" wird ein Abschluss.
        </Motion>
      </template>

      <template #links>
        <Motion
          class="flex flex-wrap justify-center gap-4"
          v-bind="enterMotion(0.65)"
        >
          <UButton
            label="Jetzt ausprobieren"
            class="bg-gradient-to-r from-violet-500 to-fuchsia-500 hover:from-violet-400 hover:to-fuchsia-400 text-white shadow-[0_0_20px_rgba(139,92,246,0.25)] hover:shadow-[0_0_30px_rgba(139,92,246,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
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

    <!-- Demo Video -->
    <UPageSection
      id="demo"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-6xl'
      }"
    >
      <Motion v-bind="scrollMotion(0.1)">
        <div class="rounded-2xl border border-default bg-white dark:bg-[#1a1a2e] shadow-2xl shadow-fuchsia-500/10 overflow-hidden">
          <!-- Browser Top Bar -->
          <div class="flex items-center gap-2 px-4 py-3 bg-gray-100 dark:bg-[#12121f] border-b border-gray-200 dark:border-white/5">
            <!-- Traffic lights -->
            <div class="flex items-center gap-1.5 mr-2">
              <span class="size-3 rounded-full bg-[#ff5f57]" />
              <span class="size-3 rounded-full bg-[#febc2e]" />
              <span class="size-3 rounded-full bg-[#28c840]" />
            </div>
            <!-- Address bar -->
            <div class="flex-1 flex items-center gap-2 bg-white dark:bg-[#0d0d1a] rounded-lg px-3 py-1.5 text-xs text-gray-400 dark:text-white/50 border border-gray-200 dark:border-transparent">
              <UIcon name="i-lucide-lock" class="size-3 text-emerald-400 shrink-0" />
              <span class="text-gray-600 dark:text-white/70">promohero.at</span>
            </div>
            <!-- Browser actions -->
            <div class="flex items-center gap-1 ml-2">
              <UIcon name="i-lucide-arrow-left" class="size-3.5 text-gray-300 dark:text-white/20" />
              <UIcon name="i-lucide-arrow-right" class="size-3.5 text-gray-300 dark:text-white/20" />
              <UIcon name="i-lucide-rotate-cw" class="size-3.5 text-gray-300 dark:text-white/20" />
            </div>
          </div>
          <!-- Video -->
          <div class="relative">
            <video
              class="w-full block object-cover"
              autoplay
              loop
              muted
              playsinline
            >
              <source src="/demo_exit_intent.mp4" type="video/mp4">
            </video>
          </div>
        </div>
        <p class="text-center text-xs text-dimmed mt-4">
          Exit-Intent Overlay in Aktion – das Overlay erscheint, sobald der Cursor das Browserfenster verlässt.
        </p>
      </Motion>
    </UPageSection>

    <!-- Warum PromoHero -->
    <UPageSection
      :ui="{
        container: 'max-w-3xl text-center'
      }"
    >
      <Motion v-bind="scrollMotion()">
        <p class="text-lg sm:text-xl leading-relaxed text-muted">
          Jede Website hat sie: Besucher:innen, die klicken, scrollen – und dann einfach verschwinden.
          <span class="text-default font-medium">Genau hier setzt PromoHero an.</span>
          Statt diese Chancen zu verlieren, holen Sie Nutzer:innen im entscheidenden Moment zurück – mit einem letzten, überzeugenden Impuls.
        </p>
      </Motion>
    </UPageSection>

    <!-- Vorteile -->
    <UPageSection
      id="vorteile"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-fuchsia-400 uppercase tracking-[0.12em] text-center',
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
          Alles, was Sie für mehr Conversions brauchen.
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          PromoHero verwandelt verlorene Besucher in zahlende Kunden – automatisch und messbar.
        </Motion>
      </template>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 mt-2">
        <Motion
          v-for="(item, index) in vorteile"
          :key="item.title"
          v-bind="staggerMotion(index)"
        >
          <div
            class="rounded-2xl border border-default bg-default p-6 h-full hover:border-fuchsia-500/30 transition-colors duration-300"
            style="background-image: linear-gradient(to top, rgba(192, 38, 211, 0.07) 0%, transparent 60%)"
          >
            <div class="mb-4 flex size-10 items-center justify-center rounded-lg bg-violet-500/10">
              <UIcon :name="item.icon" class="size-5 text-violet-400" />
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
        headline: 'font-mono font-medium text-xs text-fuchsia-400 uppercase tracking-[0.12em] text-center',
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
          In drei Schritten zu mehr Conversions.
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          PromoHero arbeitet im Hintergrund und reagiert genau dann, wenn es zählt.
        </Motion>
      </template>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 mt-4">
        <Motion
          v-for="(step, index) in steps"
          :key="step.title"
          v-bind="staggerMotion(index)"
        >
          <div
            class="relative rounded-2xl border border-default bg-default p-8 h-full"
            style="background-image: linear-gradient(to top, rgba(192, 38, 211, 0.07) 0%, transparent 60%)"
          >
            <span class="absolute top-6 right-6 font-mono text-4xl font-black text-white/5">{{ step.number }}</span>
            <div class="mb-5 flex size-12 items-center justify-center rounded-xl bg-violet-500/10">
              <UIcon :name="step.icon" class="size-6 text-violet-400" />
            </div>
            <h3 class="text-base font-semibold tracking-tight mb-2">{{ step.title }}</h3>
            <p class="text-sm text-dimmed leading-relaxed">{{ step.description }}</p>
          </div>
        </Motion>
      </div>
    </UPageSection>

    <!-- Was macht PromoHero besonders? -->
    <UPageSection
      id="features"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-fuchsia-400 uppercase tracking-[0.12em] text-center',
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
          Was PromoHero besonders macht.
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          Nicht jedes Pop-up funktioniert. PromoHero setzt auf intelligente Ausspielung statt störender Unterbrechung.
        </Motion>
      </template>

      <div
        class="rounded-2xl border border-default bg-default overflow-hidden"
        style="background-image: linear-gradient(to top, rgba(192, 38, 211, 0.07) 0%, transparent 60%)"
      >
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-px">
          <Motion
            v-for="(feature, index) in features"
            :key="feature.title"
            v-bind="staggerMotion(index)"
          >
            <div class="p-8 h-full hover:bg-elevated/50 transition-colors duration-300">
              <div class="mb-5 flex size-10 items-center justify-center rounded-lg bg-violet-500/10">
                <UIcon :name="feature.icon" class="size-5 text-violet-400" />
              </div>
              <h3 class="text-sm font-semibold tracking-tight mb-1.5">{{ feature.title }}</h3>
              <p class="text-sm text-dimmed leading-relaxed">{{ feature.description }}</p>
            </div>
          </Motion>
        </div>
      </div>
    </UPageSection>

    <!-- Maximale Flexibilität -->
    <UPageSection
      :ui="{
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-fuchsia-400 uppercase tracking-[0.12em] text-center',
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
          PromoHero passt sich Ihrer Website an – nicht umgekehrt.
        </Motion>
      </template>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 mt-2">
        <Motion
          v-for="(item, index) in integration"
          :key="item.title"
          v-bind="staggerMotion(index)"
        >
          <div class="text-center p-6">
            <div class="mb-4 mx-auto flex size-12 items-center justify-center rounded-xl bg-violet-500/10">
              <UIcon :name="item.icon" class="size-6 text-violet-400" />
            </div>
            <h3 class="text-sm font-semibold tracking-tight mb-1.5">{{ item.title }}</h3>
            <p class="text-xs text-dimmed leading-relaxed">{{ item.description }}</p>
          </div>
        </Motion>
      </div>
    </UPageSection>

    <!-- Einsatzbereiche -->
    <UPageSection
      id="einsatzbereiche"
      :ui="{
        root: 'scroll-mt-(--ui-header-height)',
        container: 'max-w-5xl',
        headline: 'font-mono font-medium text-xs text-fuchsia-400 uppercase tracking-[0.12em] text-center',
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
          Passt sich Ihrem Business an.
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.2)" class="inline-block">
          Egal ob E-Commerce, Tourismus oder Leadgenerierung – PromoHero liefert Ergebnisse.
        </Motion>
      </template>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 mt-4">
        <Motion
          v-for="(useCase, index) in useCases"
          :key="useCase.title"
          v-bind="staggerMotion(index)"
        >
          <div
            class="rounded-2xl border border-default bg-default p-8 h-full hover:border-fuchsia-500/30 transition-colors duration-300"
            style="background-image: linear-gradient(to top, rgba(192, 38, 211, 0.07) 0%, transparent 60%)"
          >
            <div class="mb-5 flex size-12 items-center justify-center rounded-xl bg-default">
              <UIcon :name="useCase.icon" :class="['size-7', useCase.color]" />
            </div>
            <h3 class="text-base font-semibold tracking-tight mb-2">{{ useCase.title }}</h3>
            <p class="text-sm text-dimmed leading-relaxed">{{ useCase.description }}</p>
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
        <GradientGlow class="bottom-0 w-2/3 h-1/2" />
      </template>

      <template #title>
        <Motion as="span" v-bind="scrollMotion()" class="inline-block text-4xl lg:text-5xl tracking-tighter">
          Bereit für mehr Conversions?
        </Motion>
      </template>

      <template #description>
        <Motion as="span" v-bind="scrollMotion(0.1)" class="inline-block max-w-md mx-auto leading-relaxed text-dimmed">
          Warten Sie nicht, bis Ihre Besucher:innen weg sind. Nutzen Sie den Moment – und machen Sie mehr aus jedem Klick.
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
            <UTextarea
              placeholder="Ihre Nachricht (optional)"
              :rows="3"
              :ui="{ base: 'bg-elevated' }"
            />
            <UButton
              label="Jetzt mit PromoHero durchstarten"
              class="bg-gradient-to-r from-violet-500 to-fuchsia-500 hover:from-violet-400 hover:to-fuchsia-400 text-white shadow-[0_0_20px_rgba(139,92,246,0.25)] hover:shadow-[0_0_30px_rgba(139,92,246,0.35)] hover:-translate-y-px active:translate-y-0 transition-all duration-200 font-semibold"
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
