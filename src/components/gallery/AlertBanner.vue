<script setup>
defineProps({
  message: {
    type: String,
    default: 'Gallery expires in 30 days'
  }
})
</script>

<template>
  <div class="mt-16 bg-surface-container border-b border-outline py-2">
    <div class="max-w-container-max mx-auto px-margin-desktop flex items-center justify-center gap-2">
      <span class="text-sm font-bold">{{ message }}</span>
    </div>
  </div>
</template>


