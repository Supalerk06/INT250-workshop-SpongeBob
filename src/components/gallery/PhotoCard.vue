
<script setup>
defineProps({
  imageSrc: String,
  altText: String,
  isSelected: {
    type: Boolean,
    default: false
  }
})
</script>

<template>
  <div class="group relative aspect-[4/5] bg-surface-container-high overflow-hidden border border-outline-variant/10">
    <img :src="imageSrc" :alt="altText" class="w-full h-full object-cover grayscale" />
    
    <div class="image-hover-overlay absolute inset-0 bg-primary/40 backdrop-blur-[2px] flex items-center justify-center gap-6 opacity-0 group-hover:opacity-100 transition-opacity duration-200 ease-in-out">
      <button class="w-12 h-12 bg-white flex items-center justify-center hover:bg-black hover:text-white transition-colors" title="Print Selection">
        <span class="material-symbols-outlined">print</span>
      </button>
      <button class="w-12 h-12 bg-white flex items-center justify-center hover:bg-black hover:text-white transition-colors" title="Digital Resolution">
        <span class="material-symbols-outlined">high_res</span>
      </button>
    </div>

    <div v-if="isSelected" class="absolute top-4 left-4">
      <span class="bg-white text-black px-3 py-1 font-label-sm text-[10px] tracking-widest">SELECTED</span>
    </div>
  </div>
</template>
