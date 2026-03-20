# 🔗 SOC Day 02 – Cyber Kill Chain
**Date:** 10/03/2026 | **Platform:** ThinkCloudly

---

## Part 1: A Day in the Life of a SOC Analyst (Tier 1)

### 🕗 08:00 AM – Shift Handoff & Stand-Up
- Joins morning handover with the night team
- Briefed on: suspicious login from Russian IP + 
  malware detections from endpoint protection platform
- Takes notes and prepares for **triage** 
  *(= sort, verify, prioritise)*

### 🕣 08:30 AM – Alert Triage Begins
- Opens **SIEM** (e.g. Splunk or QRadar)
- **Alert 1:** Same user logged in from 2 countries 
  within 5 minutes
  - Checks location history → Verifies with HR → 
    User is on vacation in Mexico
  - ✅ Marked as **false positive** — rule flagged for tuning

### 🕙 10:00 AM – Email Phishing Investigation
- User reports suspicious PDF attachment
- Extracts indicators: headers, URLs, hashes
- Uses **VirusTotal, Any.Run** and internal sandbox
- PDF confirmed malicious — launches PowerShell 
  to download malware
- ⬆️ **Escalated to Tier 2** for containment
- Awareness email sent via comms team

### 🕦 11:30 AM – Threat Hunting Sprint (Weekly)
- Runs hunt using known **IOCs** from phishing campaign
- Queries endpoint logs + proxy logs
- No hits → documents activity and updates detection rules

### 🕐 01:00 PM – Lunch & Catch-up
- Reads CISA's latest threat advisory

### 🕑 02:00 PM – SIEM Rule Review & Tuning
- Reviews detection rules triggered during the week
- Tunes rule causing false positives from DevOps tools

### 🕒 03:00 PM – Incident Review Meeting
- Call with Tier 2 analysts + IR team
- Reviews top 5 incidents of the week
- Discusses: response timelines, detection gaps, 
  playbook improvements

### 🕓 03:45 PM – Shift Wrap-up & Notes
- Finalises documentation, updates shift log
- Flags alert for potential overnight escalation

### 🕓 04:00 PM – Log Off
- Hand findings to the next shift

---

## Part 2: Cyber Kill Chain

> Developed by **Lockheed Martin** to describe the 
> stages of a cyber attack. Breaking **any** stage 
> can stop the full attack.

---

## ⛓️ The 7 Stages

| # | Stage | Definition | Techniques | Real-World Case |
|---|-------|-----------|------------|-----------------|
| 1 | **Reconnaissance** | Attacker gathers intel on target | OSINT, Nmap/Shodan, social engineering | Target breach (2013) |
| 2 | **Weaponization** | Crafts malicious payload | Trojans, ransomware, Metasploit | Stuxnet – zero-day exploit |
| 3 | **Delivery** | Delivers payload to target | Phishing emails, drive-by downloads, USB drops | WannaCry ransomware |
| 4 | **Exploitation** | Exploits vulnerability for access | Unpatched software, credential stuffing, zero-days | Equifax breach (2017) |
| 5 | **Installation** | Establishes persistent access | Backdoors, rootkits, registry modifications | SolarWinds (2020) |
| 6 | **Command & Control** | Remotely controls compromised system | Encrypted C2 channels, DNS tunnelling | — |
| 7 | **Actions on Objectives** | Completes the mission | Data exfiltration, ransomware, sabotage | Colonial Pipeline (2021) |

---

## 🛡️ How to Defend Against Each Stage

| Stage | Defence |
|-------|---------|
| Reconnaissance | Network monitoring, threat intelligence, segmentation |
| Weaponisation | Keep software patched, use threat intel feeds |
| Delivery | Phishing training, email/web filtering |
| Exploitation | Deploy IDS/IPS, regularly update software |
| Installation | Use **EDR** (Endpoint Detection & Response) |
| Command & Control | Monitor network traffic, block malicious domains |
| Actions on Objectives | Implement **DLP**, back up critical data regularly |

---

## 📋 Case Study: Ransomware Attack

| Stage | What Happened |
|-------|--------------|
| Recon | Scanned for outdated VPN servers |
| Weaponisation | Ransomware customised to exploit VPN flaw |
| Delivery | Phishing email tricks employee |
| Exploitation | Malware exploits VPN vulnerability |
| Installation | Ransomware installs and spreads laterally |
| C2 | Attackers receive encryption keys from C2 server |
| Actions | Files encrypted, ransom demand issued |

---

## 💡 Key Takeaway
> The SOC's job is to detect and respond at every 
> stage - ideally as early as possible before real 
> damage is done.
