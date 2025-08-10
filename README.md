# Eremos

![Eremos Banner](docs/banner2.png)

![License](https://img.shields.io/github/license/EremosCore/Eremos)
![GitHub Repo stars](https://img.shields.io/github/stars/EremosCore/Eremos?style=social)
![GitHub forks](https://img.shields.io/github/forks/EremosCore/Eremos?style=social)
![GitHub last commit](https://img.shields.io/github/last-commit/EremosCore/Eremos)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)
![Built for Solana](https://img.shields.io/badge/Built%20for-Solana-purple)

---

**Autonomous swarm agents for early on-chain signal detection**

Eremos is a **lightweight, modular framework** for deploying agents that monitor blockchain activity — tracking wallet clusters, mint patterns, and contract anomalies.  
Designed for developers who want **low-noise, early signals** integrated into their workflows.

---

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Example Signal](#example-signal)
- [Signal Confidence](#signal-confidence)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Key Folders](#key-folders)
- [Contributing](#contributing)
- [License](#license)
- [Links](#links)

---

## Overview

<p align="center">
  <img src="docs/therontphd2.png" alt="Agent Theron" width="155"/><br/>
  <em>Theron - Agent (000)</em>
</p>

**Meet Theron — Agent-000**  
*The first deployed agent in the swarm. Passive. Pattern-sensitive. Modular and extendable by design.*

**Agent-001 Coming Soon** → [Teaser](https://x.com/EremosCore/status/1949154939923833239)

---

## Features

- **Modular Agents** — Scoped logic for detecting wallet activity, contract spawns, and anomalies  
- **Signal Emission** — Structured outputs for logging, alerting, or downstream integration  
- **Swarm Design** — Agents operate independently but share core utilities  
- **Extensible Core** — Easily add watchers, inference layers, or triggers  
- **Minimal Output** — Log only high-value signals  
- **Launch Wallet Detection** — Trace newly funded wallets and flag high-confidence deploys in real time  
- **Ghost Watcher** — Monitor dormant wallets that suddenly reactivate  

---

## Architecture

![Architecture Diagram](docs/architecture.png)

*RPC Watcher feeds the Agent Core, which connects to both a Signal Processor (that triggers Alerts/Logs/API) and customizable Agent Logic — mirroring the image you want to display.*

---

## Example Signal

[Agent-000] 🚦 Funding detected
Wallet: 9W7...KpT2 at 03:57:24Z

[Agent-000] 🪙 Contract deployed 6s after funding
Tx: 3he...8vGQ

[Agent-000] 🤝 Linked wallet bundle observed
Confidence: 0.92 — SIGNAL EMITTED

text

**JSON example:**
{
"agent": "Agent-000",
"type": "launch_detected",
"glyph": "Δ",
"hash": "sig_xxx",
"timestamp": "2025-07-10T03:57:30Z",
"confidence": 0.92
}

text

---

## Signal Confidence

Signals are scored according to:
- **Funding Timing:** Large CEX → deploy gap (sec)
- **Wallet Bundling:** Dense txs between related wallets
- **Onchain Flags:** Mint patterns, meta-checks
- **Dormancy:** Reactivation after long inactivity

Confidence scores: `0.0` (noisy) → `1.0` (strong signal)

---

## Tech Stack

| Layer         | Technology             |
|---------------|-----------------------|
| Frontend      | Next.js, Tailwind CSS |
| Backend       | Node.js (TypeScript)  |
| Chain Access  | Solana RPC/watchers   |
| Language      | TypeScript            |

---

## Getting Started

### Prerequisites
- Node.js **v18+**
- npm or yarn
- Solana RPC endpoint ([Helius](https://www.helius.dev/) / [QuickNode](https://www.quicknode.com/))

### Clone & Install
git clone https://github.com/EremosCore/Eremos.git
cd Eremos
npm install

text

### Start Development
npm run dev

text
Or run agents individually:
node agents/theron.js

text

---

## Key Folders

/agents 📡 Agent logic & templates
/utils 🛠 Shared utilities
/types 🗂 TypeScript type definitions
/scripts ⚙️ Dev scripts and setup
/docs 📖 Whitepaper, diagrams, onboarding

text

---

## Contributing

Pull requests are welcome! See [CONTRIBUTING.md](CONTRIBUTING.md).

- Fork the repo, create a branch (`feature/my-update`)
- Make improvements—README, docs, code, onboarding
- Push and open a PR (describe your changes)

Please star ⭐ and watch 👀 the repo!

---

## License

MIT © EremosCore  
See [LICENSE](LICENSE) for full terms.

---

## Links

- [GitHub](https://github.com/EremosCore/Eremos)
- [Website](https://www.eremos.io/)
- [Twitter](https://x.com/EremosCore)
- [Superteam Earn Bounty](https://earn.superteam.fun/)

---
