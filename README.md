# 📁 OFile

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-informational?style=flat-square&logo=linux&logoColor=white&color=0a0c10"/>
  <img src="https://img.shields.io/badge/Category-OForensics%20%2F%20File%20Integrity-cyan?style=flat-square"/>
  <img src="https://img.shields.io/badge/Dependencies-None%20(Standalone)-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-v1.2-cyan?style=flat-square"/>
</p>

> **OFile** is a file integrity and forensic timeline tool. It performs MACB analysis, hash baseline comparison, SUID/SGID hunting, and detects recent changes on critical system paths.

**Requires root privileges** for full forensic scanning.

---

## 📌 Overview

OFile helps investigators monitor file system integrity by comparing current state (hashes + MACB timestamps) against a saved baseline. It also detects privilege escalation vectors (SUID/SGID) and recent modifications.

---

## 🖥️ Modules

| # | Module                        | Description |
|---|-------------------------------|-------------|
| **[1]** | **Integrity Audit**           | Hash + MACB comparison vs baseline |
| **[2]** | **SUID/SGID Hunter**          | Find privilege escalation binaries |
| **[3]** | **Recent Timeline**           | Files modified in last N days |
| **[4]** | **Save/Update Baseline**      | Create or refresh hash + MACB database |

---

## 📊 Key Features

- **MACB + Hash Baseline** — Tracks Modified, Accessed, Changed, Birth times + SHA256 hashes
- **SUID/SGID Detection** — Identifies risky setuid/setgid binaries
- **Recent Changes Timeline** — Shows files modified in the last 7 days (configurable)
- **Forensic Audit Logging** — All operations logged to `ofile_forensic.log`
- **Baseline Management** — Persistent JSON baseline for change detection
- **Critical Path Scanning** — Focuses on `/bin`, `/sbin`, `/etc`, `/usr/bin`, etc.
- **Safe Mode** — Clear forensic warnings before scanning

---

## ⚙️ Requirements

- **Linux** (recommended)
- **Root privileges** (required for full access to system files)
- **No additional Python dependencies**

---

## 🚀 Usage

```bash
sudo ./OFile

📁 Output

Integrity Report — Files with changed hash or MACB timestamps
SUID/SGID List — Risky binaries with permissions and owner
Recent Timeline — Chronological list of modified files
Baseline Database — baseline_hashes_macb.json with hashes + MACB times
Forensic Log — ofile_forensic.log for audit trail


📦 Part of OwlSec Toolkit
This tool is part of the OwlSec suite — a collection of 300+ security and privacy tools.
🔗 owlsec.org

©️ License
Proprietary — © Khaled S. Haddad
Tools are distributed as pre-built executables. Source code is proprietary.

AUTHORISED FORENSIC FILE INTEGRITY ANALYSIS USE ONLY
