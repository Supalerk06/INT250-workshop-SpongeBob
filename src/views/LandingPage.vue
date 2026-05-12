<script setup>
import { ref } from 'vue'
</script>

<template>
  <main class="pt-16">
    <!-- Hero Section -->
    <section class="max-w-container-max mx-auto px-4 py-16 grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
      <div class="flex flex-col gap-6">
        <h1 class="text-4xl font-bold text-primary">
          The Art of Photography
        </h1>
        <p class="text-secondary">
          Capturing light, form, and space. We provide a minimalist lens to frame the world.
        </p>
        <div>
          <button class="bg-primary text-on-primary px-8 py-3 font-bold uppercase">
            Book a Session
          </button>
        </div>
      </div>
      <div class="aspect-[4/5] bg-surface-container border border-outline">
        <img 
          src="https://lh3.googleusercontent.com/aida-public/AB6AXuBCzRQVlmQT27kW8jaQVwndi_khenQxTYRmL5huhacXdUD_omxi8l30vRQlatmoy2Rhi3BKfAhyfWUQj8-Cka_ZfHc48-yoyRVYoEW_oqarZqPNewWJ6qME2KbOL_4MrOm8E0zlntn4SjIlgHH5ZF-os3JcfnwpxxDSo2f0Db5fCbPpRx9T168DZaoEppdBK8NBw8mKLjulRpDk4owzjGKCzF8IaYnIw9NFcgdXIR6LTixZ08ldzyca7FaaNT-k8dbKvOrNPfOieuw" 
          alt="Photography" 
          class="w-full h-full object-cover"
        />
      </div>
    </section>

    <!-- Gallery Section -->
    <section class="bg-surface-container py-16">
      <div class="max-w-container-max mx-auto px-4">
        <div class="flex justify-between items-end mb-8">
          <h2 class="text-2xl font-bold">Featured Works</h2>
          <router-link to="/gallery" class="text-primary font-bold underline">
            View All
          </router-link>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <!-- Item 1 -->
          <div class="flex flex-col gap-4">
            <div class="aspect-square bg-white border border-outline">
              <img src="https://lh3.googleusercontent.com/aida-public/AB6AXuCj36zg4wH7Lqyy2i3L5LWsfsnU6pribfK8QZQNgrGHtWsY6_x-h8sECZEnAUbjKWwYh1GDY5PqrZ2k1haa195qmY_xakt7R-MtxzZA1xYN422-k_mCvsbSN5JBO48e9Cg-Taeq6m3lIMpnSzItlQjhFQOFr3miyvvKx0oO6ooo9y9NJ2gPPnJU8bTKDQEEOGZLGXIfyGfIQQDIMaQrNQvc9xiRdv5_xT00PuLG1mdT-EXLAwU6VrejEHzZ2IHyYav_cxbpXq5SoL0" alt="Work" class="w-full h-full object-cover" />
            </div>
            <h3 class="text-lg font-bold">Noir Monolith</h3>
          </div>

          <!-- Item 2 -->
          <div class="flex flex-col gap-4">
            <div class="aspect-square bg-white border border-outline">
              <img src="https://lh3.googleusercontent.com/aida-public/AB6AXuAUWDG9Whci0ho1W2VN9gavNb-CSjG_ZPON0-Ues5BxqAkk-4VzGgXdTx1SJrjdGR4G0QWFG6pXx7gAJ1S7XHP5Z2pAsDYROEOAxugUeHa2TfUu9FeQo9Zo0vLGF6WtNhX5xYZFLEYTYnC6kETbFzg4y4jq9MZXvXtWFTtIrENC4kCw9kf9Wb-INm3iLT1BKysuWViSXypWcPg6HE2HFDjT_wZ19EJyW6QPfObvWOIatRTyWi6kRM-VjDDeh4exGLVPB7xr31varIw" alt="Work" class="w-full h-full object-cover" />
            </div>
            <h3 class="text-lg font-bold">Glass & Steel</h3>
          </div>

          <!-- Item 3 -->
          <div class="flex flex-col gap-4">
            <div class="aspect-square bg-white border border-outline">
              <img src="https://lh3.googleusercontent.com/aida-public/AB6AXuBRH2VvtPYmHtTcoKxMfFOtDBoX1Z6PoN6gpBprRL-EB_Ng4kuw9YPllAAjcmDigbG4Dw0imMM9oi8eMVZkzj3_3LdEUm3mi27inVefSdkahyTAz19vwPtvlaqC-auX5c4GheH0tgYQIHYkThm294NIHAjZjdLpO1dz6Jir0TCZQfOtEVtQzB-CgtR9VG_D93XGKbCe81qYAFw9tvj7Y1h-Ms8yvhCg1wOCC9kjZXXprPtTHwdGGCX3b7N2EGCu-suTWSxVncRytDg" alt="Work" class="w-full h-full object-cover" />
            </div>
            <h3 class="text-lg font-bold">The Silent Observer</h3>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="py-16 bg-surface text-center">
      <div class="max-w-container-max mx-auto px-4">
        <h2 class="text-3xl font-bold mb-4">Ready to start?</h2>
        <p class="text-secondary mb-8">Limited availability for the upcoming season.</p>
        <button class="bg-primary text-on-primary px-10 py-4 font-bold uppercase">
          Inquire Now
        </button>
      </div>
    </section>
  </main>
</template>

