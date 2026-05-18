# 📸 FOTOF Studio - Minimalist Booking & Gallery System

> **INT250 CSS Framework (2/2025)**  
> **Group SpongeBob**  

---

## 📖 Case Study: The Fotof Scenario
**Fotof** is a professional studio offering premium family, personal event (weddings & parties), and commercial photography. Annually, the studio manages over **10,000 commercial orders** and **80,000 private orders**. 

This web application represents the **Booking-to-Cash process**, bridging:
1. **Client Booking/Inquiry** (In-studio or on-location requests).
2. **Private Client Gallery Proofing** (Selecting print/digital images and requesting special retouching annotations).
3. **Automated Invoicing & Delivery Choice** (Picking up at the studio for free vs. postal delivery with a dynamic shipment fee).

---

## 🎨 Design System & Aesthetics (Tailwind CSS v4)
This project is styled with the state-of-the-art **Tailwind CSS v4** engine, creating a highly premium, modern, and minimalist editorial design.

*   **Color Palette (HSL Curated):** Sleek, editorial monochrome scheme using pitch black, crisp white, muted greys/slates, and structural borders.
*   **Aesthetics:** High-contrast layout, premium serif-emulating serif headers (`font-display`), smooth transitions, responsive grids, and high-fidelity hovering states.
*   **Dark Mode Syncing:** Full support for system-wide light/dark themes, complete with a manual toggle in the navigation bar that persists user preferences using `localStorage`.

---

## 🖥️ Core Pages & Page Structure
The application fully satisfies the **Step 2: Website Structure** requirements by implementing a complete multi-page web app with **6 detailed pages**:

### 1. 🏠 Home Page (`LandingPage.vue`)
*   **Features:** Clean editorial hero layout with a "Book a Session" call-to-action, a beautiful interactive "Featured Works" showcase linking to client galleries, and a studio vision banner.
*   **Animations:** Integrated `IntersectionObserver` to trigger elegant fade-and-slide micro-animations as the user scrolls.

### 👥 2. About Page (`AboutPage.vue`)
*   **Features:** Details the scale of operations (commercial vs. private orders) and introduces the core studio team roles described in the case study:
    *   **Senior Studio Manager / Senior Customer Service Representative**
    *   **Junior Customer Representative**
    *   **Creative Photographers**
    *   **Lab & Retouch Technicians**

### 📅 3. Booking Form Page (`BookingPage.vue`)
*   **Features:** Responsive inquiry form allowing clients to choose:
    *   **Service Category:** Commercial & Editorial, Family & Portrait, Personal Event, or Fine Art Studio.
    *   **Preferred Location:** In-Studio vs. On-Location (which determines pricing parameters).
    *   **Interactive Inclusions:** Dynamic info blocks and recent portfolio showcases.

### 🖼️ 4. Interactive Proofing Gallery (`GalleryPage.vue`)
*   **Features:** 
    *   **30-day Expiration Banner:** Warning clients about the 30-day proof deletion policy (with reminders sent 5 days before).
    *   **Photo Proof Selection Cards:** Grid of high-res proofs displaying on-hover selectors for print copies and digital downloads.
    *   **Revision Request Sidebar:** A form for clients to specify individual picture IDs and submit custom retouch instructions (special requests).

### 🧾 5. Dynamic Invoicing & Payments (`InvoicePage.vue`)
*   **Features:** 
    *   Itemized billing breakdown (retouch fees, session fees, and base facility hire).
    *   **Interactive Delivery Selector:** Toggle between *Pickup at Studio ($0.00)* and *Postal Delivery (+$25.00)*.
    *   **Reactive Totals:** Automatically calculates delivery fee changes and updates the Subtotal, Taxes (8%), and Grand Total in real-time.

### 📰 6. News & Guides Page (`NewsPage.vue`)
*   **Features:** Client-facing journal entries outlining:
    *   **Operational policies:** Explaining gallery expiry rules, rescheduled bookings, and cancellation/no-show fees (€50 for on-location no-shows, €100/€150 default fees for un-ordered galleries).
    *   **Behind-the-scenes:** Inside look at the studio's advanced fine-art color grading and commercial achievements.

---

## 🛠️ Technical Stack
*   **Core Framework:** Vue 3 (Composition API with `<script setup>`)
*   **Styling Engine:** Tailwind CSS v4 (incorporating `@theme` variables for fonts, container max-widths, and layout spacing)
*   **Router:** Vue Router (configured with clean history modes and default scroll restoration behavior)
*   **Icons:** Google Material Symbols (Outlined)

---

## 🚀 Project Setup & Execution

### 1. Install Dependencies
```bash
npm install
```

### 2. Compile and Hot-Reload for Development
```bash
npm run dev
```

### 3. Build and Minify for Production
```bash
npm run build
```

### 4. Preview Production Build Locally
```bash
npm run preview
```

---

## 👥 Group SpongeBob Team Roster

| Student ID | Full Name | Responsible |
| :--- | :--- | :--- |
| `6713050006` | Natthasith Boonheng | InvoicePage and Report|
| `67130500028` | Phakaphol Dherachaisuphakij | Darkmode , BookingPage and NewsPage |
| `67130500074` | Thitirat Srithomya | Component Design and GalleryPage |
| `67130500117` | Supalerk Kamolnetr| README , LandingPage and AboutPage |