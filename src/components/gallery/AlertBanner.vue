<script setup>
defineProps({
  message: {
    type: String,
    default: 'Gallery expires in 30 days'
  }
})
</script>

<template>
  <div class="mt-20 bg-surface-container-lowest border-b border-outline-variant/20 py-3">
    <div class="max-w-container-max mx-auto px-margin-desktop flex items-center justify-center gap-2">
      <span class="material-symbols-outlined text-[18px] text-error">alarm</span>
      <span class="font-label-sm text-label-sm text-on-surface uppercase tracking-[0.2em]">{{ message }}</span>
    </div>
  </div>
</template>

