---
title: "Nmap: The Ultimate Recon Field Manual"
date: 2026-01-03 00:00:00 +0000
categories: [Resources, Cheatsheets]
tags: [nmap, recon, scanning, networking]
---

# 🛰️ Nmap Reconnaissance
> **Mission Objective:** Identify live hosts, open ports, and service versions without triggering every IDS in the network.

Nmap (Network Mapper) is the "God-Eye" of offensive security. Whether you are prepping for the **OSCP** or hitting a **HTB Pro Lab**, these are the commands you need at your fingertips.

---

### 🚀 Initial Discovery (No Port Scan)
Quickly find what's alive on the network before wasting time on dead IPs.

| Command | Action |
| :--- | :--- |
| `nmap -sn 10.10.10.0/24` | **Ping Sweep:** Check live hosts only. |
| `nmap -Pn <target>` | **No Ping:** Assume the host is up (Bypass ICMP block). |
| `nmap -PR <target>` | **ARP Scan:** Best for local network discovery. |

---

### ⚔️ The "Standard" Kill-Chain
The most common scans used in HTB and real-world engagements.

```bash
# The "All-in-One" Scan (Agreessive)
nmap -A -T4 <target>

# Stealthy SYN Scan (Requires Root)
sudo nmap -sS <target>

# Full TCP Connect Scan (No Root required)
nmap -sT <target>

# Fast Scan (Top 100 ports)
nmap -F <target>
