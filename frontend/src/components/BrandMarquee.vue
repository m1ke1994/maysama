<template>
  <section class="reveal-section bg-[#f4e9e3] py-6">
    <div class="overflow-hidden">
      <div class="marquee-track">
        <div class="marquee-group">
          <div class="brand-item flex items-center gap-3">
            <span class="text-[30px]">*</span>
            <span>The Vegan</span>
          </div>
          <span class="brand-item tracking-[0.3em]">TATLER</span>
          <div class="brand-item text-center leading-none">
            <div class="text-[22px] font-semibold">YOU</div>
            <div class="text-[12px] tracking-[0.3em]">MAGAZINE</div>
          </div>
          <span class="brand-item text-[28px] font-semibold">VOGUE</span>
          <span class="brand-item tracking-[0.22em] hide-lg">ELLE</span>
          <span class="brand-item tracking-[0.22em] hide-lg">GLAMOUR</span>
          <span class="brand-item tracking-[0.22em] hide-md">HARPER'S BAZAAR</span>
        </div>
        <div class="marquee-group" aria-hidden="true">
          <div class="brand-item flex items-center gap-3">
            <span class="text-[30px]">*</span>
            <span>The Vegan</span>
          </div>
          <span class="brand-item tracking-[0.3em]">TATLER</span>
          <div class="brand-item text-center leading-none">
            <div class="text-[22px] font-semibold">YOU</div>
            <div class="text-[12px] tracking-[0.3em]">MAGAZINE</div>
          </div>
          <span class="brand-item text-[28px] font-semibold">VOGUE</span>
          <span class="brand-item tracking-[0.22em] hide-lg">ELLE</span>
          <span class="brand-item tracking-[0.22em] hide-lg">GLAMOUR</span>
          <span class="brand-item tracking-[0.22em] hide-md">HARPER'S BAZAAR</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
@keyframes marquee-scroll {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}

.marquee-track {
  display: flex;
  width: 200%;
  animation: marquee-scroll 24s linear infinite;
}

.marquee-group {
  display: flex;
  align-items: center;
  gap: 5rem;
  width: 50%;
  flex: 0 0 50%;
  font-size: 32px;
  font-weight: 600;
  color: rgba(0, 0, 0, 0.8);
  white-space: nowrap;
}

.brand-item {
  flex: 0 0 auto;
  white-space: nowrap;
}

@media (max-width: 1200px) {
  .hide-lg {
    display: none;
  }
}

@media (max-width: 1024px) {
  .hide-md {
    display: none;
  }

  .marquee-group {
    gap: 1.5rem;
    font-size: 18px;
  }

  .marquee-group .text-\[30px\] {
    font-size: 20px;
  }

  .marquee-group .text-\[22px\] {
    font-size: 14px;
  }

  .marquee-group .text-\[28px\] {
    font-size: 18px;
  }
}

@media (max-width: 640px) {
  .hide-sm {
    display: none;
  }

  .marquee-group {
    gap: 1rem;
    font-size: 14px;
  }

  .marquee-group .text-\[30px\] {
    font-size: 16px;
  }

  .marquee-group .text-\[22px\] {
    font-size: 12px;
  }

  .marquee-group .text-\[28px\] {
    font-size: 14px;
  }

  .marquee-group .text-\[12px\] {
    font-size: 10px;
  }
}
</style>
