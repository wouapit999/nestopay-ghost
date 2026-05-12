# Nestopay Ghost Edition 👻

> **Cross-border mobile money transfers for the global diaspora.**  
> Rebuilt to outperform Tap Tap Send — zero fees, 60s settlement, live tracking, tiered KYC, referral engine, and full Web PWA.

[![Deploy](https://img.shields.io/badge/GitHub%20Pages-Live-00E896?style=flat-square&logo=github)](https://YOUR-USERNAME.github.io/nestopay-ghost)
[![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](LICENSE)
[![Version](https://img.shields.io/badge/Version-Ghost%201.0-00E896?style=flat-square)](#)

---

## 🗂 Project Structure

```
nestopay-ghost/
├── index.html               ← Full app (single-file PWA)
├── manifest.json            ← PWA install manifest
├── sw.js                    ← Service worker (offline support)
├── .github/
│   └── workflows/
│       └── deploy.yml       ← Auto-deploy to GitHub Pages on push
├── docs/
│   └── IMPROVEMENTS.md      ← Competitive analysis vs Tap Tap Send
├── .gitignore
├── LICENSE
└── README.md
```

---

## ✨ Features vs Tap Tap Send

| Feature | Nestopay Ghost | Tap Tap Send |
|---|---|---|
| Zero fees (5 corridors) | ✅ SN, CI, GH, GN, ML | ✅ Major routes only |
| Web app (no install needed) | ✅ Full PWA | ❌ App-only |
| WhatsApp bot | ✅ | ❌ |
| 30-min cancellation | ✅ All markets | ⚠️ US only |
| Live transfer tracking | ✅ Real-time state machine | ⚠️ Basic |
| Rate comparison vs competitors | ✅ Live on send screen | ❌ |
| Tiered KYC (90s Tier 1) | ✅ | ⚠️ Slow verification |
| Referral programme | ✅ €10/friend | ❌ |
| B2B / API licensing | ✅ | ❌ |
| Francophone Africa focus | ✅ Core strategy | ❌ |
| Pluggable operator APIs | ✅ New operator in 4–6h | ❌ |
| Customer support SLA | ✅ <4hr target | ❌ (top complaint) |

---

## 🚀 Quick Deploy to GitHub Pages (5 minutes)

### Step 1 — Fork or create the repo

**Option A — Use this repo directly:**
```bash
git clone https://github.com/YOUR-USERNAME/nestopay-ghost.git
cd nestopay-ghost
```

**Option B — Start fresh:**
```bash
mkdir nestopay-ghost && cd nestopay-ghost
git init
git branch -M main
```

### Step 2 — Add the files

Copy all files from this package into your local folder. Verify:
```bash
ls -la
# Should show: index.html  manifest.json  sw.js  .github/  docs/  README.md
```

### Step 3 — Push to GitHub

```bash
git add .
git commit -m "feat: Nestopay Ghost Edition initial deploy"
git remote add origin https://github.com/YOUR-USERNAME/nestopay-ghost.git
git push -u origin main
```

### Step 4 — Enable GitHub Pages

1. Go to your repo on GitHub
2. Click **Settings** → **Pages** (left sidebar)
3. Under **Source**, select **GitHub Actions**
4. Click **Save**

GitHub will automatically run the `deploy.yml` workflow on every push to `main`.

### Step 5 — Your live URL

Within ~60 seconds your app is live at:
```
https://YOUR-USERNAME.github.io/nestopay-ghost
```

---

## 🛠 Local Development

No build tools required. Pure HTML/CSS/JS.

```bash
# Option 1 — Python (built-in)
python3 -m http.server 8080
# Open http://localhost:8080

# Option 2 — Node.js
npx serve .
# Open http://localhost:3000

# Option 3 — VS Code
# Install "Live Server" extension → right-click index.html → Open with Live Server
```

---

## 📱 Install as PWA

Once deployed, users can install Nestopay Ghost as a native app:

- **Chrome/Edge (desktop):** Click the install icon in the address bar
- **Android Chrome:** Tap the "Add to Home Screen" banner or browser menu
- **iOS Safari:** Tap Share → "Add to Home Screen"

The service worker (`sw.js`) caches the app for offline use — critical for low-connectivity corridors in West Africa.

---

## 🌍 Supported Corridors

| Flag | Country | Operator | Fee | Status |
|------|---------|----------|-----|--------|
| 🇸🇳 | Senegal | Orange Money | **FREE** | Live |
| 🇨🇮 | Côte d'Ivoire | Orange CI | **FREE** | Live |
| 🇬🇭 | Ghana | MTN MoMo | **FREE** | Live |
| 🇬🇳 | Guinea | Wave | **FREE** | Live |
| 🇲🇱 | Mali | Wave | **FREE** | Live |
| 🇳🇬 | Nigeria | First Bank | 1.2% | Live |
| 🇸🇱 | Sierra Leone | Africell | 1.2% | Live |
| 🇬🇲 | Gambia | Wave | 1.2% | Live |
| 🇰🇪 | Kenya | M-Pesa | 1.2% | Beta |

Adding a new operator: `one folder + 3 env variables. Core platform never changes.`

---

## 🔧 Customisation

All configuration lives at the top of `index.html` inside the `<script>` block:

```js
// FX rates (replace with live API call in production)
const FX_RATES = {
  XOF: 655.2,   // Senegal / CI / Mali / Guinea
  GHS: 15.24,   // Ghana
  NGN: 1620,    // Nigeria
  // ...
};

// Zero-fee corridors
const FREE_CORRIDORS = ['SN', 'CI', 'GH', 'GN', 'ML'];

// Referral reward amount (EUR)
const REFERRAL_REWARD = 10;
```

---

## 🏗 Production Upgrade Path

This Ghost Edition is a **high-fidelity frontend prototype**. To productionise:

| Layer | Recommended stack |
|---|---|
| Backend API | Node.js / TypeScript (see technical docs) |
| Database | Supabase (PostgreSQL) |
| Auth | JWT RS256 + Twilio OTP |
| KYC | Sumsub |
| AML | ComplyAdvantage |
| FX rates | Open Exchange Rates API |
| Hosting | Railway / Render (backend) + GitHub Pages / Vercel (frontend) |
| CI/CD | GitHub Actions (already configured) |

Full technical architecture is documented in `docs/IMPROVEMENTS.md`.

---

## 📄 License

MIT — free to use, fork, and build on.

---

## 👥 Team

Built by **Bouquet Innovation** — [support@bouquet-innovation.net](mailto:support@bouquet-innovation.net) | [nestopay.com](https://nestopay.com)

*We are diaspora. We've paid the fees. We've waited for the transfers. We built the solution.*
