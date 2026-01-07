<template>
  <section class="reveal-section bg-white py-12">
    <div class="mx-auto w-full max-w-[1000px] px-6">
      <div class="text-center">
        <h2 class="text-[22px] font-semibold uppercase tracking-[0.2em] text-black/80">
          Shop The
          <span class="inline-block border-b-2 border-[var(--color-primary)] pb-1 text-[var(--color-secondary)]">
            Pulse
          </span>
        </h2>
      </div>

      <div class="mt-10 grid items-start gap-8 md:grid-cols-2">
        <article class="text-left">
          <div class="rounded-2xl bg-transparent p-0">
            <div class="overflow-hidden rounded-xl">
              <img class="h-[260px] w-full rounded-xl object-cover transition-transform duration-200 hover:scale-105" src="/shop_the_pulse/1.png" alt="PRANA LED Light Therapy Mask">
            </div>
          </div>
          <h3 class="mt-4 text-[12px] font-semibold text-black/70">PRANA LED Light Therapy Mask</h3>
          <div class="mt-1 flex items-center gap-2 text-[11px] text-black/60">
            <div class="flex items-center text-[var(--color-primary)]">
              &#9733;&#9733;&#9733;&#9733;&#9734;
            </div>
            <span>261 Reviews</span>
          </div>
          <div class="mt-3 text-[13px] font-semibold text-black/80">From &euro;345,00 EUR</div>
          <button
            class="mt-4 w-full max-w-[220px] rounded-full border border-black/40 px-5 py-2 text-[10px] font-montserrat uppercase tracking-[0.14em] text-black/70"
            type="button"
          >
            Choose Options
          </button>
        </article>

        <article class="text-left">
          <div class="rounded-2xl bg-transparent p-0">
            <div class="overflow-hidden rounded-xl">
              <img class="h-[260px] w-full rounded-xl object-cover transition-transform duration-200 hover:scale-105" src="/shop_the_pulse/2.png" alt="Green Rooibos Pressed Serum">
            </div>
          </div>
          <h3 class="mt-4 text-[12px] font-semibold text-black/70">Green Rooibos Pressed Serum</h3>
          <div class="mt-1 flex items-center gap-2 text-[11px] text-black/60">
            <div class="flex items-center text-[var(--color-primary)]">
              &#9733;&#9733;&#9733;&#9733;&#9733;
            </div>
            <span>972 Reviews</span>
          </div>
          <div class="mt-3 text-[13px] font-semibold text-black/80">&euro;55,95 EUR</div>
          <button
            class="mt-4 w-full max-w-[220px] rounded-full border border-black/40 px-5 py-2 text-[10px] font-montserrat uppercase tracking-[0.14em] text-black/70"
            type="button"
          >
            Add To Cart
          </button>
        </article>
      </div>
    </div>
  </section>
</template>
