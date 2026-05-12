
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
  <div class="relative aspect-square bg-surface-container border border-outline">
    <img :src="imageSrc" :alt="altText" class="w-full h-full object-cover" />
    
    <div v-if="isSelected" class="absolute top-2 left-2">
      <span class="bg-primary text-on-primary px-2 py-1 text-[10px] font-bold">SELECTED</span>
    </div>
    
    <div class="p-2 flex gap-2">
      <button class="text-xs underline" title="Print">Print</button>
      <button class="text-xs underline" title="Download">Download</button>
    </div>
  </div>
</template>

