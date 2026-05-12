<script setup>
import { ref } from 'vue'

// สามารถเพิ่ม State สำหรับผูกกับฟอร์มได้ที่นี่
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
  <main class="pt-24 pb-16">
    <!-- Title Section -->
    <section class="px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto mb-12">
      <h1 class="text-3xl font-bold mb-4">Book a Session</h1>
      <p class="text-secondary">Fill out the form below to request a photography session.</p>
    </section>

    <!-- Booking Form -->
    <section class="px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto grid grid-cols-1 lg:grid-cols-2 gap-8">
      
      <!-- Form Column -->
      <div class="bg-surface-container p-6 border border-outline">
        <form @submit.prevent="submitForm" class="space-y-6">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div>
              <label class="block text-sm font-bold mb-2">Full Name</label>
              <input v-model="formData.fullName" required class="w-full border border-outline p-2 bg-white focus:outline-primary" placeholder="Jane Doe" type="text"/>
            </div>
            <div>
              <label class="block text-sm font-bold mb-2">Email Address</label>
              <input v-model="formData.email" required class="w-full border border-outline p-2 bg-white focus:outline-primary" placeholder="hello@example.com" type="email"/>
            </div>
          </div>

          <div>
            <label class="block text-sm font-bold mb-2">Service Category</label>
            <select v-model="formData.service" class="w-full border border-outline p-2 bg-white focus:outline-primary">
              <option value="commercial">Commercial</option>
              <option value="family">Family</option>
              <option value="event">Event</option>
              <option value="studio">Studio</option>
            </select>
          </div>

          <div>
            <label class="block text-sm font-bold mb-2">Preferred Location</label>
            <div class="flex gap-4">
              <label class="flex items-center gap-2">
                <input v-model="formData.location" type="radio" value="in-studio"/> In-Studio
              </label>
              <label class="flex items-center gap-2">
                <input v-model="formData.location" type="radio" value="on-location"/> On-Location
              </label>
            </div>
          </div>

          <div>
            <label class="block text-sm font-bold mb-2">Proposed Date</label>
            <input v-model="formData.date" required class="w-full border border-outline p-2 bg-white focus:outline-primary" type="date"/>
          </div>

          <div>
            <label class="block text-sm font-bold mb-2">Message</label>
            <textarea v-model="formData.message" class="w-full border border-outline p-2 bg-white focus:outline-primary" placeholder="Details..." rows="4"></textarea>
          </div>

          <button class="w-full bg-primary text-on-primary p-3 font-bold uppercase" type="submit">
            Confirm Request
          </button>
        </form>
      </div>

      <!-- Context Column -->
      <div class="flex flex-col gap-6">
        <div class="aspect-video bg-surface-container overflow-hidden">
          <img class="w-full h-full object-cover" alt="Studio" src="https://lh3.googleusercontent.com/aida-public/AB6AXuDfAAVAjlYP8_aZw-EUo4WpREWIhE3SkAgCB51Ua110Hss12-KBUuTYLevEyebCj7hI_dbLNHsBWMnEGLGgqE_4Xbg4vEg0v0mh66xw_J2r7_hIg9BnCdZ5vZ3BCxX3izTZ2JXABPsL-eZUS3A40q-lBnUklkkssGw4iEGfoPNJGHkJNEKlAneTYeFAsUhEHo24PXEPuOvpO1_onPSZUgfcclyczJ0H_fPvYt5TdT2gKUt8loOMEfMkXYaVNowD-W2-m20AHdWLkbc"/>
        </div>
        
        <div class="bg-surface-container p-6 border border-outline">
          <h3 class="text-lg font-bold mb-4">Inclusions</h3>
          <ul class="space-y-2">
            <li>• High-resolution digital files</li>
            <li>• Professional retouching</li>
            <li>• Online gallery access</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- Recent Projects Section -->
    <section class="mt-16 px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto">
      <h2 class="text-2xl font-bold mb-8">Recent Projects</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
        <div class="aspect-square bg-surface-container overflow-hidden border border-outline">
          <img class="w-full h-full object-cover" src="https://lh3.googleusercontent.com/aida-public/AB6AXuCPl-VXV6aHiBLfSBUS_wr5hYpH6H1ITBSA_cQMYznUZ-Ru9Oy753c3jxikAxfgdrxVqFchHMa-qJmJGh5RXhuZl8sz-iHig9RqfRcusokYbJg3vk_X2sP1OpWZKYw0NiQSTf-VFvA7c65EDci6LJQ6kaa_bL91_n9nP4mTriWtrruV7Syz2u96Am4rcnAHU6zVPmJ2gfNJ5NZLWbG87iRlkXXABgEBdyKx3VBnUfaVfJsJc2ixajNf0JeB-mWCpOgTb_CdicT_MHE"/>
        </div>
        <div class="aspect-square bg-surface-container overflow-hidden border border-outline">
          <img class="w-full h-full object-cover" src="https://lh3.googleusercontent.com/aida-public/AB6AXuClUCzrHObF2HQqYBG61J6ErkRmqUOHO32bLiVljLqsm_eLEmz5gG8ja6Sts2M9Pisal95ctDNzQXXvXw1_imPKzj6F3ncz0aBgq7f_KxLxvMKKXcztj_zk0IZxKDP3mXIb7Vo4vAONDNtzfn2sckI5ZdyQy1As--61ruG59N8eCCc9kA2AA4WHwD8T98yPucB50OcbpXlceO12fGP__mpTtCrspcU-mBfKZz2LntxyDfiZXFqZScq2mPjEsI6chWP0SbtyolAWYRI"/>
        </div>
        <div class="aspect-square bg-surface-container overflow-hidden border border-outline">
          <img class="w-full h-full object-cover" src="https://lh3.googleusercontent.com/aida-public/AB6AXuDBAK8fW-L1rG0wuNATAWWPuLK011IH7i3S8FBJkyJNsm8-mUrAllawchR-pb9Sb7YYu4NQAm0HSMftBXnCvm31ryKEb8baHau16qXD72FqRVC0jWLlTfq1rRxwSc6sNLxhdkQEgQTm67mVxZS9yAJ95w9IZkU4SphvlYAk-odTlE0L2Cx6_OFHzlScVNE1lvP-quUXwLyOn5cmkdN3d2jOikjjqe-wltqbwMyUsd8J1HEdrzezySen0oa7BY32bgR-t8dFb5RuDZQ"/>
        </div>
      </div>
    </section>
  </main>
</template>