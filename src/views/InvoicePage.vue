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
  <main class="pt-32 pb-section-gap px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto">
    <div class="grid grid-cols-1 lg:grid-cols-12 gap-gutter">

      <!-- Left Column: Invoice Details -->
      <div class="lg:col-span-8">
        <h1 class="font-display text-display mb-12">Invoice INV-2024-0812</h1>

        <!-- Items Table -->
        <div class="w-full overflow-x-auto">
          <table class="w-full text-left border-collapse">
            <thead>
              <tr class="border-b border-outline-variant">
                <th class="py-6 font-label-sm text-label-sm text-secondary uppercase tracking-widest">Description</th>
                <th class="py-6 font-label-sm text-label-sm text-secondary uppercase tracking-widest text-right">Quantity</th>
                <th class="py-6 font-label-sm text-label-sm text-secondary uppercase tracking-widest text-right">Amount</th>
              </tr>
            </thead>
            <tbody class="font-body-md text-body-md">
              <tr class="border-b border-outline-variant/30">
                <td class="py-8">
                  <div class="flex items-center gap-6">
                    <div class="w-20 h-20 bg-surface-container overflow-hidden shrink-0">
                      <img class="w-full h-full object-cover" alt="Portrait Session" src="https://lh3.googleusercontent.com/aida-public/AB6AXuCgCjC83yn88uytpo_FzLVA6_NLCJZv5vWNuOpBPq74_QuUrrbL9Ev3GYVUMbK5BiDdT8oqp27aMn1SK0XiFTtWJJG3UeIyJaTtBElWW-hAlbdErKl5jEDXjJHE8XBrnGX8lt6N9xJawpk43VVfTFtrgkiC6d-mSByjN36_uzQGjO7k1H74PCL2ig5geJkHry3uY9n_W0e7hSSj96jvkQS5jT4qLLhNPJo3O86oSJ4nCWqjTiQPJnOdv6odqerpoaf9EfDafR8XMxs"/>
                    </div>
                    <div>
                      <p class="font-semibold">Portrait Session - Master Selection</p>
                      <p class="text-sm text-secondary">High-resolution digital file</p>
                    </div>
                  </div>
                </td>
                <td class="py-8 text-right">05</td>
                <td class="py-8 text-right">$450.00</td>
              </tr>
              <tr class="border-b border-outline-variant/30">
                <td class="py-8">
                  <div class="flex items-center gap-6">
                    <div class="w-20 h-20 bg-surface-container overflow-hidden shrink-0">
                      <img class="w-full h-full object-cover" alt="Fine Art Retouching" src="https://lh3.googleusercontent.com/aida-public/AB6AXuAgDYxsAoVKfKILtXxJ6b8LjMZGVkX-hiUKTOolPpLmLOEBjTOXLAqUbK6oxoCweChAvehASaUyKBGjj2FQz_8eJB19j4GLpQVmUqSOaNM6vWEX8rKqGpSamKcIAA0eAg0LW7INE61rhr4-M3JADM5lE_lluHqvcuEjUJT3lgjJ7QrUs3ebY67nw37xjo0Md-b-fTKDdV8YFp7ekeRV2Ia4FzWvrbBrZQUYxAtnrdV-vkvIDTc7z9jFNbH279u9JJKAKhEu1tGap24"/>
                    </div>
                    <div>
                      <p class="font-semibold">Fine Art Retouching</p>
                      <p class="text-sm text-secondary">Advanced skin texture & color grading</p>
                    </div>
                  </div>
                </td>
                <td class="py-8 text-right">03</td>
                <td class="py-8 text-right">$120.00</td>
              </tr>
              <tr class="border-b border-outline-variant/30">
                <td class="py-8">
                  <div>
                    <p class="font-semibold">Studio Usage Fee</p>
                    <p class="text-sm text-secondary">Base facility and equipment fee</p>
                  </div>
                </td>
                <td class="py-8 text-right">01</td>
                <td class="py-8 text-right">$150.00</td>
              </tr>
            </tbody>
          </table>
        </div>

        <!-- Delivery Options -->
        <div class="mt-16">
          <h2 class="font-headline-lg text-headline-lg mb-8">Delivery Method</h2>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <label class="border border-outline-variant p-8 flex items-start gap-4 cursor-pointer hover:bg-surface-container-low transition-colors group">
              <!-- ผูก v-model เข้ากับ deliveryMethod -->
              <input v-model="deliveryMethod" class="mt-1 w-5 h-5 text-primary focus:ring-primary border-outline" name="delivery" type="radio" value="pickup"/>
              <div>
                <span class="font-label-sm text-label-sm uppercase tracking-widest block mb-2">Pickup at Studio</span>
                <p class="text-secondary text-sm">Collect your physical prints from our downtown gallery. No additional charge.</p>
              </div>
            </label>

            <label class="border border-outline-variant p-8 flex items-start gap-4 cursor-pointer hover:bg-surface-container-low transition-colors group">
              <!-- ผูก v-model เข้ากับ deliveryMethod -->
              <input v-model="deliveryMethod" class="mt-1 w-5 h-5 text-primary focus:ring-primary border-outline" name="delivery" type="radio" value="postal"/>
              <div>
                <span class="font-label-sm text-label-sm uppercase tracking-widest block mb-2">Postal Delivery</span>
                <p class="text-secondary text-sm">Insured courier delivery to your registered address. +$25.00 flat rate.</p>
              </div>
            </label>
          </div>
        </div>
      </div>

      <!-- Right Column: Summary & Payment -->
      <div class="lg:col-span-4">
        <div class="bg-surface-container-low p-10 sticky top-32">
          <h3 class="font-headline-md text-headline-md mb-8">Order Summary</h3>
          <div class="space-y-4 mb-8">
            <div class="flex justify-between font-body-md">
              <span class="text-secondary">Subtotal</span>
              <span>${{ subtotal.toFixed(2) }}</span>
            </div>
            <div class="flex justify-between font-body-md">
              <span class="text-secondary">Taxes (8%)</span>
              <span>${{ tax.toFixed(2) }}</span>
            </div>
            <div class="flex justify-between font-body-md">
              <span class="text-secondary">Delivery</span>
              <!-- แสดงค่าจัดส่งแบบ Dynamic -->
              <span>${{ deliveryFee.toFixed(2) }}</span>
            </div>
          </div>

          <div class="border-t border-outline-variant pt-6 mb-10">
            <div class="flex justify-between items-baseline">
              <span class="font-label-sm text-label-sm uppercase tracking-widest">Total Amount</span>
              <!-- แสดงยอดรวมแบบ Dynamic -->
              <span class="font-headline-lg text-headline-lg">${{ totalAmount.toFixed(2) }}</span>
            </div>
          </div>

          <div class="space-y-6">
            <div class="group">
              <label class="font-label-sm text-label-sm text-secondary uppercase block mb-2">Payment Method</label>
              <div class="border-b border-outline group-focus-within:border-primary transition-colors py-2 flex items-center justify-between cursor-pointer">
                <span class="font-body-md">Credit Card</span>
                <span class="material-symbols-outlined text-secondary">expand_more</span>
              </div>
            </div>

            <button @click="handlePayment" class="w-full bg-primary text-on-primary py-5 font-label-sm text-label-sm tracking-[0.2em] uppercase hover:opacity-90 transition-opacity flex items-center justify-center gap-3">
              Pay Invoice
              <span class="material-symbols-outlined text-sm">arrow_forward</span>
            </button>
          </div>

          <p class="mt-8 text-xs text-secondary text-center leading-relaxed">
            By clicking "Pay Invoice", you agree to our Terms of Service and Privacy Policy regarding digital and physical assets.
          </p>
        </div>
      </div>

    </div>
  </main>
</template>
 