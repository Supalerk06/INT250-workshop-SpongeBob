<script setup>
import { ref } from 'vue'



const img = [
  {
link: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR3MuoNaiuiToPX8p_73R6goqoS0mSnrXNjdA&s"
},
  {
link: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR3MuoNaiuiToPX8p_73R6goqoS0mSnrXNjdA&s"
},
  {
link: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR3MuoNaiuiToPX8p_73R6goqoS0mSnrXNjdA&s"
} 
]
</script>

<template>
  <main class="pt-24 pb-16">
    <!-- Hero -->
    <section class="max-w-4xl mx-auto px-4 mb-24 flex flex-col md:flex-row items-center gap-12">
      <div class="flex-1">
        <h1 class="text-5xl font-bold mb-6">Capture the Moment</h1>
        <p class="text-lg text-secondary mb-8">Professional photography studio focusing on minimalist architectural and editorial work.</p>
        <button class="bg-primary text-on-primary px-6 py-3 font-bold">
          Book a Session
        </button>
      </div>
      <div class="flex-1 aspect-[4/5] border border-outline bg-surface-container">
        <img src="https://lh3.googleusercontent.com/aida-public/AB6AXuBCzRQVlmQT27kW8jaQVwndi_khenQxTYRmL5huhacXdUD_omxi8l30vRQlatmoy2Rhi3BKfAhyfWUQj8-Cka_ZfHc48-yoyRVYoEW_oqarZqPNewWJ6qME2KbOL_4MrOm8E0zlntn4SjIlgHH5ZF-os3JcfnwpxxDSo2f0Db5fCbPpRx9T168DZaoEppdBK8NBw8mKLjulRpDk4owzjGKCzF8IaYnIw9NFcgdXIR6LTixZ08ldzyca7FaaNT-k8dbKvOrNPfOieuw" alt="Hero" class="w-full h-full object-cover" />
      </div>
    </section>

    <!-- Gallery -->
    <section class="max-w-4xl mx-auto px-4 mb-24">
      <div class="flex justify-between items-center mb-8">
        <h2 class="text-2xl font-bold">Featured Works</h2>
        <router-link to="/gallery" class="underline font-bold">View Gallery</router-link>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div v-for="i in img" class="border border-outline p-2 bg-surface-container">
          <div class="aspect-square bg-white mb-2 overflow-hidden">
             <img :src="i.link" alt="work" class="w-full h-full object-cover" />
          </div>
          <p class="font-bold">mock</p>
        </div>
      </div>
    </section>
  </main>
</template>


