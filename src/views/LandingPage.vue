<script setup>
import { onMounted, ref } from 'vue'

const observerOptions = {
  threshold: 0.1,
  rootMargin: '0px 0px -50px 0px'
}

const observedElements = ref([])

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('animate-slide-up')
        entry.target.style.opacity = '1'
        observer.unobserve(entry.target)
      }
    })
  }, observerOptions)

  observedElements.value.forEach(el => {
    if (el) observer.observe(el)
  })
})

const setObservedElement = (el) => {
  if (el) observedElements.value.push(el)
}
</script>

<template>
  <main class="pt-20 overflow-hidden">
    
    <section class="max-w-container-max mx-auto px-margin-mobile md:px-margin-desktop py-section-gap grid grid-cols-12 gap-gutter items-center">
      <div class="col-span-12 md:col-span-5 flex flex-col gap-8 order-2 md:order-1 animate-fade-in">
        <h1 class="text-display text-primary tracking-tight">
          The Art of <br/>
          <span class="font-bold">Silent Architecture</span>
        </h1>
        <p class="text-lg text-secondary max-w-md">
          Capturing the interplay of light, form, and space. We provide a minimalist lens to frame the world's most sophisticated designs and moments.
        </p>
        <div>
          <button class="bg-primary text-on-primary px-10 py-5 text-label-sm tracking-widest font-semibold uppercase hover:opacity-90 active:scale-95 transition-all shadow-lg shadow-primary/10">
            Book a Session
          </button>
        </div>
      </div>
      <div class="col-span-12 md:col-span-7 order-1 md:order-2 animate-fade-in" style="animation-delay: 0.2s">
        <div class="relative w-full aspect-[4/5] bg-surface-container overflow-hidden border border-outline-variant/10 group">
          <img 
            src="https://lh3.googleusercontent.com/aida-public/AB6AXuBCzRQVlmQT27kW8jaQVwndi_khenQxTYRmL5huhacXdUD_omxi8l30vRQlatmoy2Rhi3BKfAhyfWUQj8-Cka_ZfHc48-yoyRVYoEW_oqarZqPNewWJ6qME2KbOL_4MrOm8E0zlntn4SjIlgHH5ZF-os3JcfnwpxxDSo2f0Db5fCbPpRx9T168DZaoEppdBK8NBw8mKLjulRpDk4owzjGKCzF8IaYnIw9NFcgdXIR6LTixZ08ldzyca7FaaNT-k8dbKvOrNPfOieuw" 
            alt="Professional Photography" 
            class="w-full h-full object-cover transition-transform duration-1000 group-hover:scale-105"
          />
          <div class="absolute inset-0 bg-primary/5 opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
        </div>
      </div>
    </section>

    
    <section class="bg-surface-container-low py-section-gap transition-colors duration-300">
      <div class="max-w-container-max mx-auto px-margin-mobile md:px-margin-desktop">
        <div :ref="setObservedElement" class="opacity-0 flex flex-col md:flex-row justify-between items-end mb-16 gap-8">
          <div class="flex flex-col gap-2">
            <span class="text-label-sm tracking-widest font-semibold uppercase text-outline">Curation</span>
            <h2 class="text-headline-lg text-primary">Featured Works</h2>
          </div>
          <router-link to="/gallery" class="text-label-sm tracking-widest font-semibold uppercase text-primary border-b border-primary pb-1 hover:opacity-70 transition-opacity">
            VIEW ALL PROJECTS
          </router-link>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-gutter">
          
          <div :ref="setObservedElement" class="opacity-0 flex flex-col gap-6 group cursor-pointer">
            <div class="aspect-square bg-surface-container overflow-hidden border border-outline-variant/10 relative">
              <img src="https://lh3.googleusercontent.com/aida-public/AB6AXuCj36zg4wH7Lqyy2i3L5LWsfsnU6pribfK8QZQNgrGHtWsY6_x-h8sECZEnAUbjKWwYh1GDY5PqrZ2k1haa195qmY_xakt7R-MtxzZA1xYN422-k_mCvsbSN5JBO48e9Cg-Taeq6m3lIMpnSzItlQjhFQOFr3miyvvKx0oO6ooo9y9NJ2gPPnJU8bTKDQEEOGZLGXIfyGfIQQDIMaQrNQvc9xiRdv5_xT00PuLG1mdT-EXLAwU6VrejEHzZ2IHyYav_cxbpXq5SoL0" alt="Editorial Shot" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110" />
              <div class="absolute inset-0 bg-black/20 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                <span class="text-white text-label-sm tracking-widest font-semibold uppercase border border-white/50 px-4 py-2">VIEW DETAILS</span>
              </div>
            </div>
            <div class="flex flex-col gap-1">
              <span class="text-label-sm tracking-widest font-semibold uppercase text-outline">Editorial</span>
              <h3 class="text-xl font-medium text-primary">Noir Monolith</h3>
            </div>
          </div>

          
          <div :ref="setObservedElement" class="opacity-0 flex flex-col gap-6 group cursor-pointer md:mt-12">
            <div class="aspect-square bg-surface-container overflow-hidden border border-outline-variant/10 relative">
              <img src="https://lh3.googleusercontent.com/aida-public/AB6AXuAUWDG9Whci0ho1W2VN9gavNb-CSjG_ZPON0-Ues5BxqAkk-4VzGgXdTx1SJrjdGR4G0QWFG6pXx7gAJ1S7XHP5Z2pAsDYROEOAxugUeHa2TfUu9FeQo9Zo0vLGF6WtNhX5xYZFLEYTYnC6kETbFzg4y4jq9MZXvXtWFTtIrENC4kCw9kf9Wb-INm3iLT1BKysuWViSXypWcPg6HE2HFDjT_wZ19EJyW6QPfObvWOIatRTyWi6kRM-VjDDeh4exGLVPB7xr31varIw" alt="Architectural Shot" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110" />
              <div class="absolute inset-0 bg-black/20 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                <span class="text-white text-label-sm tracking-widest font-semibold uppercase border border-white/50 px-4 py-2">VIEW DETAILS</span>
              </div>
            </div>
            <div class="flex flex-col gap-1">
              <span class="text-label-sm tracking-widest font-semibold uppercase text-outline">Spaces</span>
              <h3 class="text-xl font-medium text-primary">Glass & Steel</h3>
            </div>
          </div>

          
          <div :ref="setObservedElement" class="opacity-0 flex flex-col gap-6 group cursor-pointer">
            <div class="aspect-square bg-surface-container overflow-hidden border border-outline-variant/10 relative">
              <img src="https://lh3.googleusercontent.com/aida-public/AB6AXuBRH2VvtPYmHtTcoKxMfFOtDBoX1Z6PoN6gpBprRL-EB_Ng4kuw9YPllAAjcmDigbG4Dw0imMM9oi8eMVZkzj3_3LdEUm3mi27inVefSdkahyTAz19vwPtvlaqC-auX5c4GheH0tgYQIHYkThm294NIHAjZjdLpO1dz6Jir0TCZQfOtEVtQzB-CgtR9VG_D93XGKbCe81qYAFw9tvj7Y1h-Ms8yvhCg1wOCC9kjZXXprPtTHwdGGCX3b7N2EGCu-suTWSxVncRytDg" alt="Portrait Shot" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110" />
              <div class="absolute inset-0 bg-black/20 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                <span class="text-white text-label-sm tracking-widest font-semibold uppercase border border-white/50 px-4 py-2">VIEW DETAILS</span>
              </div>
            </div>
            <div class="flex flex-col gap-1">
              <span class="text-label-sm tracking-widest font-semibold uppercase text-outline">Portraits</span>
              <h3 class="text-xl font-medium text-primary">The Silent Observer</h3>
            </div>
          </div>
        </div>
      </div>
    </section>

    
    <section :ref="setObservedElement" class="opacity-0 py-section-gap bg-surface transition-colors duration-300">
      <div class="max-w-container-max mx-auto px-margin-mobile md:px-margin-desktop text-center flex flex-col items-center gap-8">
        <h2 class="text-display text-primary max-w-3xl">Let us frame your vision with precision and elegance.</h2>
        <p class="text-md text-secondary max-w-xl">Our studio is currently accepting bookings for commercial and private sessions. Limited availability for the upcoming season.</p>
        <div class="pt-8">
          <button class="bg-primary text-on-primary px-12 py-6 text-label-sm tracking-widest font-semibold uppercase hover:bg-secondary transition-colors shadow-xl shadow-primary/5">
            INQUIRE NOW
          </button>
        </div>
      </div>
    </section>
  </main>
</template>