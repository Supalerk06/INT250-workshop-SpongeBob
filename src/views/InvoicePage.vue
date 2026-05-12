 <script setup>
import { ref, computed } from 'vue'


const deliveryMethod = ref('pickup')


const subtotal = 720.00
const tax = 57.60


const deliveryFee = computed(() => {
  return deliveryMethod.value === 'pickup' ? 0 : 25.00
})


const totalAmount = computed(() => {
  return subtotal + tax + deliveryFee.value
})

const handlePayment = () => {
  alert(`Processing payment of $${totalAmount.value.toFixed(2)}...`)
}
</script>

<template>
  <main class="pt-24 pb-16 px-4">
    <div class="max-w-4xl mx-auto">
      <h1 class="text-3xl font-bold mb-8">Invoice INV-2024-0812</h1>

      <div class="border border-outline overflow-hidden mb-8">
        <table class="w-full text-left">
          <thead>
            <tr class="bg-surface-container border-b border-outline">
              <th class="p-4 font-bold">Description</th>
              <th class="p-4 font-bold text-right">Qty</th>
              <th class="p-4 font-bold text-right">Amount</th>
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

      <div class="max-w-xs ml-auto bg-surface-container p-6 border border-outline">
        <div class="space-y-2 mb-6">
          <div class="flex justify-between">
            <span>Subtotal</span>
            <span>$720.00</span>
          </div>
          <div class="flex justify-between font-bold text-lg border-t border-outline pt-2">
            <span>Total</span>
            <span>$777.60</span>
          </div>
        </div>
        <button @click="handlePayment" class="w-full bg-primary text-on-primary py-3 font-bold uppercase">
          Pay Now
        </button>
      </div>
    </div>
  </main>
</template>


 