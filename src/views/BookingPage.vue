<script setup>
import { ref } from 'vue'

const formData = ref({
  fullName: '',
  email: '',
  service: 'commercial',
  location: 'in-studio',
  date: '',
  message: ''
})

const submitForm = () => {
  console.log('Form Submitted:', formData.value)
  alert('Booking request sent!')
}
</script>

<template>
  <main class="pt-32 pb-section-gap">
    <section class="px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto mb-16">
      <div class="md:w-2/3">
        <p class="font-label-sm text-label-sm text-secondary mb-4 tracking-[0.2em]">RESERVE YOUR SESSION</p>
        <h1 class="font-display text-display mb-8">Capturing the <br/>essence of the moment.</h1>
        <div class="w-24 h-px bg-primary mb-8"></div>
      </div>
    </section>
    <section class="px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto grid grid-cols-1 lg:grid-cols-12 gap-gutter">
      <div class="lg:col-span-7 bg-surface-container-lowest p-8 md:p-12 border border-outline-variant/20 shadow-sm">
        <form @submit.prevent="submitForm" class="space-y-12">

          <div class="grid grid-cols-1 md:grid-cols-2 gap-x-gutter gap-y-10">
            <div class="relative group">
              <label class="block font-label-sm text-label-sm text-secondary mb-1">FULL NAME</label>
              <input v-model="formData.fullName" required class="w-full bg-transparent border-t-0 border-l-0 border-r-0 border-b border-outline-variant focus:border-primary focus:ring-0 py-2 px-0 transition-colors duration-300 placeholder:text-surface-dim" placeholder="Jane Doe" type="text"/>
            </div>
            <div class="relative group">
              <label class="block font-label-sm text-label-sm text-secondary mb-1">EMAIL ADDRESS</label>
              <input v-model="formData.email" required class="w-full bg-transparent border-t-0 border-l-0 border-r-0 border-b border-outline-variant focus:border-primary focus:ring-0 py-2 px-0 transition-colors duration-300 placeholder:text-surface-dim" placeholder="hello@example.com" type="email"/>
            </div>
          </div>
          <div>
            <label class="block font-label-sm text-label-sm text-secondary mb-4">SERVICE CATEGORY</label>
            <select v-model="formData.service" class="w-full bg-transparent border-t-0 border-l-0 border-r-0 border-b border-outline-variant focus:border-primary focus:ring-0 py-2 px-0 transition-colors duration-300 appearance-none font-body-md text-body-md">
              <option value="commercial">Commercial & Editorial</option>
              <option value="family">Family & Portrait</option>
              <option value="event">Personal Event</option>
              <option value="studio">Fine Art Studio</option>
            </select>
          </div>
          <div>
            <label class="block font-label-sm text-label-sm text-secondary mb-6">PREFFERED LOCATION</label>
            <div class="flex gap-8">
              <label class="flex items-center cursor-pointer group">
                <input v-model="formData.location" class="hidden peer" name="location" type="radio" value="in-studio"/>
                <span class="w-5 h-5 border border-primary flex items-center justify-center mr-3 peer-checked:bg-primary transition-all">
                  <span class="material-symbols-outlined text-[14px] text-white peer-checked:block hidden">check</span>
                </span>
                <span class="font-body-md text-body-md group-hover:text-primary transition-colors">In-Studio</span>
              </label>
              <label class="flex items-center cursor-pointer group">
                <input v-model="formData.location" class="hidden peer" name="location" type="radio" value="on-location"/>
                <span class="w-5 h-5 border border-primary flex items-center justify-center mr-3 peer-checked:bg-primary transition-all">
                  <span class="material-symbols-outlined text-[14px] text-white peer-checked:block hidden">check</span>
                </span>
                <span class="font-body-md text-body-md group-hover:text-primary transition-colors">On-Location</span>
              </label>
            </div>
          </div>
          <div class="space-y-10">
            <div class="relative group">
              <label class="block font-label-sm text-label-sm text-secondary mb-1">PROPOSED DATE</label>
              <input v-model="formData.date" required class="w-full bg-transparent border-t-0 border-l-0 border-r-0 border-b border-outline-variant focus:border-primary focus:ring-0 py-2 px-0 transition-colors duration-300" type="date"/>
            </div>
            <div class="relative group">
              <label class="block font-label-sm text-label-sm text-secondary mb-1">TELL US ABOUT YOUR VISION</label>
              <textarea v-model="formData.message" class="w-full bg-transparent border-t-0 border-l-0 border-r-0 border-b border-outline-variant focus:border-primary focus:ring-0 py-2 px-0 transition-colors duration-300 placeholder:text-surface-dim resize-none font-body-md text-body-md" placeholder="Brief description of the mood, concept, or specific requirements..." rows="4"></textarea>
            </div>
          </div>
          <div class="pt-6">
            <button class="w-full md:w-auto bg-primary text-on-primary px-12 py-5 font-label-sm text-label-sm tracking-[0.2em] hover:opacity-90 transition-opacity" type="submit">
              CONFIRM REQUEST
            </button>
            <p class="mt-4 font-label-sm text-[10px] text-on-surface-variant uppercase tracking-wider">A studio representative will respond within 24 hours.</p>
          </div>
        </form>
      </div>
      <div class="lg:col-span-5 flex flex-col gap-gutter">
        <div class="aspect-[4/5] bg-surface-container overflow-hidden group">
          <img class="w-full h-full object-cover grayscale hover:grayscale-0 transition-all duration-700 scale-105 group-hover:scale-100" alt="Professional studio" src="https://lh3.googleusercontent.com/aida-public/AB6AXuDfAAVAjlYP8_aZw-EUo4WpREWIhE3SkAgCB51Ua110Hss12-KBUuTYLevEyebCj7hI_dbLNHsBWMnEGLGgqE_4Xbg4vEg0v0mh66xw_J2r7_hIg9BnCdZ5vZ3BCxX3izTZ2JXABPsL-eZUS3A40q-lBnUklkkssGw4iEGfoPNJGHkJNEKlAneTYeFAsUhEHo24PXEPuOvpO1_onPSZUgfcclyczJ0H_fPvYt5TdT2gKUt8loOMEfMkXYaVNowD-W2-m20AHdWLkbc"/>
        </div>
        
        <div class="bg-surface-container-low p-8 border border-outline-variant/10">
          <h3 class="font-headline-md text-headline-md mb-6">Session Inclusions</h3>
          <ul class="space-y-4">
            <li class="flex items-start gap-3">
              <span class="material-symbols-outlined text-primary text-[18px]">photo_camera</span>
              <span class="font-body-md text-body-md text-secondary">High-resolution digital negatives with full printing rights.</span>
            </li>
            <li class="flex items-start gap-3">
              <span class="material-symbols-outlined text-primary text-[18px]">brush</span>
              <span class="font-body-md text-body-md text-secondary">Professional retouching and artistic color grading on selected images.</span>
            </li>
            <li class="flex items-start gap-3">
              <span class="material-symbols-outlined text-primary text-[18px]">cloud_done</span>
              <span class="font-body-md text-body-md text-secondary">Private online gallery for image selection and archiving.</span>
            </li>
          </ul>
        </div>
        
        <div class="relative aspect-video bg-surface overflow-hidden group">
          <img class="w-full h-full object-cover transition-all duration-700 group-hover:scale-110" alt="Vintage camera" src="https://lh3.googleusercontent.com/aida-public/AB6AXuDADgYvj74Pwgsaucz-XjsyE6k3nWXGALel7WxhgRmiiuGT0OweFJX78NTl7ENyuF_ta7XQ_2gq5bE_mLTiQdxpLzayvc8n9CYq0I1q5PDVGoNn_GwQSZR0MgcWWwi_1xMgIJAWEkI_J82qYtJOdZS2-XhlmgHmXAH7UGf9F78QHpw8AaXl1b5HlxF7quGaOtomOxtW4IWUNISjESBUBIJej4ycTj-yJPu30WylzcgYdIUdEqfL0_U_OUbZkp78TI-oRhYbWFRgSF4"/>
          <div class="absolute inset-0 bg-primary/10 group-hover:bg-transparent transition-colors duration-500"></div>
        </div>
      </div>
    </section>
    <section class="mt-section-gap px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto">
      <h2 class="font-headline-lg text-headline-lg mb-12">Recent Projects</h2>
      <div class="grid grid-cols-2 md:grid-cols-4 gap-4 h-[600px]">
        <div class="col-span-2 row-span-2 overflow-hidden bg-surface-container">
          <img class="w-full h-full object-cover grayscale hover:grayscale-0 transition-all duration-500 cursor-pointer" alt="Fashion portrait" src="https://lh3.googleusercontent.com/aida-public/AB6AXuCPl-VXV6aHiBLfSBUS_wr5hYpH6H1ITBSA_cQMYznUZ-Ru9Oy753c3jxikAxfgdrxVqFchHMa-qJmJGh5RXhuZl8sz-iHig9RqfRcusokYbJg3vk_X2sP1OpWZKYw0NiQSTf-VFvA7c65EDci6LJQ6kaa_bL91_n9nP4mTriWtrruV7Syz2u96Am4rcnAHU6zVPmJ2gfNJ5NZLWbG87iRlkXXABgEBdyKx3VBnUfaVfJsJc2ixajNf0JeB-mWCpOgTb_CdicT_MHE"/>
        </div>
        <div class="overflow-hidden bg-surface-container">
          <img class="w-full h-full object-cover grayscale hover:grayscale-0 transition-all duration-500 cursor-pointer" alt="Wedding photography" src="https://lh3.googleusercontent.com/aida-public/AB6AXuClUCzrHObF2HQqYBG61J6ErkRmqUOHO32bLiVljLqsm_eLEmz5gG8ja6Sts2M9Pisal95ctDNzQXXvXw1_imPKzj6F3ncz0aBgq7f_KxLxvMKKXcztj_zk0IZxKDP3mXIb7Vo4vAONDNtzfn2sckI5ZdyQy1As--61ruG59N8eCCc9kA2AA4WHwD8T98yPucB50OcbpXlceO12fGP__mpTtCrspcU-mBfKZz2LntxyDfiZXFqZScq2mPjEsI6chWP0SbtyolAWYRI"/>
        </div>
        <div class="overflow-hidden bg-surface-container">
          <img class="w-full h-full object-cover grayscale hover:grayscale-0 transition-all duration-500 cursor-pointer" alt="Interior space" src="https://lh3.googleusercontent.com/aida-public/AB6AXuDBAK8fW-L1rG0wuNATAWWPuLK011IH7i3S8FBJkyJNsm8-mUrAllawchR-pb9Sb7YYu4NQAm0HSMftBXnCvm31ryKEb8baHau16qXD72FqRVC0jWLlTfq1rRxwSc6sNLxhdkQEgQTm67mVxZS9yAJ95w9IZkU4SphvlYAk-odTlE0L2Cx6_OFHzlScVNE1lvP-quUXwLyOn5cmkdN3d2jOikjjqe-wltqbwMyUsd8J1HEdrzezySen0oa7BY32bgR-t8dFb5RuDZQ"/>
        </div>
        <div class="col-span-2 overflow-hidden bg-surface-container">
          <img class="w-full h-full object-cover grayscale hover:grayscale-0 transition-all duration-500 cursor-pointer" alt="Landscape" src="https://lh3.googleusercontent.com/aida-public/AB6AXuBrypYQ7UOGHlzXR1Z21ScWds1dAYK188XWEoi-DaN1RKrdgL0Wp5ucgbcGmUPDHvwA0mDOzSGRC2HjBA7ISuCm1cXpPMX7jkwl_OHY2DqsRCoyxIGwWY4oM71Abg9sIXDCD6CCHy28ATWyLQIqy5G8ay-VAC16ZXkU0c1FcF866ODU6wYZK-KT7oIVVpCzX9PVohLR3LOUXYFwrLCWaPHaMTHcsgexuoAd0Hl-Fc8s3-uPVQUjVX28G0HtqhhKJlH3JbUJjWKmjQw"/>
        </div>
      </div>
    </section>
  </main>
</template>