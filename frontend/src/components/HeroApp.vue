<script setup>
import { onMounted, ref } from 'vue'

const isVideoReady = ref(false)
const videoRef = ref(null)
const isPlaying = ref(false)
const onVideoReady = () => {
  isVideoReady.value = true
}
const tryPlay = () => {
  const video = videoRef.value
  if (video) {
    video.muted = true
    video.play().catch(() => {})
  }
}
const onPlay = () => {
  isPlaying.value = true
}
const onPause = () => {
  isPlaying.value = false
}

onMounted(() => {
  const video = videoRef.value
  if (video) {
    video.muted = true
    video.setAttribute('playsinline', '')
    video.setAttribute('webkit-playsinline', '')
    video.load()
  }
  tryPlay()
})
</script>

<template>
  <section class="reveal-section w-full" @touchstart="tryPlay" @click="tryPlay">
    <div class="relative h-[420px] w-full overflow-hidden bg-black">
      <video
        ref="videoRef"
        class="absolute inset-0 h-full w-full object-cover"
        src="/video/HeroBlock.mp4"
        autoplay
        muted
        loop
        playsinline
        preload="auto"
        @loadeddata="onVideoReady"
        @canplay="onVideoReady"
        @play="onPlay"
        @pause="onPause"
      ></video>
      <div v-if="!isVideoReady" class="absolute inset-0 flex items-center justify-center bg-black/30">
        <div class="video-loader"></div>
      </div>
      <button
        v-if="isVideoReady && !isPlaying"
        class="absolute inset-0 flex items-center justify-center text-white/90"
        type="button"
        aria-label="Play video"
      >
        <span class="rounded-full bg-black/50 px-4 py-2 text-[10px] font-montserrat uppercase tracking-[0.18em]">
          Tap To Play
        </span>
      </button>
      <div class="absolute inset-0 bg-black/10"></div>
      <div class="relative mx-auto flex h-full w-full max-w-[1280px] items-center px-6">
        <div class="max-w-[520px] text-white">
          <h1 class="text-[36px] font-semibold leading-tight">
            Powered by Pulse.<br>
            Grounded in Nature.
          </h1>
          <p class="mt-3 text-[12px] leading-relaxed text-white/85">
            Advanced pulsed-LED therapy paired with synergistic skincare
            formulas. Welcome to the future of at-home skin care.
          </p>
          <button
            class="btn-primary mt-5 rounded-full px-5 py-2 text-[10px] font-montserrat uppercase tracking-[0.16em]"
            type="button"
          >
            Shop Maysama
          </button>
        </div>
      </div>
    </div>

    <div class="bg-[#f4e9e3] py-12">
      <div class="mx-auto w-full max-w-[780px] px-6 text-center">
        <h2 class="text-[22px] font-semibold uppercase tracking-[0.18em] text-black/80">
          Optimising <span class="text-[var(--color-primary)]">Skin</span> Health
        </h2>
        <p class="mx-auto mt-4 max-w-[620px] text-[12px] leading-relaxed text-black/60">
          Maysama combines AEG-rooibos with LED Light Therapy to accelerate and amplify
          results for skin rejuvenation. Our unique bioactive ingredient, Aspalathin-enriched
          Green Rooibos Extract, is proven to complement the action of your red light device
          and increase the efficacy to help tackle signs of aging.
        </p>
        <button
          class="btn-primary mt-6 rounded-full px-6 py-2 text-[10px] font-montserrat uppercase tracking-[0.14em]"
          type="button"
        >
          Learn More
        </button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.video-loader {
  width: 36px;
  height: 36px;
  border: 3px solid rgba(255, 255, 255, 0.4);
  border-top-color: #ffffff;
  border-radius: 50%;
  animation: spin 800ms linear infinite;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}
</style>
