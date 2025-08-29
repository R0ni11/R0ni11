# 🧩 R0n1n

**Red Team Operator · Malware R\&D · Adversary Emulation**

<p align="center">
  <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExZWR1OHU5NzdncGRidjE5ZzMyYzZvYnl3cWlrbTA3bTZ1MHBvZ2hvbCZlcD12MV9naWZzX3NlYXJjaCZjdD1n/gGC6a1N8Vd0uW/giphy.gif" width="400" alt="Johan Liebert">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Focus-Adversary%20Emulation-informational" />
  <img src="https://img.shields.io/badge/Domains-Windows%20Internals%20%7C%20EDR%20Evasion%20%7C%20Transports-9cf" />
  <img src="https://img.shields.io/badge/Languages-Python%20%7C%20Go%20%7C%20Rust%20%7C%20C%2FC%2B%2B-blue" />
  <img src="https://img.shields.io/badge/Ethics-Authorized%20Use%20Only-success" />
</p>

---

### TL;DR

* Red Team operator building **offensive security research tooling** for **authorized** environments.
* Interests: **implant design**, **C2 transports**, **opsec**, **artifact minimization**, **post‑ex**, **telemetry shaping**.
* I ship small, composable tools and document trade‑offs.

### ⚗️ Selected Research / Tools

> Swap in your repo links when ready.

* **Operator Lab** — Private repo of PoCs for transport, staging, and OPSEC experiments.
* **WS Relay** — WebSocket man‑in‑the‑middle for testing auth/session edge cases.
* **Distributed Scanner** — RabbitMQ‑backed fan‑out scan framework (workers 1..N).
* **C2 Sandbox** — Modular C2 research playground (protocol adapters & handlers).

### 🧠 Design Snapshot

```mermaid
flowchart LR
  subgraph Operator
    UI[CLI/Console]
  end
  subgraph C2Core[C2 Core]
    TA[Task API]
    TP[Transport Abstraction]
    ST[Stagers]
    LM[Logging/Telemetry]
  end
  subgraph Transports
    HT[HTTP/2]
    WS[WebSocket]
    GR[gRPC/TLS]
    DOH[DoH]
  end
  subgraph Agents[Agents]
    AG1[Minimal Beacon]
    AG2[Interactive Agent]
  end

  UI --> TA
  TA --> TP
  TP --> HT
  TP --> WS
  TP --> GR
  TP --> DOH
  ST --> AG1
  ST --> AG2
  AG1 --> TA
  AG2 --> TA
  LM -. observability .- TA
```

### 🛠️ Stack

* **Langs:** Python, Go, Rust, C/C++
* **Infra:** Docker, RabbitMQ, Redis, SQLite/Postgres
* **Targets:** Windows & Linux (userland), containers, cloud endpoints
* **Tooling:** Git, Make/CMake, Poetry/Pipenv, clang, llvm, cmocka

### 📎 Notes on Use

* Research intended for **defensive improvement** and **adversary emulation** in scoped, lawful tests.
* All code: **for authorized security assessments only**. No warranties.
* I practice **operational hygiene**: minimize footprint, isolate risk, and document assumptions.

### 🔐 Trust & Contact

* **PGP:** *add fingerprint*
* **Secure contact:** *add channel (e.g., Matrix, Proton)*
* **Collab:** Open to research collabs w/ clear scope.

### 📌 Quick Start (Profile README)

This file should live at `github.com/<your‑username>/<your‑username>` so it renders on your profile. Pin 3–6 repos for visibility.

---

<sub>Badges are via shields.io. Replace placeholders when your repos go public.</sub>
