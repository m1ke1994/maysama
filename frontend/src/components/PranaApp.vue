<script setup>
import { onBeforeUnmount, onMounted, ref } from 'vue'

const sectionRef = ref(null)
let observer
const isVideoReady = ref(false)
const videoRef = ref(null)
const onVideoReady = () => {
  isVideoReady.value = true
}
const tryPlay = () => {
  const video = videoRef.value
  if (video) {
    video.play().catch(() => {})
  }
}

onMounted(() => {
  observer = new IntersectionObserver(
    ([entry]) => {
      if (entry.isIntersecting) {
        entry.target.classList.add('is-visible')
        observer?.disconnect()
      }
    },
    { threshold: 0.35 }
  )

  if (sectionRef.value) {
    observer.observe(sectionRef.value)
  }

  tryPlay()
})

onBeforeUnmount(() => {
  observer?.disconnect()
})
</script>

<template>
  <section ref="sectionRef" class="prana-section reveal-section relative w-full overflow-hidden bg-[#f4e6df]">
    <video
      ref="videoRef"
      class="absolute inset-0 h-full w-full object-cover"
      src="/video/Hero-2.mp4"
      autoplay
      muted
      loop
      playsinline
      preload="auto"
      @loadeddata="onVideoReady"
      @canplay="onVideoReady"
      @click="tryPlay"
    ></video>
    <div v-if="!isVideoReady" class="absolute inset-0 flex items-center justify-center bg-[#f4e6df]/70">
      <div class="video-loader"></div>
    </div>
    <div class="absolute inset-0 bg-[#f4e6df]/70"></div>

    <div class="relative mx-auto w-full max-w-[1280px] px-8 py-16">
      <div class="max-w-[720px] text-black/80">
        <div class="prana-title text-[72px] font-light uppercase tracking-[0.28em] text-white/70">
          PRANA
        </div>
        <div class="fade-in mt-2 text-[16px] font-montserrat uppercase tracking-[0.3em] text-black/60">
          Breathe Life Into Your Skin
        </div>
        <p class="fade-in mt-6 text-[16px] leading-relaxed text-black/60">
          Harness the power of <span class="font-bold text-black/70">super-pulsed light technology</span>
          with our cutting-edge <span class="text-[var(--color-primary)] underline underline-offset-4">PRANA LED Light Therapy Mask</span>,
          optimising results for anti-aging and skin rejuvenation.
        </p>
        <p class="fade-in mt-6 text-[16px] font-semibold text-black/70">
          Experience the future of skincare today.
        </p>
        <button
          class="btn-primary fade-in mt-8 rounded-lg px-8 py-3 text-[12px] font-montserrat uppercase tracking-[0.2em] shadow-sm"
          type="button"
        >
          Shop Now
        </button>
      </div>
    </div>
  </section>
</template>

<style scoped>
@keyframes slide-in-left {
  from {
    opacity: 0;
    transform: translateX(-24px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fade-up {
  from {
    opacity: 0;
    transform: translateY(12px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.prana-title,
.fade-in {
  opacity: 0;
}

.prana-section.is-visible .prana-title {
  animation: slide-in-left 700ms ease forwards;
}

.prana-section.is-visible .fade-in {
  animation: fade-up 700ms ease forwards;
  animation-delay: 120ms;
}

.prana-section.is-visible .fade-in:nth-of-type(2) {
  animation-delay: 220ms;
}

.prana-section.is-visible .fade-in:nth-of-type(3) {
  animation-delay: 320ms;
}

.prana-section.is-visible .fade-in:nth-of-type(4) {
  animation-delay: 420ms;
}

.video-loader {
  width: 36px;
  height: 36px;
  border: 3px solid rgba(0, 0, 0, 0.2);
  border-top-color: rgba(0, 0, 0, 0.7);
  border-radius: 50%;
  animation: spin 800ms linear infinite;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}
</style>
