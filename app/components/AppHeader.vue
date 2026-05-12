<script setup lang="ts">
import { motion } from 'motion-v'
import type { VariantType } from 'motion-v'

const route = useRoute()
const nuxtApp = useNuxtApp()
const colorMode = useColorMode()
const activeSection = ref<string>()

const currentProduct = computed(() => {
  if (route.path === '/promohero') return 'promohero'
  if (route.path === '/triguest') return 'triguest'
  if (route.path === '/topaccess') return 'topaccess'
  return 'overview'
})

const overviewItems = [
  { label: 'PromoHero', to: '/promohero' },
  { label: 'TriGuest', to: '/triguest' },
  { label: 'TopAccess', to: '/topaccess' }
]

const promoHeroItems = [
  { label: 'Vorteile', to: '#vorteile', exactHash: true },
  { label: 'So funktioniert\'s', to: '#so-funktionierts', exactHash: true },
  { label: 'Features', to: '#features', exactHash: true },
  { label: 'Einsatzbereiche', to: '#einsatzbereiche', exactHash: true }
]

const triGuestItems = [
  { label: 'Analyse', to: '#analyse', exactHash: true },
  { label: 'Setup', to: '#voraussetzungen', exactHash: true },
  { label: 'Vorteile', to: '#vorteile', exactHash: true },
  { label: 'Ablauf', to: '#so-funktionierts', exactHash: true }
]

const topAccessItems = [
  { label: 'Vorteile', to: '#vorteile', exactHash: true },
  { label: 'Features', to: '#features', exactHash: true },
  { label: 'Einsatzbereiche', to: '#einsatzbereiche', exactHash: true },
  { label: 'Preise', to: '#preise', exactHash: true }
]

const navMap = {
  overview: overviewItems,
  promohero: promoHeroItems,
  triguest: triGuestItems,
  topaccess: topAccessItems
} as Record<string, { label: string, to: string, exactHash?: boolean }[]>

const items = computed(() => {
  const baseItems = navMap[currentProduct.value] || overviewItems
  return baseItems.map(item => ({
    ...item,
    active: activeSection.value === item.to.replace('#', '')
  }))
})

const sectionIds = computed(() =>
  items.value.map(i => i.to.replace('#', ''))
)

nuxtApp.hooks.hookOnce('page:loading:end', () => {
  const observer = new IntersectionObserver((entries) => {
    const visible = entries.find(e => e.isIntersecting)
    if (visible) {
      activeSection.value = visible.target.id
    } else if (entries.every(e => !e.isIntersecting)) {
      activeSection.value = undefined
    }
  }, { rootMargin: '-50% 0px -50% 0px' })

  sectionIds.value.forEach((id) => {
    const el = document.getElementById(id)
    if (el) observer.observe(el)
  })
})

const otherProducts = computed(() => {
  const all = [
    { label: 'PromoHero', to: '/promohero' },
    { label: 'TriGuest', to: '/triguest' },
    { label: 'TopAccess', to: '/topaccess' }
  ]
  return all.filter(p => p.to !== route.path)
})

const ctaConfig = computed(() => {
  if (currentProduct.value === 'triguest') {
    return { label: 'Angebot anfragen', class: 'bg-teal-500 hover:bg-teal-400 text-white transition-all duration-200 font-semibold' }
  }
  if (currentProduct.value === 'topaccess') {
    return { label: 'Jetzt starten', class: 'bg-gradient-to-r from-amber-500 to-orange-500 hover:from-amber-400 hover:to-orange-400 text-white transition-all duration-200 font-semibold' }
  }
  return { label: 'Jetzt starten', class: 'bg-gradient-to-r from-violet-500 to-fuchsia-500 hover:from-violet-400 hover:to-fuchsia-400 text-white transition-all duration-200 font-semibold' }
})

const variants: Record<string, VariantType | ((custom: unknown) => VariantType)> = {
  normal: {
    rotate: 0,
    y: 0,
    opacity: 1
  },
  close: (custom: unknown) => {
    const c = custom as number
    return {
      rotate: c === 1 ? 45 : c === 3 ? -45 : 0,
      y: c === 1 ? 6 : c === 3 ? -6 : 0,
      opacity: c === 2 ? 0 : 1,
      transition: {
        type: 'spring',
        stiffness: 260,
        damping: 20
      }
    }
  }
}
</script>

