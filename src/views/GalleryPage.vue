
<script setup>

import AlertBanner from '../components/gallery/AlertBanner.vue'
import PhotoCard from '../components/gallery/PhotoCard.vue'
import RequestSidebar from '../components/gallery/RequestSidebar.vue'

const photos = [
  { src: 'https://lh3.googleusercontent.com/aida-public/AB6AXuBM2DAE-nrzTTLniTmWwePVXHAAGw_fe9c0gPF-fFYhy5SIyBPHYMNB3Pr2spn5sTNjapUimM8PrECq264uIOut17Cr53VHQme4d50l98rokQoxBEVGHPkGn28w745urCUWigIgzc7ShtkwhW5h_WC_XyJitLesy7H2QLpzKMlwuJHHWCGxnMucGPUWV_ZhtS9B1TuJK5dYeIoK94lnDOoh--W6yC2GmddMGIL8fru9O6w_zMwce-wIi0eyXYRQcisIUeYN-l7udy0', alt: 'Portrait 1', selected: true },
  { src: 'https://lh3.googleusercontent.com/aida-public/AB6AXuDFL2esYvkv_WhvOCJyJBZ8vavWGE8HHwP0TPTlokGcBp9JhyJmDeootI1ldx7XTpdRX5QbUTzwNX0tALUb7AR1KVNldUfPIADq8r0muFsWkKQJIrHupDuKjfxCpGum73W9Z4e2ofk-86_AeJZs7xxrY2IgQd-uJMXOo_iWGrS0vWPw2wMp9w_jMopquTUoUrNcq47Pu2vYN62SL5-jy1yiDr3t2ucT59L_1D_Y73f1kPcAa1upeCGxvfKjNCY0C_aKKWKsI9n2uVM', alt: 'Portrait 2', selected: false },
  { src: 'https://lh3.googleusercontent.com/aida-public/AB6AXuCrc1U32VfwWq6vipRxYQ5wR7mwu5r19cAqc2D2sx_2AIuQwZKGJrcY7C-8uXr_IP2aXJaE4KII_im_xVgD6ss8TDxhOe6bdHKFhcJN-rx3lTkqGl0JDz6kwyBetNf0bGXobfC8XdviaW0PstSkJvtPeR2tujaWai7jEfdlCagfT8tERIA2SqpioyUS9BvAOIh54kR4nJBLy1428SsXRBRjxd0MbuQl-dcwrJsgHgpZ4XEtoc6wcbD3RGlpp9X8QXFAmj0NPfEzBfU', alt: 'Portrait 3', selected: false },
  { src: 'https://lh3.googleusercontent.com/aida-public/AB6AXuADzWF-ntR73eM8Tzay_FbEDRyxK82nXQSWXyAG5DjJl3_enmLwKd3jwttcLoMjvf01tEMlk8Qxb6SFa6upy2O5hFfoDp22EvJoBvj7zVWyc9Prr-rw7AjTWZIC7v5rdQs6IKjj2fWmvO6X2vEfwSQ5FWn3tuq5_m2ksNYlkK4O8WGQxaAoL_aWsjCpUC9vw40T_pmQKQekJFas8oSrpigfWVrRH5tDFEpxTzHmOr-vYMuXKqJFUOQjFflpoR2IUOHmpxuS5JcIjxU', alt: 'Portrait 4', selected: false },
  { src: 'https://lh3.googleusercontent.com/aida-public/AB6AXuDgwox7BVWCN2FcId_JXEqpPP1AvK9eNHytmtkJgsO-E2DLEwOS54Kfn4AXTx1JxFVaPVjwR2zUH6rwSoFEDMB36T2H8fBLk4CXxdO4bWvWHQERovJmZ1vDWs1sGVvankWjdlms0-eZJXH-0hazwuYR99t18r-dP3IT0mKWwxqH1nXatGSi0xQa0zfuqRzhBfiXGAfqcMaYfRdvepbMVXEhsA0bcTjyiXo28Xcpw9vrpuqVqQUfgutI7NDKDmkW-V00FGA49TG69w8', alt: 'Portrait 5', selected: false },
  { src: 'https://lh3.googleusercontent.com/aida-public/AB6AXuDvVjzbn8S7c0u-YRrtEfyPy_nnkHZY4fbSN5CdrRxtI4gaoDvCS-3bawmKHUhdBvhGhtSVXnIbb_C7oXe-ZdcttmIqafUCb7xbmCuLsZ62zjztMI1-gXdRot8q0m4UxViph8MciNleygHafLNuVfb5noPmNnnL6BOw9Csk9UfuDcxK7FY-6WoJx1mh59Gpt766FnGVxAmYLmlwodDr9DHhXJFjQv3bZJpUOPDSpI4Fe6fXqRPYoIKD4tatNhURijyWWxNgcYhYmmo', alt: 'Portrait 6', selected: false }
]
</script>

<template>
  <div class="bg-background text-on-background font-body-md">
    
    <AlertBanner message="Gallery expires in 30 days" />

    <main class="max-w-container-max mx-auto px-margin-desktop py-16">
      <header class="mb-16 flex flex-col md:flex-row md:items-end justify-between gap-8">
        <div class="max-w-2xl">
          <h1 class="font-display text-[48px] font-light leading-tight mb-4">Portrait Session: The Glass House</h1>
          <p class="font-body-lg text-lg text-secondary">Curated selection from your architectural editorial session. Select your preferred high-resolution digital files or request specific print finishes.</p>
        </div>
        <div class="flex items-center gap-4">
          <button class="flex items-center gap-2 font-label-sm text-sm text-primary border border-primary/10 px-4 py-2 hover:bg-surface-container transition-colors">
            <span class="material-symbols-outlined text-[20px]">download</span> DOWNLOAD ALL
          </button>
        </div>
      </header>

      <div class="flex flex-col lg:flex-row gap-16">
        <div class="flex-grow">
          <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8">
            <PhotoCard 
              v-for="(photo, index) in photos" 
              :key="index"
              :imageSrc="photo.src" 
              :altText="photo.alt"
              :isSelected="photo.selected"
            />
          </div>
        </div>

        <RequestSidebar />
      </div>
    </main>

</div>
</template>
