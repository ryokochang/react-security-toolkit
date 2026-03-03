# 🔐 React Security Toolkit

![React](https://img.shields.io/badge/React-18-61DAFB?style=flat&logo=react&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-20-6EBF20?style=flat&logo=node.js&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-5-646CFF?style=flat&logo=vite&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green?style=flat)

A browser-based **cybersecurity toolkit** built with React and TypeScript. Provides developers and security professionals with a collection of essential tools for analyzing, decoding, and testing security-related data — all running client-side with no data ever leaving your browser.

> 🎓 Built as a hands-on learning project alongside my **Bachelor's in Cybersecurity & Data Governance** (PUC Minas).

---

## 🧰 Tools Included

### 🔑 JWT Inspector
- Decode JWT tokens (header, payload, signature)
- Highlight expiration, issuer, subject fields
- Detect common JWT vulnerabilities (none algorithm, expired tokens, weak secrets)
- Supports RS256, HS256, and other common algorithms

### 🔒 Password Strength Analyzer
- Real-time entropy calculation
- Pattern detection (dictionary words, keyboard sequences, repeated chars)
- NIST-compliant strength scoring
- Suggestions for improvement
- Estimated brute-force crack time

### #️⃣ Hash Generator & Verifier
- Generate MD5, SHA-1, SHA-256, SHA-512 hashes
- Compare hashes for file/text integrity verification
- Side-by-side input/output display

### 🌐 HTTP Security Headers Checker
- Inspect security headers from any URL via proxy
- Check for: `Content-Security-Policy`, `X-Frame-Options`, `Strict-Transport-Security`, `X-Content-Type-Options`, and more
- Grade each header with pass/warn/fail status
- Export report as JSON

### 🔡 Encoding / Decoding Tools
- Base64 encode/decode
- URL encode/decode
- HTML entity encode/decode
- Hex converter

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 18, TypeScript, Vite |
| UI | Ant Design, CSS Modules |
| Crypto | Web Crypto API, crypto-js |
| HTTP Proxy | Node.js + Express (header checker backend) |
| Testing | Vitest, React Testing Library |
| Build | Vite, ESBuild |

---

## 📁 Project Structure

```
react-security-toolkit/
├── src/
│   ├── components/
│   │   ├── Layout/
│   │   │   └── AppLayout.tsx
│   │   └── shared/
│   │       ├── CopyButton.tsx
│   │       └── StatusBadge.tsx
│   ├── tools/
│   │   ├── JwtInspector/
│   │   │   ├── JwtInspector.tsx
│   │   │   ├── JwtDecoder.ts
│   │   │   └── JwtInspector.test.ts
│   │   ├── PasswordAnalyzer/
│   │   │   ├── PasswordAnalyzer.tsx
│   │   │   ├── entropyCalculator.ts
│   │   │   └── PasswordAnalyzer.test.ts
│   │   ├── HashGenerator/
│   │   │   ├── HashGenerator.tsx
│   │   │   └── hashUtils.ts
│   │   ├── HeadersChecker/
│   │   │   ├── HeadersChecker.tsx
│   │   │   └── headerRules.ts
│   │   └── EncodingTools/
│   │       ├── EncodingTools.tsx
│   │       └── encoders.ts
│   ├── utils/
│   │   └── clipboard.ts
│   ├── types/
│   │   └── index.ts
│   ├── App.tsx
│   └── main.tsx
├── server/                   # Header checker proxy (Node.js)
│   ├── src/
│   │   ├── routes/headers.ts
│   │   └── index.ts
│   └── package.json
├── vite.config.ts
├── tsconfig.json
└── package.json
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js 20+
- npm or yarn

### Installation

```bash
# Clone the repository
git clone https://github.com/ryokochang/react-security-toolkit.git
cd react-security-toolkit

# Install frontend dependencies
npm install

# Install server dependencies (for Headers Checker)
cd server && npm install && cd ..
```

### Running Locally

```bash
# Start the React app
npm run dev

# Start the header proxy server (optional, for Headers Checker tool)
cd server && npm run dev
```

App available at **http://localhost:5173**

---

## 🔍 Usage Examples

### JWT Inspector

```
Input:
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiJ1c2VyXzEyMyIsInJvbGUiOiJhZG1pbiIsImlhdCI6MTcwMDAwMDAwMCwiZXhwIjoxNzAwMDAwOTAwfQ.SIGNATURE

Output:
Header:  { alg: "HS256", typ: "JWT" }
Payload: { sub: "user_123", role: "admin", iat: ..., exp: ... }
Status:  ⚠️ TOKEN EXPIRED
```

### Password Analyzer

```
Input:   "p@ssword123"
Entropy: 42.3 bits
Score:   Weak (2/5)
Issues:  Contains dictionary word "password"
         Sequential numbers detected
Crack:   ~3 hours (GPU brute force)
```

---

## 🧪 Running Tests

```bash
# Run all tests
npm test

# Watch mode
npm run test:watch

# Coverage
npm run test:coverage
```

---

## 🔒 Privacy

All tools run **100% client-side** in the browser. No data is sent to any server (except the optional header checker proxy which only fetches HTTP headers from the target URL, never your input data).

---

## 🗺️ Roadmap

- [ ] SSL/TLS certificate inspector
- [ ] CIDR / IP range calculator
- [ ] Regex tester with security patterns
- [ ] CORS policy analyzer
- [ ] Clickjacking vulnerability tester (iframe sandbox)
- [ ] Subdomain enumeration helper

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

<p align="center">Built with ❤️ by <a href="https://github.com/ryokochang">Alex Chang</a> | Learning Cybersecurity one tool at a time 🔐</p>
