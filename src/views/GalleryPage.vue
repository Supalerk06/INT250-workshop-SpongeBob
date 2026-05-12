<template>
  <main class="pt-32 pb-20 px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto min-h-screen">
    <div class="animate-fade-in flex flex-col gap-12">
      <div class="flex flex-col gap-4">
        <span class="text-label-sm tracking-widest font-semibold uppercase text-outline">Portfolio</span>
        <h1 class="text-display text-primary">Gallery</h1>
        <p class="text-lg text-secondary max-w-2xl">
          A collection of our most significant works across various disciplines.
        </p>
      </div>
      
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="i in 6" :key="i" class="group cursor-pointer overflow-hidden border border-outline-variant/10">
          <div class="aspect-[3/4] bg-surface-container relative">
             <div class="absolute inset-0 flex items-center justify-center text-outline text-label-sm tracking-widest font-semibold uppercase">IMAGE {{ i }}</div>
             <img 
               :src="`https://picsum.photos/seed/${i + 10}/600/800`" 
               class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105"
               alt="Gallery Work"
             />
          </div>
          <div class="p-6 bg-surface">
            <h3 class="text-xl font-medium text-primary">Project Name {{ i }}</h3>
            <p class="text-label-sm tracking-widest font-semibold uppercase text-secondary mt-1">Category</p>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
