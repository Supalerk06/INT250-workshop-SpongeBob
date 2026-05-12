<template>
  <main class="pt-32 pb-20 px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto min-h-screen">
    <div class="animate-fade-in flex flex-col gap-12">
      <div class="flex flex-col gap-4">
        <span class="text-label-sm tracking-widest font-semibold uppercase text-outline">Reservation</span>
        <h1 class="text-display text-primary">Book a Session</h1>
        <p class="text-lg text-secondary max-w-2xl">
          Secure your date for a professional photography session. Choose your preferred package and we'll handle the rest.
        </p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
        <div class="bg-surface-container p-8 md:p-12 border border-outline-variant/20 flex flex-col gap-8">
          <h2 class="text-2xl font-medium">Session Details</h2>
          <form class="flex flex-col gap-6">
            <div class="flex flex-col gap-2">
              <label class="text-label-sm tracking-widest font-semibold uppercase text-secondary">Full Name</label>
              <input type="text" placeholder="Your Name" class="bg-surface border border-outline-variant/30 p-4 focus:outline-none focus:border-primary transition-colors" />
            </div>
            <div class="flex flex-col gap-2">
              <label class="text-label-sm tracking-widest font-semibold uppercase text-secondary">Email Address</label>
              <input type="email" placeholder="email@example.com" class="bg-surface border border-outline-variant/30 p-4 focus:outline-none focus:border-primary transition-colors" />
            </div>
            <div class="flex flex-col gap-2">
              <label class="text-label-sm tracking-widest font-semibold uppercase text-secondary">Session Type</label>
              <select class="bg-surface border border-outline-variant/30 p-4 focus:outline-none focus:border-primary transition-colors appearance-none">
                <option>Architectural</option>
                <option>Editorial</option>
                <option>Portrait</option>
              </select>
            </div>
            <button type="submit" class="bg-primary text-on-primary p-5 text-label-sm tracking-widest font-semibold uppercase mt-4 hover:opacity-90 transition-opacity">
              SUBMIT REQUEST
            </button>
          </form>
        </div>
        
        <div class="flex flex-col gap-8">
          <div class="aspect-video bg-surface-container overflow-hidden">
            <img src="https://lh3.googleusercontent.com/aida-public/AB6AXuBRH2VvtPYmHtTcoKxMfFOtDBoX1Z6PoN6gpBprRL-EB_Ng4kuw9YPllAAjcmDigbG4Dw0imMM9oi8eMVZkzj3_3LdEUm3mi27inVefSdkahyTAz19vwPtvlaqC-auX5c4GheH0tgYQIHYkThm294NIHAjZjdLpO1dz6Jir0TCZQfOtEVtQzB-CgtR9VG_D93XGKbCe81qYAFw9tvj7Y1h-Ms8yvhCg1wOCC9kjZXXprPtTHwdGGCX3b7N2EGCu-suTWSxVncRytDg" alt="Studio" class="w-full h-full object-cover opacity-50 grayscale" />
          </div>
          <div class="flex flex-col gap-4">
            <h3 class="text-xl font-medium">Why choose Fotof?</h3>
            <p class="text-secondary">
              Our process is designed for clarity and excellence. Every session includes a consultation to ensure your vision is perfectly captured.
            </p>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
