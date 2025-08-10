# 🌌 Eremos — Autonomous Swarm Agents for Early On-Chain Signal Detection

![Eremos Banner](docs/banner2.png)

<p align="center">
  <img src="https://img.shields.io/github/stars/EremosCore/Eremos?style=for-the-badge" alt="Stars"/>
  <img src="https://img.shields.io/github/forks/EremosCore/Eremos?style=for-the-badge" alt="Forks"/>
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white"/>
  <img src="https://img.shields.io/badge/Solana-9945FF?style=for-the-badge&logo=solana&logoColor=white"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge"/>
</p>

---

Eremos is a **modular framework** for deploying autonomous “swarm agents” that monitor on-chain activity across the Solana ecosystem.

Each agent runs independently — observing **funding flows, bundling behavior, deploy patterns**, and surfacing early on-chain signals **before they’re obvious**.

💛 Built as a **public good**, Eremos enhances transparency & insight for developers, researchers, and analysts.

---

## ✨ Features

- **🧩 Modular Agents** — Scoped logic for detecting wallet activity, contract spawns, anomalies
- **📡 Signal Emission** — Structured signals for logging, alerting, or downstream use
- **🦾 Swarm Design** — Each agent operates independently with shared utilities
- **⚙️ Extensible Core** — Plug in watchers, inference layers, or custom triggers
- **🕵️ Launch Wallet Detection** — Trace freshly funded wallets & monitor deploys in real time
- **👻 Ghost Watcher** — Detect dormant wallets suddenly becoming active

---

## 🏗️ Architecture

![Architecture Diagram](docs/architecture.png)

> *RPC Watcher feeds the Agent Core, which connects to both a Signal Processor (that triggers Alerts/Logs/API) and customizable Agent Logic — mirroring the diagram layout shown above.*

---

## 🛠 Project Structure

Eremos/
├── agents/ # Agent templates + detection logic
├── utils/ # Shared logging & signal utilities
├── types/ # TypeScript definitions & interfaces
├── scripts/ # Bootstrap & developer scripts
├── docs/ # Architecture diagrams, artwork, whitepaper
└── .env.example # Environment variable template

text

---

## 📊 Example Signal

[agent-observer] → fresh funding detected from kraken (wallet: 6Yxk...P2M8) at 04:41:12Z
[agent-observer] → contract probing detected within 4s (pump.fun interaction traced)
[agent-observer] → token created at 04:41:17Z (tx: 5gW...pump)
[agent-observer] → 5 bundle-linked wallets interacted within 8s of deploy
[agent-observer] → launch confidence spike (0.91) - emitting signal (elapsed: 13s)

{
agent: "Observer",
type: "launch_detected",
glyph: "Δ",
hash: "sig_c7f9a3d2bc",
timestamp: "2025-06-12T04:41:25Z",
source: "agent-observer",
confidence: 0.91
}

text

---

## 📈 Signal Confidence

Each emitted signal includes a confidence score (`0–1`) based on behavioral heuristics:

- CEX-origin funding (e.g., Kraken, Coinbase)
- Time between funding → deploy
- Wallet linkage density (bundled activity)
- Token metadata validation

Confidence is computed agent-side and logged with the signal.

---

## 🧰 Tech Stack

| Layer         | Technology                |
|---------------|--------------------------|
| Frontend      | Next.js, Tailwind CSS    |
| Backend       | Node.js (TypeScript)     |
| Chain Layer   | Solana RPC/live watchers |
| Language      | TypeScript               |

---

## 🚀 Getting Started

### ✅ Prerequisites

- Node.js **v18+**
- npm or yarn
- Solana RPC endpoint (free from Helius, QuickNode, etc.)

### 📦 Installation

git clone https://github.com/EremosCore/Eremos.git
cd Eremos
npm install

text

### ⚙️ Setup

cp .env.example .env.local

Add your RPC URL + configuration in .env.local
text

### ▶️ Run an Agent

npm run dev

text
You should see logs from Agent-000 as it begins monitoring.

---

## 🤝 Contributing

We welcome all contributors!

- Star ⭐ and Watch 👀 the repo
- Fork the repository
- Create a feature branch

git checkout -b feature/my-improvement

text

Make your changes (follow Prettier formatting), then:

git commit -m "feat: improve docs"
git push

text
Open a Pull Request!

📌 See [CONTRIBUTING.md](CONTRIBUTING.md) for more.

---

## 📜 License

MIT © Eremos LLC

---

## 🔗 Links

- Twitter/X: [@EremosCore](https://x.com/EremosCore)
- Website: [eremos.io](https://www.eremos.io)
- Whitepaper: [v1.0 PDF](docs/whitepaper.pdf)

---

## ❓ FAQ

**Q: How do I run an Eremos agent locally?**  
A: After cloning the repo and installing dependencies, run `npm run dev` to start the agent in development mode.

**Q: Which Solana RPC providers work?**  
A: You can use public endpoints from providers like Helius, QuickNode, or set your own in `.env.local`.

**Q: What is the architecture diagram in this README?**  
A: It shows how RPC Watcher, Agent Core, Signal Processor, and Alerts/Logs/API connect for signal detection.

**Q: Who do I contact for questions?**  
A: Feel free to open an issue in this repo or reach out on [Twitter](https://x.com/EremosCore).

---
