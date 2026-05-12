<template>
  <footer class="w-full py-16 bg-surface-container border-t border-outline">
    <div class="flex flex-col md:flex-row justify-between items-start px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto gap-8">
      <div class="flex flex-col gap-4">
        <div class="text-xl font-bold text-primary">
          Fotof
        </div>
        <p class="text-secondary text-sm max-w-xs">
          Professional photography studio. Minimalist architectural and editorial work.
        </p>
      </div>
      
      <div class="flex flex-col md:flex-row gap-16 mt-8 md:mt-0">
        <div class="flex flex-col gap-4">
          <span class="text-sm font-bold text-primary">Navigation</span>
          <ul class="flex flex-col gap-2">
            <li><router-link to="/" class="footer-link">Home</router-link></li>
            <li><router-link to="/gallery" class="footer-link">Gallery</router-link></li>
            <li><router-link to="/booking" class="footer-link">Booking</router-link></li>
          </ul>
        </div>
        <div class="flex flex-col gap-4">
          <span class="text-sm font-bold text-primary">Legal</span>
          <ul class="flex flex-col gap-2">
            <li><a href="#" class="footer-link">Privacy Policy</a></li>
            <li><a href="#" class="footer-link">Terms</a></li>
            <li><a href="#" class="footer-link">Contact</a></li>
          </ul>
        </div>
      </div>
      
      <div class="w-full md:w-auto mt-12 md:mt-0 border-t md:border-t-0 border-outline pt-8 md:pt-0">
        <p class="text-xs text-secondary">
          © 2024 FOTOF STUDIO.
        </p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
@reference "../style.css";
.footer-link {
  @apply text-sm text-secondary hover:text-primary underline;
}
</style>

