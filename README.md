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

```mermaid
graph TD
    A[RPC Watcher] --> B[Agent Core]
    B --> C[Signal Processor]
    C --> D[Alerts / Logs / API]
    B --> E[Custom Agent Logic]
