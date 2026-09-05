# AI Scam Shield — Proactive Threat Intelligence & Social Engineering Defense

[![TypeScript](https://img.shields.io/badge/TypeScript-5.8-blue.svg)](https://www.typescriptlang.org/)
[![React](https://img.shields.io/badge/React-19.0-61dafb.svg)](https://react.dev/)
[![Tailwind CSS](https://img.shields.io/badge/TailwindCSS-4.1-38b2ac.svg)](https://tailwindcss.com/)
[![Express](https://img.shields.io/badge/Express-4.21-lightgrey.svg)](https://expressjs.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

**AI Scam Shield** is a cybersecurity intelligence and threat prevention web application engineered to detect, analyze, and intercept phishing attempts, social engineering attacks, deceptive SMS/WhatsApp alerts, and malicious links in real-time.

Powered by a hybrid multi-pattern heuristic engine and Google Gemini AI explainability, it breaks down the psychological manipulation levers used by attackers and provides actionable safety countermeasures.

---

## ✨ Features

- 🔍 **AI Message Analyzer**:
  - Instant heuristic pattern matching for Phishing, Fake KYC, UPI fraud, Telegram job scams, Lottery lures, and Electricity cutoff extortion.
  - Generates a **0–100 Risk Score**, threat category, and identified red flags.
  - **Deep AI Explainability** powered by Google Gemini (identifies psychological manipulation levers like Urgency, Fear, Authority, and Greed).
  - Recipient verification checklist tailored to the detected attack vector.

- 🌐 **Secure URL & Domain Scanner**:
  - Inspects suspicious links for domain impersonation, high-risk TLDs (`.xyz`, `.top`, `.tk`, `.click`), excessive subdomains, and protocol vulnerabilities (HTTP vs HTTPS).
  - Warns against credential harvesting and fraudulent redirect vectors.

- 📊 **Community Threat Intelligence Dashboard**:
  - Live community-driven threat matrix displaying recently identified scams, attacker identifiers (phone numbers, email addresses, Telegram handles), and severity classifications.
  - Dynamic telemetry metrics tracking total scans, intercepted threats, and system defense scores.

- 🚩 **Decentralized Scam Reporting Portal**:
  - Community reporting form to document and log emerging scam patterns, target payment addresses, and malicious lures.
  - Synchronizes reported threats directly into the shared threat feed.

- 🎨 **Frosted Glass UI**:
  - Cyber-defense theme with deep slate backdrop, ambient gradient glow orbs, frosted glass cards (`backdrop-blur-xl`), responsive touch controls, and WCAG AA contrast.

---

## 🛠️ Tech Stack

- **Frontend**: [React 19](https://react.dev/), [TypeScript](https://www.typescriptlang.org/), [Tailwind CSS v4](https://tailwindcss.com/), [Motion](https://motion.dev/), [Lucide React](https://lucide.dev/)
- **Backend**: [Express.js](https://expressjs.com/), [Node.js](https://nodejs.org/) (ESM + TSX)
- **AI & Intelligence**: [@google/genai SDK](https://www.npmjs.com/package/@google/genai) (Google Gemini 2.5 Flash / Flash-Lite models)
- **Build Tooling**: [Vite 6](https://vitejs.dev/), [esbuild](https://esbuild.github.io/)

---

## 🚀 Getting Started

### Prerequisites

- **Node.js**: `v20.x` or higher
- **npm**: `v9.x` or higher
- *(Optional)* **Gemini API Key**: For deep AI social engineering explainability (the app also works fully offline with the built-in rule heuristics engine).

---

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/ai-scam-shield.git
   cd ai-scam-shield
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure Environment Variables:**
   Copy `.env.example` to `.env`:
   ```bash
   cp .env.example .env
   ```


4. **Start the Development Server:**
   ```bash
   npm run dev
   ```

5. **Open the Application:**
   Visit [http://localhost:3000](http://localhost:3000) in your browser.

---

## 📦 Production Build & Deployment

To compile and bundle both the React frontend and Express backend for production:

```bash
# Build Vite client and bundle server with esbuild
npm run build

# Launch the production server
npm start
```

The server binds to port `3000` (`http://0.0.0.0:3000`).

---

## 📁 Project Structure

```text
├── data/
│   └── reports.json            # Local store for community scam reports
├── src/
│   ├── components/
│   │   ├── AnalyzerView.tsx    # AI SMS/Message analyzer with threat scoring
│   │   ├── DashboardView.tsx   # Live threat matrix and aggregate metrics
│   │   ├── Navbar.tsx          # Frosted glass navigation & system status
│   │   ├── ReportView.tsx      # Community scam incident reporting form
│   │   └── UrlScannerView.tsx  # Link & suspicious domain scanner
│   ├── App.tsx                 # Core application layout & routing state
│   ├── index.css               # Global Tailwind CSS styles
│   └── main.tsx                # Client DOM entry point
├── server.ts                   # Express server & Gemini AI / heuristic analysis API
├── package.json                # Project scripts and dependencies
├── vite.config.ts              # Vite frontend configuration
└── README.md                   # Project documentation
```

---

## 🛡️ API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/analyze` | Analyze text for scam indicators (supports `enable_deep_ai: true`) |
| `POST` | `/api/scan-url` | Scan a URL for spoofing, deceptive subdomains, and risk level |
| `GET` | `/api/dashboard` | Retrieve total scan counts and recent threat reports |
| `POST` | `/api/report` | Submit a new community scam report |
| `GET` | `/api/health` | Health check probe |

---

## 🔒 Privacy & Security

- **Zero Credential Retention**: Message content is analyzed in-memory and is never stored unless explicitly submitted via the community report form.
- **Fail-Safe Heuristics**: The detection engine functions reliably even when offline or without external AI API credentials.
- **Client Safeguards**: All API keys remain isolated on the server side and are never exposed to the client browser.

---

## 🤝 Contributing

Contributions, bug reports, and feature requests are welcome!
1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

