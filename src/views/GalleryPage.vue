
<script setup>

import AlertBanner from '../components/gallery/AlertBanner.vue'
import PhotoCard from '../components/gallery/PhotoCard.vue'
import RequestSidebar from '../components/gallery/RequestSidebar.vue'

const photos = [
  { src: 'https://img.freepik.com/free-photo/lavender-field-sunset-near-valensole_268835-3910.jpg?semt=ais_hybrid&w=740&q=80', alt: 'Portrait 1', selected: true },
  { src: 'https://img.freepik.com/free-photo/lavender-field-sunset-near-valensole_268835-3910.jpg?semt=ais_hybrid&w=740&q=80', alt: 'Portrait 2', selected: false },
  { src: 'https://img.freepik.com/free-photo/lavender-field-sunset-near-valensole_268835-3910.jpg?semt=ais_hybrid&w=740&q=80', alt: 'Portrait 3', selected: false },
  { src: 'https://img.freepik.com/free-photo/lavender-field-sunset-near-valensole_268835-3910.jpg?semt=ais_hybrid&w=740&q=80', alt: 'Portrait 4', selected: false },
  { src: 'https://img.freepik.com/free-photo/lavender-field-sunset-near-valensole_268835-3910.jpg?semt=ais_hybrid&w=740&q=80', alt: 'Portrait 5', selected: false },
  { src: 'https://img.freepik.com/free-photo/lavender-field-sunset-near-valensole_268835-3910.jpg?semt=ais_hybrid&w=740&q=80', alt: 'Portrait 6', selected: false }
]
</script>

<template>
  <main class="max-w-4xl mx-auto px-4 py-24">
    <header class="mb-12 flex justify-between items-end">
      <div>
        <h1 class="text-3xl font-bold mb-2">Gallery: The Glass House</h1>
        <p class="text-secondary">Select files or request adjustments.</p>
      </div>
      <button class="bg-surface-container border border-outline px-4 py-2 font-bold">
        Download All
      </button>
    </header>

    <div class="grid grid-cols-2 md:grid-cols-3 gap-6">
      <PhotoCard 
        v-for="(photo, index) in photos" 
        :key="index"
        :imageSrc="photo.src" 
        :altText="photo.alt"
        :isSelected="photo.selected"
      />
    </div>
  </main>
</template>


