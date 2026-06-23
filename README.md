# Hisabika – Simple Billing, Smart Business
### Developed by Trishab Online Service

---

## 🚀 Quick Start

### 1. Firebase Setup (Required)

1. Go to [https://console.firebase.google.com](https://console.firebase.google.com)
2. Click **Add Project** → Name it `hisabika` → Create
3. Enable **Authentication**:
   - Go to Authentication → Sign-in method
   - Enable **Email/Password**
4. Enable **Realtime Database**:
   - Go to Realtime Database → Create Database
   - Start in **Test mode** (you'll update rules after)
5. Get your config:
   - Go to Project Settings → Your apps → Add Web App
   - Copy the `firebaseConfig` object

### 2. Add Firebase Config to index.html

Open `index.html` and replace the placeholder config (~line 800):

```javascript
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",                    // ← Replace
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  databaseURL: "https://YOUR_PROJECT-default-rtdb.firebaseio.com",
  projectId: "YOUR_PROJECT",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

### 3. Apply Firebase Security Rules

In Firebase Console → Realtime Database → Rules, paste the contents of `firebase-rules.json`.

### 4. Deploy

**Option A – Any Web Host (Netlify, Vercel, Firebase Hosting):**
Upload all files maintaining this structure:
```
hisabika/
├── index.html         ← Main app (single file)
├── manifest.json      ← PWA manifest
├── service-worker.js  ← Offline support
├── firebase-rules.json
├── icons/
│   ├── favicon.ico
│   ├── favicon.png
│   ├── logo.svg
│   ├── logo-48.png
│   ├── logo-72.png
│   ├── logo-96.png
│   ├── logo-144.png
│   ├── logo-192.png
│   ├── logo-512.png
│   └── logo-1024.png
└── screenshots/
    ├── screen1.png … screen8.png
```

**Option B – Firebase Hosting (Recommended):**
```bash
npm install -g firebase-tools
firebase login
firebase init hosting
# Set public directory to: hisabika/
firebase deploy
```

**Option C – Local Test:**
```bash
# Python
python3 -m http.server 8080
# Then visit: http://localhost:8080
```

---

## 📱 PWA / Android TWA Conversion

### Install as PWA:
- Open the app in Chrome on Android
- Tap "Add to Home Screen" or use the install banner

### Convert to Android TWA (Trusted Web Activity):
1. Install [Bubblewrap](https://github.com/GoogleChromeLabs/bubblewrap):
   ```bash
   npm install -g @bubblewrap/cli
   bubblewrap init --manifest https://your-domain.com/manifest.json
   bubblewrap build
   ```
2. Sign the APK and upload to Google Play Store

---

## 🗂️ App Modules

| Module | Features |
|--------|----------|
| **Dashboard** | Sales overview, stats, quick actions, recent invoices |
| **Invoices** | Create, edit, delete, PDF export, status tracking |
| **Customers** | Add, edit, delete, due tracking, search |
| **Products** | Catalog, pricing, stock tracking, categories |
| **Expenses** | Track, categorize, monthly reports |
| **Reports** | Daily/Weekly/Monthly/Yearly, PDF export |
| **Settings** | Profile, dark mode, backup/restore |

---

## 🎨 Design Specs

- **Framework:** Vanilla JS + CSS (no dependencies except Firebase & jsPDF)
- **Design System:** Material Design 3 inspired
- **Fonts:** Inter + Poppins (Google Fonts)
- **Icons:** Material Icons Round
- **Theme:** Light + Dark mode
- **Layout:** Mobile-first, responsive

---

## 🔐 Security

- Firebase Auth (Email/Password only)
- Per-user data isolation via Firebase Rules
- No data shared between users
- HTTPS enforced via Firebase Hosting / any SSL host

---

## 📦 Tech Stack

| Library | Version | Purpose |
|---------|---------|---------|
| Firebase | 10.7.1 | Auth + Database |
| jsPDF | 2.5.1 | PDF generation |
| jsPDF-AutoTable | 3.7.0 | Table in PDF |
| Material Icons | Latest | UI Icons |
| Inter/Poppins | Latest | Typography |

---

## 📸 Play Store Screenshots

8 screenshots at 1240×2208 px ready in `/screenshots/`:
1. Dashboard Overview
2. Invoice Creation
3. Customer Management
4. Product Management
5. Expense Tracking
6. Reports & Analytics
7. Dark Mode Interface
8. Business Profile & Settings

---

## 🛠️ Customization

### Change Currency Symbol
Search for `₹` in `index.html` and replace with your currency symbol.

### Change Business Language
Update placeholder text in form inputs and labels.

### Add More Expense Categories
Find the `exp-category` select in index.html and add `<option>` tags.

---

## 📄 License

Developed by **Trishab Online Service**  
All rights reserved © 2026

---

*Hisabika – Simple Billing, Smart Business*
