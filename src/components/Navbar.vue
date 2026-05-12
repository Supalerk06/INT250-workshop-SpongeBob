<script setup>
import { ref, onMounted } from 'vue'

const isDark = ref(false)

const toggleDarkMode = () => {
  isDark.value = !isDark.value
  if (isDark.value) {
    document.documentElement.classList.add('dark')
    localStorage.setItem('theme', 'dark')
  } else {
    document.documentElement.classList.remove('dark')
    localStorage.setItem('theme', 'light')
  }
}

onMounted(() => {
  const savedTheme = localStorage.getItem('theme')
  if (savedTheme === 'dark' || (!savedTheme && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
    isDark.value = true
    document.documentElement.classList.add('dark')
  }
})
</script>

<template>
  <header class="fixed top-0 w-full z-50 bg-surface border-b border-outline-variant">
    <nav class="flex justify-between items-center h-16 px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto">
      <router-link to="/" class="text-xl font-bold text-primary">
        Fotof
      </router-link>
      
      <div class="hidden md:flex gap-6 items-center">
        <router-link to="/" class="nav-link" active-class="nav-link-active">Home</router-link>
        <router-link to="/booking" class="nav-link" active-class="nav-link-active">Booking</router-link>
        <router-link to="/gallery" class="nav-link" active-class="nav-link-active">Gallery</router-link>
        <router-link to="/invoice" class="nav-link" active-class="nav-link-active">Invoice</router-link>
      </div>

      <div class="flex items-center gap-4">
        <button 
          @click="toggleDarkMode" 
          class="p-2 rounded hover:bg-surface-container"
          aria-label="Toggle dark mode"
        >
          <span v-if="isDark" class="material-symbols-outlined">light_mode</span>
          <span v-else class="material-symbols-outlined">dark_mode</span>
        </button>
        
        <router-link 
          to="/booking" 
          class="bg-primary text-on-primary px-4 py-2 text-label-sm font-bold"
        >
          BOOK NOW
        </router-link>
      </div>
    </nav>
  </header>
</template>

<style scoped>
@reference "../style.css";
.nav-link {
  @apply text-label-sm text-secondary hover:text-primary;
}

.nav-link-active {
  @apply text-primary font-bold;
}
</style>

