# The Porcelain Palace 🚽
> **Midterm Task Performance — Business System Build**  
> **Live Deployment:** [https://the-porcelain-palace.onrender.com](https://the-porcelain-palace.onrender.com)  
> **Repository:** [https://github.com/BoatRider23/the-porcelain-palace](https://github.com/BoatRider23/the-porcelain-palace)

---

## 1. Project Overview & Business Description

**Business Name:** The Porcelain Palace  
**Core CRUD Entity:** Toilets (`toilets` collection in Cloud Firestore)  
**System Purpose:** A dedicated e-commerce showroom catalog for luxury porcelain commodes and smart bidets, coupled with an integrated on-demand dispatch schedule for an internal 3-master-plumber squad.

### Target Users:
* **Customers / Homeowners:** Browse luxury vitreous china commodes, inspect real-time unit stock counts, add products to cart, and bundle flat-rate professional installation with an available plumber during checkout.
* **Store Administrators:** Manage catalog inventory (Create, Read, Update, Delete toilet models), upload photos directly from local storage, and toggle shift dispatch statuses for the 3 master plumbers.

---

## 2. Problem Being Solved

Purchasing high-end sanitary ware traditionally suffers from fragmented fulfillment:
1. **Uncertain Inventory & Complex Specifications:** Homeowners struggle to find verified flush ratings (GPF), siphon jet specifications, and actual live warehouse availability before purchase.
2. **Third-Party Installation Risk:** Buying heavy, fragile ceramic fixtures usually leaves the buyer searching for unknown independent contractors, leading to improper rough-ins, improper seal seating, and water leaks.

**The Porcelain Palace** consolidates supply and installation into a single transaction:
* Provides transparent specs, anti-microbial glaze ratings, and live unit availability.
* Directly assigns licensed, accountable in-house plumbers (Mario, Luigi, and Bob) at checkout with an automated dispatch workflow.

---

## 3. Feature List

### Part 1: Landing Page & Public Showroom
* **Regal Aesthetic & Branding:** Ceramic-gloss UI, Tailwind CSS gradients, Playfair Display serif typography, and Lucide vector iconography.
* **Value Propositions:** Highlights 1,280°C anti-microbial nano-glaze, dual-action siphon water conservation, and a 10-year porcelain warranty.
* **3 Master Plumbers Showcase:** Publicly displays Mario, Luigi, and Bob with technical specialties, job completion counts, and live availability badges (`Available`, `Dispatched`, `Off-Duty`).
* **Live Stock Indicators:** Visual pill badges dynamically display stock status (`● X units available`, `● Only X left in stock!`, or `● Sold Out`). Unavailable items automatically disable purchase controls.
* **Mobile-First Responsive Layout:** Custom app dock fixed at the bottom for iOS and Android viewports (`Home`, `Catalog`, `3 Plumbers`, `Cart`, `Admin`).

### Part 2: Users & Authentication
* **Secure Firebase Auth:** Managed via Google Firebase Authentication utilizing salted and hashed credential storage (PBKDF2/scrypt).
* **Role-Based Access Control:**
  * **Customer:** Showroom browsing, stock inspection, cart assembly, plumber add-on scheduling, and checkout.
  * **Admin:** Unlocks the protected **Admin Control Center** to perform CRUD operations on inventory and control plumber schedules.
* **Protected Views & Route Guards:** Unauthorized attempts to access the Admin Panel trigger security toasts and redirect to authentication.
* **Auto-Filling Evaluation Credentials:** One-click `Use` credential buttons inside the authentication modal allow instructors to test Admin and Customer permissions instantly.

### Part 3: Core CRUD Operations (Toilets Entity)
* **Create (C):** Admins can add models with name, category, price, stock, flush rating (GPF), local image file upload, and descriptions.
* **Read (R):** Real-time data synchronization directly from Cloud Firestore into the public catalog and admin tables.
* **Update (U):** Admins can edit model pricing, stock quantities, technical flush specs, and descriptions.
* **Delete (D):** Protected deletion flow backed by a modal (*"Scrap This Throne?"*) to prevent accidental database purges.

---

## 4. Tech Stack

* **Frontend:** HTML5, Tailwind CSS (via CDN), Lucide Icons, Google Fonts (Inter & Playfair Display).
* **Backend as a Service (BaaS):** Firebase SDK v10 (Modular ES Modules).
  * **Authentication:** Firebase Auth (Email/Password provider).
  * **Database:** Cloud Firestore (Persistent NoSQL document store).
* **Deployment & Hosting:** Render (Static Site Service with auto-deploy on Git push).
* **Version Control:** Git & GitHub.

---

## 5. Setup and Run Instructions (Clean Machine)

### Option A: View Live Deployment
Visit the deployed application directly: **[https://the-porcelain-palace.onrender.com](https://the-porcelain-palace.onrender.com)**

### Option B: Run Locally via Git & VS Code
1. **Clone the repository:**
   ```bash
   git clone [https://github.com/BoatRider23/the-porcelain-palace.git](https://github.com/BoatRider23/the-porcelain-palace.git)