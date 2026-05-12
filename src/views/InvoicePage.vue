<template>
  <main class="pt-32 pb-20 px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto min-h-screen">
    <div class="animate-fade-in flex flex-col gap-12">
      <div class="flex flex-col gap-4">
        <span class="text-label-sm tracking-widest font-semibold uppercase text-outline">Billing</span>
        <h1 class="text-display text-primary">Invoice</h1>
        <p class="text-lg text-secondary max-w-2xl">
          Review your session details and complete payment.
        </p>
      </div>
      
      <div class="bg-surface-container-high p-8 md:p-16 border border-outline-variant/20 shadow-sm max-w-4xl mx-auto w-full">
        <div class="flex justify-between items-start border-b border-outline-variant pb-8 mb-8">
          <div>
            <h2 class="text-2xl font-bold">FOTOF STUDIO</h2>
            <p class="text-secondary text-label-sm tracking-widest font-semibold uppercase mt-2">123 Design District, Creative City</p>
          </div>
          <div class="text-right">
            <p class="text-label-sm tracking-widest font-semibold uppercase font-bold">INVOICE #INV-2024-001</p>
            <p class="text-secondary text-label-sm tracking-widest font-semibold uppercase mt-1">May 12, 2024</p>
          </div>
        </div>
        
        <div class="flex flex-col gap-8">
          <table class="w-full text-left">
            <thead>
              <tr class="border-b border-outline-variant/50">
                <th class="py-4 text-label-sm tracking-widest font-semibold uppercase">Description</th>
                <th class="py-4 text-label-sm tracking-widest font-semibold uppercase text-right">Amount</th>
              </tr>
            </thead>
            <tbody>
              <tr class="border-b border-outline-variant/20">
                <td class="py-6">
                  <p class="font-medium">Architectural Photography Session</p>
                  <p class="text-label-sm tracking-widest font-semibold uppercase text-secondary mt-1">Half-day session + 10 edited photos</p>
                </td>
                <td class="py-6 text-right font-medium">$1,200.00</td>
              </tr>
              <tr class="border-b border-outline-variant/20">
                <td class="py-6">
                  <p class="font-medium">Travel Fee</p>
                  <p class="text-label-sm tracking-widest font-semibold uppercase text-secondary mt-1">Within city limits</p>
                </td>
                <td class="py-6 text-right font-medium">$150.00</td>
              </tr>
            </tbody>
            <tfoot>
              <tr>
                <td class="pt-8 text-xl font-bold uppercase">Total Due</td>
                <td class="pt-8 text-xl font-bold text-right">$1,350.00</td>
              </tr>
            </tfoot>
          </table>
          
          <div class="flex justify-end gap-4 mt-8">
            <button class="px-8 py-4 border border-primary text-primary text-label-sm tracking-widest font-semibold uppercase hover:bg-primary hover:text-on-primary transition-all">
              DOWNLOAD PDF
            </button>
            <button class="px-8 py-4 bg-primary text-on-primary text-label-sm tracking-widest font-semibold uppercase hover:opacity-90 transition-all">
              PAY NOW
            </button>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
