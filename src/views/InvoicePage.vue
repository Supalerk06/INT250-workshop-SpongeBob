 <script setup>
import { ref, computed } from 'vue'

// State สำหรับเก็บรูปแบบการจัดส่งที่เลือก
const deliveryMethod = ref('pickup')

// ข้อมูลราคาสินค้า (สมมติว่าเป็นข้อมูลที่ดึงมาจาก Database หรือ Props)
const subtotal = 720.00
const tax = 57.60

// คำนวณค่าส่งอัตโนมัติตามตัวเลือก
const deliveryFee = computed(() => {
  return deliveryMethod.value === 'pickup' ? 0 : 25.00
})

// คำนวณยอดรวมทั้งหมดอัตโนมัติ
const totalAmount = computed(() => {
  return subtotal + tax + deliveryFee.value
})

const handlePayment = () => {
  alert(`Processing payment of $${totalAmount.value.toFixed(2)}...`)
}
</script>

<template>
  <main class="pt-24 pb-16 px-4 max-w-container-max mx-auto">
    <div class="grid grid-cols-1 lg:grid-cols-12 gap-8">

      <!-- Left Column -->
      <div class="lg:col-span-8">
        <h1 class="text-3xl font-bold mb-8">Invoice INV-2024-0812</h1>

        <!-- Table -->
        <div class="w-full overflow-x-auto">
          <table class="w-full border border-outline">
            <thead>
              <tr class="bg-surface-container border-b border-outline">
                <th class="p-4 text-left font-bold text-sm">Description</th>
                <th class="p-4 text-right font-bold text-sm">Qty</th>
                <th class="p-4 text-right font-bold text-sm">Amount</th>
              </tr>
            </thead>
            <tbody>
              <tr class="border-b border-outline">
                <td class="p-4">Portrait Session</td>
                <td class="p-4 text-right">05</td>
                <td class="p-4 text-right">$450.00</td>
              </tr>
              <tr class="border-b border-outline">
                <td class="p-4">Retouching</td>
                <td class="p-4 text-right">03</td>
                <td class="p-4 text-right">$120.00</td>
              </tr>
              <tr class="border-b border-outline">
                <td class="p-4">Studio Fee</td>
                <td class="p-4 text-right">01</td>
                <td class="p-4 text-right">$150.00</td>
              </tr>
            </tbody>
          </table>
        </div>

        <!-- Delivery -->
        <div class="mt-12">
          <h2 class="text-xl font-bold mb-6">Delivery Method</h2>
          <div class="space-y-4">
            <label class="border border-outline p-4 flex items-start gap-3 cursor-pointer bg-surface-container">
              <input v-model="deliveryMethod" name="delivery" type="radio" value="pickup"/>
              <div>
                <span class="font-bold block">Pickup at Studio</span>
                <p class="text-secondary text-sm">No additional charge.</p>
              </div>
            </label>

            <label class="border border-outline p-4 flex items-start gap-3 cursor-pointer bg-surface-container">
              <input v-model="deliveryMethod" name="delivery" type="radio" value="postal"/>
              <div>
                <span class="font-bold block">Postal Delivery</span>
                <p class="text-secondary text-sm">+$25.00 flat rate.</p>
              </div>
            </label>
          </div>
        </div>
      </div>

      <!-- Right Column -->
      <div class="lg:col-span-4">
        <div class="bg-surface-container p-8 border border-outline sticky top-24">
          <h3 class="text-lg font-bold mb-6">Order Summary</h3>
          <div class="space-y-2 mb-6">
            <div class="flex justify-between">
              <span>Subtotal</span>
              <span>${{ subtotal.toFixed(2) }}</span>
            </div>
            <div class="flex justify-between">
              <span>Tax (8%)</span>
              <span>${{ tax.toFixed(2) }}</span>
            </div>
            <div class="flex justify-between font-bold">
              <span>Total</span>
              <span>${{ totalAmount.toFixed(2) }}</span>
            </div>
          </div>

          <button @click="handlePayment" class="w-full bg-primary text-on-primary py-4 font-bold uppercase">
            Pay Invoice
          </button>
        </div>
      </div>

    </div>
  </main>
</template>

 