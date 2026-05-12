<template>
  <aside class="w-full lg:w-96 shrink-0">
    <div class="sticky top-32 bg-surface-container-low p-8 border border-outline-variant/20">
      <h2 class="font-headline-md text-headline-md mb-6 uppercase tracking-widest">Editing Requests</h2>
      <p class="font-body-md text-body-md text-secondary mb-8">Specify any final retouching or technical adjustments for your selected photographs. Each image includes one round of revisions.</p>
      
      <form class="space-y-8">
        <div class="space-y-2">
          <label class="font-label-sm text-label-sm uppercase text-primary">Target Image ID</label>
          <input type="text" placeholder="e.g. GLASS_HOUSE_042" class="w-full bg-transparent border-0 border-b border-outline p-0 py-2 focus:ring-0 focus:border-primary placeholder:text-outline-variant/50" />
        </div>
        <div class="space-y-2">
          <label class="font-label-sm text-label-sm uppercase text-primary">Revision Details</label>
          <textarea rows="4" placeholder="e.g. Reduce glare on surface, soften skin texture..." class="w-full bg-transparent border-0 border-b border-outline p-0 py-2 focus:ring-0 focus:border-primary placeholder:text-outline-variant/50 resize-none"></textarea>
        </div>
        <div class="pt-4">
          <button type="submit" class="w-full bg-primary text-on-primary py-4 font-label-sm text-label-sm uppercase tracking-[0.2em] hover:bg-primary/90 transition-colors">
            SUBMIT REQUESTS
          </button>
        </div>
      </form>

      <div class="mt-12 pt-8 border-t border-outline-variant/30">
        <h3 class="font-label-sm text-label-sm mb-4 uppercase tracking-widest text-secondary">Summary</h3>
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