<!-- Banner / header -->
<p align="center">
  <img src="assets/banner.png" width="100%" alt="Red Team & Malware Development" />
</p>

<h1 align="center">⚔️ Red Team & Malware Development Lab</h1>

<p align="center">
  <a href="https://github.com/<YOUR-USER>"><img src="https://img.shields.io/github/followers/<YOUR-USER>?style=social" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-BSD%203--Clause-blue.svg" /></a>
  <img src="https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-222222" />
  <img src="https://img.shields.io/badge/status-ongoing-orange" />
</p>

> **⚠️ Legal notice**  
> All code and research in this repository are provided **strictly for educational and authorized-testing purposes**.  
> Misuse can lead to severe criminal penalties. By cloning or using any part of this repo, you agree to use it **only** in environments where you have explicit written permission.

---

## 📜 Table of Contents
1. [About the Lab](#about-the-lab)
2. [Key Projects](#key-projects)
3. [Quick Start](#quick-start)
4. [Directory Layout](#directory-layout)
5. [Research & Write-Ups](#research--write-ups)
6. [Contributing](#contributing)
7. [Roadmap](#roadmap)
8. [License](#license)

---

## About the Lab

This repo is my personal playground for:

* Reverse-engineering Windows internals (NT, PEB/TEB, ntdll syscalls)
* Custom C/C++ loaders with **Hell’s Gate**, **Heaven’s Gate**, and hybrid techniques
* Offensive tooling in Rust, Go, and Python (C2 stagers, reflective DLLs, BOFs)
* Linux user-land implants (ptrace, eBPF) and kernel rootkits
* Bypassing modern EDRs & ETW, obfuscation, and sandbox evasion
* Automation scripts for purple-team lab setups (Terraform, Ansible)

I document trade-offs, detection artifacts, and blue-team countermeasures alongside each tool to encourage *defense-driven* offense.

---

## Key Projects

| Folder | Language | Description |
|--------|----------|-------------|
| **`SyscallLoader`** | C++ / ASM | Inline-assembly syscall loader using Hell’s Gate + hash-based resolution. |
| **`RustBeacon`** | Rust | Minimal Beacon Object File (BOF) re-implementation in Rust. |
| **`PythonC2`** | Python | Asyncio-based C2 server supporting encrypted WebSocket channels. |
| **`KernelHide`** | C | Proof-of-concept LKM rootkit: process hiding + TCP port knock. |
| **`AVEscape`**  | Go | Sandbox/VM fingerprint toolkit & EDR anti-debug tricks. |

> *See the [`/projects`](projects/) folder for the full list.*

---

## Quick Start

```bash
# clone with submodules (for third-party libs)
git clone --recurse-submodules https://github.com/<YOUR-USER>/redteam-lab.git
cd redteam-lab

# build Windows tools (MSVC, x64)
cmake -S SyscallLoader -B build && cmake --build build --config Release

# run local C2 (Python ≥3.11)
cd PythonC2 && pip install -r requirements.txt && python main.py

# compile Rust BOF
cd RustBeacon && cargo build --release
