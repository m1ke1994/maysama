<template>
  <section class="bg-white py-12">
    <div class="mx-auto w-full max-w-[1200px] px-6">
      <div class="grid items-center gap-8 md:grid-cols-2">
        <div class="rounded-2xl bg-[#f1e6df] p-8 shadow-[0_2px_10px_rgba(0,0,0,0.08)]">
          <h3 class="text-[22px] font-semibold text-black/80">Double Whammy!</h3>
          <p class="mt-3 text-[12px] leading-relaxed text-black/60">
            It's official! Pre-treating your skin with Maysama Green Rooibos
            Pressed Serum prior to your Red LED Light Therapy Treatment session,
            <span class="text-[var(--color-primary)] underline underline-offset-4">more than doubles</span>
            outcomes for skin rejuvenation.
          </p>
          <button
            class="btn-primary mt-6 rounded-full px-6 py-2 text-[10px] font-montserrat uppercase tracking-[0.14em]"
            type="button"
          >
            Read More
          </button>
        </div>

        <div class="relative">
          <img class="w-full rounded-2xl" src="/banner/banner.png" alt="Up to 260% improved results">
          <div class="absolute inset-0 flex flex-col justify-center px-6 text-black/80 sm:px-10">
            <div class="text-[11px] font-semibold uppercase tracking-[0.14em] sm:text-[14px]">Up to</div>
            <div class="text-[34px] font-bold leading-none text-black/90 sm:text-[48px]">260%</div>
            <div class="text-[13px] font-semibold uppercase tracking-[0.12em] sm:text-[18px]">Improved Results*</div>
            <ul class="mt-3 space-y-1 text-[12px] font-semibold sm:mt-4 sm:space-y-2 sm:text-[14px]">
              <li><span class="text-[var(--color-primary)]">+55%</span> Elasticity</li>
              <li><span class="text-[var(--color-primary)]">-30%</span> Wrinkles</li>
              <li><span class="text-[var(--color-primary)]">-30%</span> Erythema</li>
              <li><span class="text-[var(--color-primary)]">-23%</span> Pigmentation</li>
            </ul>
            <p class="mt-3 text-[9px] text-black/60 sm:mt-4 sm:text-[10px]">*Independently tested. Click below to find out more</p>
            <button
              class="btn-primary mt-4 w-fit rounded-full px-6 py-2 text-[10px] font-montserrat uppercase tracking-[0.14em]"
              type="button"
            >
              Learn More
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
