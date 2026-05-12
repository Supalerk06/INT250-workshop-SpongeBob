<template>
  <footer class="w-full py-section-gap bg-surface dark:bg-surface-container border-t border-outline-variant/20 transition-colors duration-300">
    <div class="flex flex-col md:flex-row justify-between items-start px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto gap-gutter">
      <div class="flex flex-col gap-4">
        <div class="text-headline-md font-bold text-primary">
          Fotof
        </div>
        <p class="text-secondary text-body-md max-w-xs">
          Professional photography studio specializing in minimalist architectural and editorial work.
        </p>
      </div>
      
      <div class="flex flex-col md:flex-row gap-gutter md:gap-16 mt-8 md:mt-0">
        <div class="flex flex-col gap-4">
          <span class="text-label-sm text-primary font-bold">Navigation</span>
          <ul class="flex flex-col gap-2">
            <li><router-link to="/" class="footer-link">Home</router-link></li>
            <li><router-link to="/gallery" class="footer-link">Gallery</router-link></li>
            <li><router-link to="/booking" class="footer-link">About</router-link></li>
          </ul>
        </div>
        <div class="flex flex-col gap-4">
          <span class="text-label-sm text-primary font-bold">Legal</span>
          <ul class="flex flex-col gap-2">
            <li><a href="#" class="footer-link">Privacy Policy</a></li>
            <li><a href="#" class="footer-link">Terms of Service</a></li>
            <li><a href="#" class="footer-link">Contact</a></li>
          </ul>
        </div>
      </div>
      
      <div class="w-full md:w-auto mt-12 md:mt-0 border-t md:border-t-0 border-outline-variant/10 pt-8 md:pt-0">
        <p class="text-label-sm text-secondary">
          © 2024 FOTOF STUDIO. ALL RIGHTS RESERVED.
        </p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
@reference "../style.css";
.footer-link {
  @apply text-body-md text-secondary hover:text-primary underline underline-offset-4 decoration-outline-variant/30 hover:decoration-primary transition-all;
}
</style>
