<script setup>
import Navbar from './components/Navbar.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div class="min-h-screen flex flex-col font-sans">
    <Navbar />
    
    <router-view />
    
    <Footer />
  </div>
</template>

<style>
/* Simplified styles */
</style>