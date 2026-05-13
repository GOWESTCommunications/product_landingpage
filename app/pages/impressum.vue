<script setup lang="ts">
definePageMeta({
})

useSeoMeta({
  title: 'Impressum – GO.WEST Communications GmbH',
  ogTitle: 'Impressum – GO.WEST Communications GmbH',
  description: 'Allgemeine Informationen nach § 5 ECG – GO.WEST Communications GmbH, Salzburg.',
  ogDescription: 'Allgemeine Informationen nach § 5 ECG – GO.WEST Communications GmbH, Salzburg.'
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
</script>

<template>
  <div class="relative">
    <!-- Background dot grid overlay -->
    <div
      class="pointer-events-none fixed inset-0 opacity-[0.03] z-0"
      style="background-image: radial-gradient(rgba(139, 92, 246, 0.8) 1px, transparent 1px); background-size: 32px 32px;"
    />

    <!-- Hero -->
    <UPageHero
      :ui="{
        container: 'relative z-10 lg:py-20',
        wrapper: 'flex flex-col items-center',
        title: 'sm:text-5xl lg:text-6xl tracking-tighter leading-[1.1]',
        description: 'mt-3 max-w-xl mx-auto text-base leading-relaxed text-dimmed'
      }"
    >
      <template #top>
        <GradientGlow class="top-0 w-2/3 h-1/2" />
        <div class="pointer-events-none absolute -top-20 -left-32 w-[400px] h-[400px] rounded-full blur-[100px] bg-violet-500/[0.07]" />
        <div class="pointer-events-none absolute -top-10 -right-40 w-[300px] h-[300px] rounded-full blur-[80px] bg-fuchsia-500/[0.06]" />
      </template>

      <template #title>
        <Motion
          as="span"
          v-bind="enterMotion(0.35)"
          class="inline-block"
        >
          Impressum
        </Motion>
      </template>

      <template #description>
        <Motion
          as="span"
          v-bind="enterMotion(0.5)"
          class="inline-block"
        >
          Allgemeine Informationen nach § 5 E-Commerce-Gesetz
        </Motion>
      </template>
    </UPageHero>

    <!-- Content -->
    <UPageSection
      :ui="{
        container: 'max-w-2xl'
      }"
    >
      <Motion v-bind="scrollMotion(0)">
        <div class="space-y-16 text-sm leading-relaxed text-dimmed">
          <!-- Dienstanbieter -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Dienstanbieter
            </h2>
            <p class="text-default font-medium">
              GO.WEST Communications GmbH
            </p>
            <p>Panzerhalle</p>
            <p>Siezenheimerstraße 39 B</p>
            <p>5020 Salzburg</p>
          </div>

          <!-- Kontakt -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Kontakt
            </h2>
            <p>
              E-Mail:
              <a
                href="mailto:office@go-west.at"
                class="text-violet-400 hover:text-violet-300 transition-colors"
              >office@go-west.at</a>
            </p>
            <p>
              Telefon:
              <a
                href="tel:+43662880540"
                class="text-violet-400 hover:text-violet-300 transition-colors"
              >+43-662-880540</a>
            </p>
          </div>

          <!-- Unternehmensdetails -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Unternehmensdetails
            </h2>
            <p>
              Geschäftsführung: <span class="text-default">Armin Stadlmeyer</span>
            </p>
            <p>
              Firmenbuchgericht: <span class="text-default">Landesgericht Salzburg</span>
            </p>
            <p>
              Firmenbuchnummer: <span class="text-default font-mono">FN205124d</span>
            </p>
            <p>
              UID: <span class="text-default font-mono">ATU50994401</span>
            </p>
          </div>

          <!-- Berufsrecht -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Berufsrecht
            </h2>
            <p>
              WKO-Fachgruppe: <span class="text-default">Werbung und Marktkommunikation</span>
            </p>
            <p>
              Berufsgruppe: <span class="text-default">Werbeagentur</span>
            </p>
          </div>

          <!-- Streitschlichtung -->
          <div class="space-y-2">
            <h2 class="font-mono uppercase text-xs tracking-[0.12em] text-violet-400 mb-3">
              Online-Streitbeilegung
            </h2>
            <p>
              Die Europäische Kommission stellt eine Plattform zur außergerichtlichen Streitschlichtung bereit:
              <a
                href="https://ec.europa.eu/consumers/odr"
                target="_blank"
                rel="noopener noreferrer"
                class="text-violet-400 hover:text-violet-300 transition-colors"
              >ec.europa.eu/consumers/odr</a>
            </p>
          </div>
        </div>
      </Motion>
    </UPageSection>

    <!-- Ambient glow bottom -->
    <div class="pointer-events-none relative">
      <div class="absolute -top-48 right-[-5%] w-[600px] h-[600px] rounded-full blur-[100px] bg-violet-500/[0.06]" />
      <div class="absolute -top-20 left-[-10%] w-[350px] h-[350px] rounded-full blur-[80px] bg-fuchsia-400/[0.04]" />
    </div>
  </div>
</template>
