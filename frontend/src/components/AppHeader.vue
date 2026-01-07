<script setup>
import { onBeforeUnmount, onMounted, ref, watch } from 'vue'

const isMenuOpen = ref(false)
const mobileSubmenu = ref('')
const headerRef = ref(null)

const updateHeaderHeight = () => {
  if (headerRef.value) {
    headerRef.value.style.setProperty('--header-height', `${headerRef.value.offsetHeight}px`)
  }
}

onMounted(() => {
  updateHeaderHeight()
  window.addEventListener('resize', updateHeaderHeight)
})

onBeforeUnmount(() => {
  window.removeEventListener('resize', updateHeaderHeight)
})

watch(isMenuOpen, (open) => {
  document.body.style.overflow = open ? 'hidden' : ''
})
</script>

<template>
  <header ref="headerRef" class="header relative z-50 w-full">
    <div class="top_header w-full bg-[var(--color-background)] border-b border-black/10">
      <div class="mx-auto hidden w-full max-w-[1280px] items-center justify-between px-4 py-2 max-[1200px]:hidden min-[1201px]:flex">
        <div class="flex items-center gap-3">
          <img class="block h-4 w-4" src="/logo/Maysama_logo.svg" alt="Maysama">
          <span class="text-[11px] font-montserrat uppercase tracking-[0.12em] text-black font-bold">
            Advanced LED Therapy Powered by Nature's Green Rooibos
          </span>
        </div>

        <div class="flex items-center gap-3">
          <div class="relative inline-flex items-center">
            <select
              class="appearance-none rounded-full border border-[var(--color-primary)] bg-white px-3 py-1 pr-6 text-[10px] font-montserrat uppercase tracking-[0.12em] text-[var(--color-primary)]"
            >
              <option>EUR &euro;</option>
              <option>USD $</option>
              <option selected>GBP &pound;</option>
              <option>CAD $</option>
              <option>AUD $</option>
            </select>
            <svg class="pointer-events-none absolute right-2 h-2 w-2 text-[var(--color-primary)]" viewBox="0 0 8 6" aria-hidden="true">
              <path d="M1 1.5L4 4.5L7 1.5" fill="none" stroke="currentColor" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round" />
            </svg>
          </div>
          <ul class="flex items-center gap-3">
            <li><img class="block h-4 w-4 min-[1201px]:h-9 min-[1201px]:w-9 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons/Link.svg" alt="icon"></li>
            <li><img class="block h-4 w-4 min-[1201px]:h-9 min-[1201px]:w-9 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons/Link-1.svg" alt="icon"></li>
            <li><img class="block h-4 w-4 min-[1201px]:h-9 min-[1201px]:w-9 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons/Link-2.svg" alt="icon"></li>
            <li><img class="block h-4 w-4 min-[1201px]:h-9 min-[1201px]:w-9 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons/Link.svg" alt="icon"></li>
            <li><img class="block h-4 w-4 min-[1201px]:h-9 min-[1201px]:w-9 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons/Link-3.svg" alt="icon"></li>
            <li><img class="block h-4 w-4 min-[1201px]:h-9 min-[1201px]:w-9 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons/Link-4.svg" alt="icon"></li>
          </ul>
        </div>
      </div>

      <div class="mx-auto hidden w-full max-w-[1280px] flex-col gap-2 px-4 py-2 text-center max-[1200px]:flex">
        <span class="text-[10px] font-montserrat uppercase tracking-[0.16em] text-black font-bold">
          Advanced LED Therapy Powered by Nature's Green Rooibos
        </span>
        <div class="flex items-center justify-center gap-3">
          <div class="relative inline-flex items-center">
            <select
              class="appearance-none rounded-full border border-[var(--color-primary)] bg-white px-3 py-1 pr-6 text-[10px] font-montserrat uppercase tracking-[0.12em] text-[var(--color-primary)]"
            >
              <option>EUR &euro;</option>
              <option>USD $</option>
              <option selected>GBP &pound;</option>
              <option>CAD $</option>
              <option>AUD $</option>
            </select>
            <svg class="pointer-events-none absolute right-2 h-2 w-2 text-[var(--color-primary)]" viewBox="0 0 8 6" aria-hidden="true">
              <path d="M1 1.5L4 4.5L7 1.5" fill="none" stroke="currentColor" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round" />
            </svg>
          </div>
          <ul class="flex items-center gap-2">
            <li><img class="block h-7 w-7 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons/Link.svg" alt="icon"></li>
            <li><img class="block h-7 w-7 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons/Link-1.svg" alt="icon"></li>
            <li><img class="block h-7 w-7 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons/Link-2.svg" alt="icon"></li>
            <li><img class="block h-7 w-7 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons/Link.svg" alt="icon"></li>
            <li><img class="block h-7 w-7 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons/Link-3.svg" alt="icon"></li>
            <li><img class="block h-7 w-7 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons/Link-4.svg" alt="icon"></li>
          </ul>
        </div>
      </div>
    </div>

    <div class="bottom_header w-full border-b border-black/10">
      <div class="mx-auto hidden w-full max-w-[1280px] items-center justify-between px-4 py-4 min-[1201px]:flex">
        <div class="flex items-center gap-8">
          <div class="flex flex-col items-center">
            <img class="block h-7 w-auto" src="/logo/Maysama_logo_header.svg" alt="Maysama">
            <span class="mt-1 text-[10px] font-montserrat font-bold uppercase tracking-[0.2em] text-black">
              Maysama
            </span>
          </div>
          <nav>
            <ul class="flex items-center gap-5 text-[11px] font-montserrat uppercase tracking-[0.14em] text-black/80">
              <li class="nav-link">Home</li>
              <li class="nav-link">Shop</li>
              <li class="nav-link relative inline-flex items-center">
                <select
                  class="nav-select appearance-none bg-transparent text-[11px] font-montserrat uppercase tracking-[0.14em] text-black/80  w-[120px]"
                >
                  <option>How It Works</option>
                  <option>Pulsed LED</option>
                  <option>Green Rooibos &amp; LED</option>
                </select>
                <svg class="pointer-events-none absolute right-0.5 h-2 w-2" viewBox="0 0 8 6" aria-hidden="true">
                  <path d="M1 1.5L4 4.5L7 1.5" fill="none" stroke="currentColor" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round" />
                </svg>
              </li>
              <li class="nav-link relative inline-flex items-center">
                <select
                  class="nav-select appearance-none bg-transparent text-[11px] font-montserrat uppercase tracking-[0.14em] text-black/80 w-[80px]"
                >
                  <option>Rooibos</option>
                  <option>The Story</option>
                  <option>The Science</option>
                </select>
                <svg class="pointer-events-none absolute right-0.5 h-2 w-2" viewBox="0 0 8 6" aria-hidden="true">
                  <path d="M1 1.5L4 4.5L7 1.5" fill="none" stroke="currentColor" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round" />
                </svg>
              </li>
              <li class="nav-link">About</li>
              <li class="nav-link">Blog</li>
              <li class="nav-link">Before &amp; Afters</li>
              <li class="nav-link">Help</li>
              <li class="nav-link">Multibuy</li>
            </ul>
          </nav>
        </div>

        <div class="flex items-center gap-4">
          <img class="block h-4 w-4 cursor-pointer transition-transform duration-150 hover:scale-110 min-[1201px]:h-8 min-[1201px]:w-8" src="/icons_site/Link-1.svg" alt="search">
          <img class="block h-4 w-4 cursor-pointer transition-transform duration-150 hover:scale-110 min-[1201px]:h-8 min-[1201px]:w-8" src="/icons_site/Link-2.svg" alt="account">
          <img class="block h-4 w-4 cursor-pointer transition-transform duration-150 hover:scale-110 min-[1201px]:h-8 min-[1201px]:w-8" src="/icons_site/Link.svg" alt="cart">
        </div>
      </div>

      <div class="mx-auto relative flex w-full max-w-[1280px] items-center justify-between px-4 py-3 min-[1201px]:hidden">
        <button
          class="flex h-8 w-8 items-center justify-center"
          type="button"
          :aria-label="isMenuOpen ? 'Close menu' : 'Open menu'"
          @click="isMenuOpen = !isMenuOpen; mobileSubmenu = ''"
        >
          <span v-if="!isMenuOpen" class="flex flex-col items-center justify-center gap-1">
            <span class="block h-[2px] w-5 bg-black/80"></span>
            <span class="block h-[2px] w-5 bg-black/80"></span>
            <span class="block h-[2px] w-5 bg-black/80"></span>
          </span>
          <span v-else class="flex items-center justify-center">
            <span class="relative block h-[2px] w-5 rotate-45 bg-black/80"></span>
            <span class="relative -ml-5 block h-[2px] w-5 -rotate-45 bg-black/80"></span>
          </span>
        </button>
        <div class="absolute left-1/2 -translate-x-1/2 flex flex-col items-center">
          <img class="block h-9 w-auto" src="/logo/Maysama_logo_header.svg" alt="Maysama">
          <span class="mt-1 text-[10px] font-montserrat font-bold uppercase tracking-[0.2em] text-black">
            Maysama
          </span>
        </div>
        <div class="flex items-center gap-3">
          <img class="block h-7 w-7 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons_site/Link-1.svg" alt="search">
          <img class="block h-7 w-7 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons_site/Link-2.svg" alt="account">
          <img class="block h-7 w-7 cursor-pointer transition-transform duration-150 hover:scale-110" src="/icons_site/Link.svg" alt="cart">
        </div>
      </div>
    </div>

    <transition name="menu-slide">
      <div
        v-if="isMenuOpen"
        class="fixed inset-x-0 z-40 flex w-full flex-col bg-white min-[1201px]:hidden"
        role="dialog"
        aria-modal="true"
        style="top: var(--header-height); height: calc(100vh - var(--header-height));"
      >
      <div class="flex-1 overflow-y-auto">
        <nav class="px-4 py-3">
          <transition name="submenu-slide" mode="out-in">
          <div v-if="mobileSubmenu === ''" key="main">
            <ul class="space-y-3 text-[12px] font-montserrat uppercase tracking-[0.18em] text-black/80">
              <li class="border-b border-black/5 pb-3">Home</li>
              <li class="border-b border-black/5 pb-3">Shop</li>
              <li class="flex items-center justify-between border-b border-black/5 pb-3">
                <button class="flex w-full items-center justify-between" type="button" @click="mobileSubmenu = 'how'">
                  <span>How It Works</span>
                  <span class="text-black/40">&rarr;</span>
                </button>
              </li>
              <li class="flex items-center justify-between border-b border-black/5 pb-3">
                <button class="flex w-full items-center justify-between" type="button" @click="mobileSubmenu = 'rooibos'">
                  <span>Rooibos</span>
                  <span class="text-black/40">&rarr;</span>
                </button>
              </li>
              <li class="border-b border-black/5 pb-3">About</li>
              <li class="border-b border-black/5 pb-3">Blog</li>
              <li class="border-b border-black/5 pb-3">Before &amp; Afters</li>
              <li class="border-b border-black/5 pb-3">Help</li>
              <li class="pb-3">Multibuy</li>
            </ul>
          </div>

          <div v-else-if="mobileSubmenu === 'how'" key="how">
            <div class="flex items-center gap-2 border-b border-black/5 pb-3 text-[12px] font-montserrat uppercase tracking-[0.18em] text-black/80">
              <button type="button" class="text-black/50" @click="mobileSubmenu = ''">&larr;</button>
              <span>How It Works</span>
            </div>
            <ul class="mt-3 space-y-3 text-[12px] font-montserrat uppercase tracking-[0.18em] text-black/80">
              <li class="border-b border-black/5 pb-3">Pulsed LED</li>
              <li class="border-b border-black/5 pb-3">Green Rooibos &amp; LED</li>
            </ul>
          </div>

          <div v-else-if="mobileSubmenu === 'rooibos'" key="rooibos">
            <div class="flex items-center gap-2 border-b border-black/5 pb-3 text-[12px] font-montserrat uppercase tracking-[0.18em] text-black/80">
              <button type="button" class="text-black/50" @click="mobileSubmenu = ''">&larr;</button>
              <span>Rooibos</span>
            </div>
            <ul class="mt-3 space-y-3 text-[12px] font-montserrat uppercase tracking-[0.18em] text-black/80">
              <li class="border-b border-black/5 pb-3">The Story</li>
              <li class="border-b border-black/5 pb-3">The Science</li>
            </ul>
          </div>
          </transition>
        </nav>
      </div>

      <div class="border-t border-black/10 px-4 py-4 text-[12px] text-black/70">
        <div class="flex items-center gap-2">
          <img class="h-4 w-4" src="/icons_site/Link-2.svg" alt="account">
          <span class="font-semibold">Log in</span>
        </div>
        <div class="mt-3 flex items-center justify-between border-b border-black/5 pb-2">
          <span>EUR &euro; | Netherlands</span>
          <span class="text-black/40">&or;</span>
        </div>
        <div class="mt-2 flex items-center justify-between">
          <span>English</span>
          <span class="text-black/40">&or;</span>
        </div>
        <div class="mt-4 flex items-center gap-4">
          <img class="h-10 w-10" src="/icons/Link.svg" alt="social">
          <img class="h-10 w-10" src="/icons/Link-1.svg" alt="social">
          <img class="h-10 w-10" src="/icons/Link-2.svg" alt="social">
          <img class="h-10 w-10" src="/icons/Link-3.svg" alt="social">
          <img class="h-10 w-10" src="/icons/Link-4.svg" alt="social">
        </div>
      </div>

      </div>
    </transition>
  </header>
</template>

<style scoped>
.nav-link {
  position: relative;
  cursor: pointer;
}

.nav-link::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: -2px;
  width: 100%;
  height: 1px;
  background-color: rgba(0, 0, 0, 0.8);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 150ms ease;
}

.nav-link:hover::after {
  transform: scaleX(1);
}
</style>

<style scoped>
.nav-select option {
  background-color: transparent;
  color: #000000;
  
  
}
</style>

<style scoped>
.menu-slide-enter-active,
.menu-slide-leave-active {
  transition: transform 250ms ease, opacity 250ms ease;
}

.menu-slide-enter-from,
.menu-slide-leave-to {
  transform: translateX(-100%);
  opacity: 0;
}

.menu-slide-enter-to,
.menu-slide-leave-from {
  transform: translateX(0);
  opacity: 1;
}

.submenu-slide-enter-active,
.submenu-slide-leave-active {
  transition: transform 200ms ease, opacity 200ms ease;
}

.submenu-slide-enter-from,
.submenu-slide-leave-to {
  transform: translateX(12px);
  opacity: 0;
}

.submenu-slide-enter-to,
.submenu-slide-leave-from {
  transform: translateX(0);
  opacity: 1;
}
</style>

