# The Porcelain Palace 🚽
> **Midterm Task Performance — Business System Build**  
> **Live Deployment:** [https://the-porcelain-palace.onrender.com](https://the-porcelain-palace.onrender.com)  
> **Repository:** [https://github.com/BoatRider23/the-porcelain-palace](https://github.com/BoatRider23/the-porcelain-palace)

---

## 1. Project Overview & Business Description

**Business Name:** The Porcelain Palace  
**Core CRUD Entity:** Toilets (`toilets` collection in Firestore)  
**System Purpose:** E-commerce showroom catalog for high-end porcelain toilets integrated with an on-demand installation service powered by a dedicated 3-master-plumber roster.

### Target Users:
* **Customers / Homeowners:** Browse luxury vitreous china toilets, view real-time available stock, add items to cart, and optionally attach professional installation from an available master plumber at checkout.
* **Store Administrators:** Manage catalog inventory (Create, Read, Update, Delete toilet models) and manage live dispatch statuses for the 3 master plumbers.

---

## 2. Problem Being Solved

Purchasing bathroom sanitary ware is traditionally fractured. Homeowners buy heavy, fragile ceramic fixtures from supply stores, then struggle to find trustworthy, licensed plumbers to handle rough-ins, pressure testing, and leak-free installations. 

**The Porcelain Palace** bridges retail and trade service:
1. Provides full visibility into ceramic specs, GPF (gallons per flush) water ratings, and live stock levels.
2. Directly bundles an on-demand, flat-rate installation service handled exclusively by an internal, accountable 3-plumber squad (Mario, Luigi, and Bob), eliminating third-party contractor risk.

---

## 3. Feature List

### Part 1: Landing Page (Public)
* **Regal Aesthetic & Branding:** Designed with ceramic-gloss styling, Tailwind CSS, Playfair Display serif typography, and Lucide vector icons.
* **Value Propositions:** Highlights 1,280°C anti-microbial nano-glaze, dual-action siphon water conservation, and a 10-year porcelain warranty.
* **3 Master Plumbers Showcase:** Publicly displays Mario, Luigi, and Bob with their technical specialties, live availability badges (`Available`, `Dispatched`, `Off-Duty`), and completed job tallies.
* **Live Stock Indicators:** Every toilet in the catalog features an instant stock badge for customers (`● X units available`, `● Only X left in stock!`, or `● Sold Out`). Out-of-stock items disable purchase buttons automatically.
* **Mobile-First Responsive Layout:** Full mobile support for iOS and Android featuring a fixed app-style bottom navigation dock (`Home`, `Catalog`, `3 Plumbers`, `Cart`, `Admin`).

### Part 2: Users & Authentication
* **Secure Firebase Auth:** Powered by Firebase Authentication using server-side PBKDF2/scrypt password hashing (no plain-text passwords stored).
* **Role-Based Access Control:**
  * **Customer:** Browse catalog, view live inventory levels, add toilets to cart, schedule plumber installation, and checkout.
  * **Admin:** Full access to the protected **Admin Control Center** to manage toilet inventory and plumber shifts.
* **Protected Views:** Unauthenticated users attempting to access the Admin Panel are blocked with error toast alerts and redirected to the login modal.
* **Auto-Filling Evaluation Credentials:** The Sign-In modal includes sample credential buttons (`Use`) allowing instructors to test Admin and Customer roles instantly.

### Part 3: Core CRUD Operations (Toilets Entity)
* **Create (C):** Admins can add new toilets to Firestore with model name, category, price, stock, flush rating (GPF), custom image URL, and description.
* **Read (R):** Real-time data synchronization directly from Cloud Firestore into the public showroom catalog and the Admin inventory table.
* **Update (U):** Admins can edit model specs, restock counts, flush ratings, and pricing.
* **Delete (D):** Safe deletion process protected by a confirmation modal (*"Scrap This Throne?"*) to prevent accidental data loss.

---

## 4. Tech Stack

* **Frontend:** HTML5, Tailwind CSS (via CDN), Lucide Icons, Google Fonts (Inter & Playfair Display).
* **Backend as a Service (BaaS):** Firebase SDK v10 (Modular ES Modules).
  * **Authentication:** Firebase Auth (Email/Password).
  * **Database:** Cloud Firestore (Persistent NoSQL document storage).
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