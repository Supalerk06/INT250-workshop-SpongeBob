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
  <main class="pt-24 pb-16 px-4">
    <div class="max-w-2xl mx-auto">
      <h1 class="text-3xl font-bold mb-4">Book a Session</h1>
      <p class="text-secondary mb-8">Fill out the form below to request a photography session.</p>

      <div class="bg-surface-container p-8 border border-outline">
        <form @submit.prevent="submitForm" class="space-y-6">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <div>
              <label class="block font-bold mb-1">Full Name</label>
              <input v-model="formData.fullName" required class="w-full border border-outline p-2 bg-white" type="text"/>
            </div>
            <div>
              <label class="block font-bold mb-1">Email</label>
              <input v-model="formData.email" required class="w-full border border-outline p-2 bg-white" type="email"/>
            </div>
          </div>

          <div>
            <label class="block font-bold mb-1">Service</label>
            <select v-model="formData.service" class="w-full border border-outline p-2 bg-white">
              <option value="commercial">Commercial</option>
              <option value="family">Family</option>
              <option value="event">Event</option>
            </select>
          </div>

          <div>
            <label class="block font-bold mb-1">Date</label>
            <input v-model="formData.date" required class="w-full border border-outline p-2 bg-white" type="date"/>
          </div>

          <div>
            <label class="block font-bold mb-1">Message</label>
            <textarea v-model="formData.message" class="w-full border border-outline p-2 bg-white" rows="4"></textarea>
          </div>

          <button class="w-full bg-primary text-on-primary p-3 font-bold" type="submit">
            Confirm Booking
          </button>
        </form>
      </div>
    </div>
  </main>
</template>