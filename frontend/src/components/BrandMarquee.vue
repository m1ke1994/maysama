<template>
  <section class="bg-[#f4e9e3] py-6">
    <div class="overflow-hidden">
      <div class="marquee-track">
        <div class="marquee-group">
          <div class="flex items-center gap-3">
            <span class="text-[30px]">✿</span>
            <span>The Vegan</span>
          </div>
          <span class="tracking-[0.3em]">TATLER</span>
          <div class="text-center leading-none">
            <div class="text-[22px] font-semibold">YOU</div>
            <div class="text-[12px] tracking-[0.3em]">MAGAZINE</div>
          </div>
          <span class="text-[28px] font-semibold">VOGUE</span>
          <span class="tracking-[0.22em]">ELLE</span>
          <span class="tracking-[0.22em]">GLAMOUR</span>
          <span class="tracking-[0.22em]">HARPER'S BAZAAR</span>
        </div>
        <div class="marquee-group" aria-hidden="true">
          <div class="flex items-center gap-3">
            <span class="text-[30px]">✿</span>
            <span>The Vegan</span>
          </div>
          <span class="tracking-[0.3em]">TATLER</span>
          <div class="text-center leading-none">
            <div class="text-[22px] font-semibold">YOU</div>
            <div class="text-[12px] tracking-[0.3em]">MAGAZINE</div>
          </div>
          <span class="text-[28px] font-semibold">VOGUE</span>
          <span class="tracking-[0.22em]">ELLE</span>
          <span class="tracking-[0.22em]">GLAMOUR</span>
          <span class="tracking-[0.22em]">HARPER'S BAZAAR</span>
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
  animation: marquee-scroll 18s linear infinite;
}

.marquee-group {
  display: flex;
  align-items: center;
  gap: 6rem;
  width: 50%;
  flex: 0 0 50%;
  font-size: 28px;
  font-weight: 600;
  color: rgba(0, 0, 0, 0.8);
  white-space: nowrap;
}
</style>
