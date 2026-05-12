<template>
  <aside class="w-full lg:w-80 shrink-0">
    <div class="sticky top-24 bg-surface-container p-6 border border-outline">
      <h2 class="text-lg font-bold mb-4">Requests</h2>
      <p class="text-sm text-secondary mb-6">Specify any adjustments for your selected photos.</p>
      
      <form class="space-y-4">
        <div>
          <label class="block text-xs font-bold mb-1">Target ID</label>
          <input type="text" placeholder="e.g. IMG_001" class="w-full border border-outline p-2 bg-white" />
        </div>
        <div>
          <label class="block text-xs font-bold mb-1">Revision Details</label>
          <textarea rows="4" placeholder="Details..." class="w-full border border-outline p-2 bg-white resize-none"></textarea>
        </div>
        <button type="submit" class="w-full bg-primary text-on-primary py-3 font-bold">
          Submit
        </button>
      </form>


      <div class="mt-12 pt-8 border-t border-outline-variant/30">
        <h3 class="font-label-sm  mb-4 uppercase tracking-widest text-secondary">Summary</h3>
        <div class="flex justify-between font-body-md py-2">
          <span>Photos Selected</span>
          <span>12</span>
        </div>
        <div class="flex justify-between font-body-md py-2">
          <span>Digital Downloads</span>
          <span>Included</span>
        </div>
        <div class="flex justify-between font-body-md py-2 border-b border-outline-variant/20 mb-6">
          <span>Print Credits</span>
          <span>$250.00 Remaining</span>
        </div>
      </div>
    </div>
  </aside>
</template>