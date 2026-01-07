<script setup>
import AppHeader from '../components/AppHeader.vue'
import HeroApp from '../components/HeroApp.vue'
import MaysamaShop from '../components/MaysamaShop.vue'
import PranaApp from '../components/PranaApp.vue'
import DoubleWhammy from '../components/DoubleWhammy.vue'
import ShopThePulse from '../components/ShopThePulse.vue'
import FeaturedArticles from '../components/FeaturedArticles.vue'
import MaysamaBlog from '../components/MaysamaBlog.vue'
import BrandMarquee from '../components/BrandMarquee.vue'
import AppFooter from '../components/AppFooter.vue'
import { nextTick, onBeforeUnmount, onMounted, watch } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
let observer

const observeSections = () => {
  if (observer) {
    observer.disconnect()
  }
  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('is-visible')
          observer.unobserve(entry.target)
        }
      })
    },
    { threshold: 0.15 }
  )

  document.querySelectorAll('.reveal-section').forEach((el) => observer.observe(el))
}

onMounted(() => {
  observeSections()
})

watch(
  () => route.fullPath,
  async () => {
    await nextTick()
    observeSections()
  }
)

onBeforeUnmount(() => {
  observer?.disconnect()
})

</script>

<template>
  <div class="min-h-screen">
    <AppHeader />
    <HeroApp />
    <MaysamaShop />
    <PranaApp />
    <DoubleWhammy />
    <ShopThePulse />
    <FeaturedArticles />
    <MaysamaBlog />
    <BrandMarquee />
    <AppFooter />
  </div>
</template>