<template>
  <UHeader>
    <template #left>
      <NuxtLink to="/">
        <AppLogo v-if="currentProduct === 'promohero'" />
        <TopAccessLogo v-else-if="currentProduct === 'topaccess'" />
        <span v-else-if="currentProduct === 'triguest'" class="flex items-center gap-1.5 font-bold text-lg tracking-tight">
          <span class="flex items-center justify-center size-7 rounded-lg bg-teal-500 text-white text-sm font-black">T</span>
          <span class="flex flex-col leading-none">
            <span>Tri<span class="text-teal-400">Guest</span></span>
            <span class="text-[9px] font-normal text-dimmed tracking-wide">by GO.WEST</span>
          </span>
        </span>
        <span v-else class="flex items-center gap-1.5 font-bold text-lg tracking-tight">
          <span class="flex items-center justify-center size-7 rounded-lg bg-gradient-to-br from-violet-500 via-teal-500 to-amber-500 text-white text-sm font-black">t</span>
          <span class="flex flex-col leading-none">
            <span>tri<span class="text-transparent bg-clip-text bg-gradient-to-r from-violet-400 via-teal-400 to-amber-400">vio</span></span>
            <span class="text-[9px] font-normal text-dimmed tracking-wide">by GO.WEST</span>
          </span>
        </span>
      </NuxtLink>

      <template v-if="currentProduct !== 'overview'">
        <NuxtLink
          v-for="product in otherProducts"
          :key="product.to"
          :to="product.to"
          class="hidden lg:inline-flex text-xs text-dimmed hover:text-default transition-colors ml-1.5 border border-default rounded-full px-2.5 py-1"
        >
          {{ product.label }}
        </NuxtLink>
      </template>
    </template>

    <UNavigationMenu
      :items="items"
      variant="link"
    />

    <template #right>
      <UButton
        :icon="colorMode.value === 'dark' ? 'i-lucide-sun' : 'i-lucide-moon'"
        variant="ghost"
        color="neutral"
        square
        :aria-label="colorMode.value === 'dark' ? 'Helles Design aktivieren' : 'Dunkles Design aktivieren'"
        class="hidden lg:flex"
        @click="colorMode.preference = colorMode.value === 'dark' ? 'light' : 'dark'"
      />
      <template v-if="currentProduct !== 'overview'">
        <UButton
          :label="ctaConfig.label"
          :class="['hidden lg:flex', ctaConfig.class]"
          to="#kontakt"
        />
      </template>
    </template>

    <template #toggle="{ open, toggle, ui }">
      <UButton
        size="sm"
        variant="ghost"
        color="neutral"
        square
        :aria-label="open ? 'Navigation schließen' : 'Navigation öffnen'"
        :aria-expanded="open"
        :class="ui.toggle({ toggleSide: 'right' })"
        @click="toggle"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="size-5"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <motion.line
            x1="4"
            y1="6"
            x2="20"
            y2="6"
            :variants="variants"
            :animate="open ? 'close' : 'normal'"
            :custom="1"
            class="outline-none"
          />
          <motion.line
            x1="4"
            y1="12"
            x2="20"
            y2="12"
            :variants="variants"
            :animate="open ? 'close' : 'normal'"
            :custom="2"
            class="outline-none"
          />
          <motion.line
            x1="4"
            y1="18"
            x2="20"
            y2="18"
            :variants="variants"
            :animate="open ? 'close' : 'normal'"
            :custom="3"
            class="outline-none"
          />
        </svg>
      </UButton>
    </template>

    <template #body>
      <UNavigationMenu
        :items="items"
        orientation="vertical"
      />

      <div class="mt-4 flex flex-col gap-2">
        <UButton
          :icon="colorMode.value === 'dark' ? 'i-lucide-sun' : 'i-lucide-moon'"
          :label="colorMode.value === 'dark' ? 'Helles Design' : 'Dunkles Design'"
          variant="ghost"
          color="neutral"
          block
          @click="colorMode.preference = colorMode.value === 'dark' ? 'light' : 'dark'"
        />
      </div>
      <div v-if="currentProduct !== 'overview'" class="mt-2 flex flex-col gap-2">
        <NuxtLink
          v-for="product in otherProducts"
          :key="product.to"
          :to="product.to"
          class="text-sm text-dimmed hover:text-default transition-colors text-center py-2"
        >
          {{ product.label }} entdecken →
        </NuxtLink>
        <UButton
          :label="ctaConfig.label"
          block
          :class="ctaConfig.class"
          to="#kontakt"
        />
      </div>
    </template>
  </UHeader>
</template>
