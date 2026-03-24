# SMTEC Portal

A web-based portal for SMTEC with role-based access for staff, admin, and developers. Built with HTML, CSS, JavaScript, and Firebase.

## Project Structure

```
SMTEC_Portal/
├── login.html          # Login page (entry point)
├── staff.html          # Staff dashboard
├── admin.html          # Admin dashboard
├── developer.html      # Developer dashboard
├── firebase-config.js  # Firebase configuration (⚠️ not committed — see setup)
└── README.md
```

## Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/SMTEC_Portal.git
   cd SMTEC_Portal
   ```

2. **Create your Firebase config file**

   Create `firebase-config.js` in the project root with your Firebase credentials:
   ```javascript
   import { initializeApp } from "https://www.gstatic.com/firebasejs/10.9.0/firebase-app.js";
   import { getAuth } from "https://www.gstatic.com/firebasejs/10.9.0/firebase-auth.js";
   import { getDatabase } from "https://www.gstatic.com/firebasejs/10.9.0/firebase-database.js";
   import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.9.0/firebase-analytics.js";

   const firebaseConfig = {
     apiKey: "YOUR_API_KEY",
     authDomain: "YOUR_PROJECT.firebaseapp.com",
     databaseURL: "https://YOUR_PROJECT-default-rtdb.YOUR_REGION.firebasedatabase.app",
     projectId: "YOUR_PROJECT_ID",
     storageBucket: "YOUR_PROJECT.firebasestorage.app",
     messagingSenderId: "YOUR_SENDER_ID",
     appId: "YOUR_APP_ID",
     measurementId: "YOUR_MEASUREMENT_ID"
   };

   const app = initializeApp(firebaseConfig);
   export const auth = getAuth(app);
   export const db = getDatabase(app);
   try { getAnalytics(app); } catch(e) {}
   ```

   > ⚠️ **Never commit `firebase-config.js` to version control.** It is listed in `.gitignore`.

3. **Open `login.html`** in your browser to start the portal.

## Deployment

You can host this project on:
- **GitHub Pages** — push to a `gh-pages` branch (note: `firebase-config.js` must be set via environment or injected at deploy time)
- **Firebase Hosting** — run `firebase deploy`
- **Any static web server**

## Tech Stack

- HTML5 / CSS3 / JavaScript (ES Modules)
- Firebase Authentication
- Firebase Realtime Database
- Firebase Analytics
