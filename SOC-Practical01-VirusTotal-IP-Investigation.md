# 🔍 SOC Practical 01 — IP Investigation Using VirusTotal

**Date:** 30 March 2026
**Platform:** VirusTotal (virustotal.com)
**Type:** Hands-On Practical
**Source:** Skill Horizon  IP Investigation Exercise

---

## 🎯 Objective

To investigate a suspicious IP address using VirusTotal, interpret the threat intelligence data returned, and practise the decision-making process a SOC Analyst uses when assessing unknown IPs in an environment.

---

## 🖥️ Target IP

| Field | Detail |
|---|---|
| IP Address | `185.234.219.246` |
| Tool Used | VirusTotal |
| Method | Manual search via VirusTotal search bar |

---

## 🔬 Process

1. Identified the sample suspicious IP from the exercise: `185.234.219.246`
2. Navigated to [virustotal.com](https://virustotal.com)
3. Entered the IP into the search bar and submitted
4. Reviewed the **Detection**, **Details**, **Relations**, and **Community** tabs
5. Recorded all findings and formed an analyst verdict

---

## 📊 Findings

### Detection

| Metric | Result |
|---|---|
| Malicious Detections | **0 / 58 vendors** |
| Clean Verdict | 58 vendors returned clean |
| Unrelated / No Data | Remaining vendors returned unrelated results |
| Overall Verdict | ✅ No Threat Detected |

---

### Infrastructure Details

| Field | Value |
|---|---|
| ASN | AS211415 |
| Country | Austria (AT) |
| Continent | Europe (EU) |
| IP Type | Likely legitimate European hosting infrastructure |

---

### Threat Association

| Category | Finding |
|---|---|
| Malware Families | None |
| C2 Activity | None |
| Phishing Campaigns | None |
| Last Seen Active | 19 days ago |

---

## ✅ Analyst Verdict

> **Block Recommended: No**

**Reasoning:**
- Zero vendors flagged the IP as malicious
- Registered to a legitimate European ASN (AS211415) in Austria
- No association with malware, C2 infrastructure, or phishing
- Last seen 19 days ago — active IP, not flagged by any intel feed
- Blocking without evidence would risk unnecessary false positive disruption

---

## 🧠 Key Takeaways

- **VirusTotal is one tool**:- a clean result does not automatically mean the IP is harmless in all contexts
- **ASN data** reveals who owns and routes the IP block :- useful for profiling infrastructure origin
- **Last seen timestamp** tells you whether an IP is still active in threat intel feeds, even if clean
- **Context is everything** :- a clean IP appearing repeatedly in logs at odd hours still warrants investigation
- A SOC analyst always cross-references VirusTotal results with **SIEM data, network logs, and other threat intel feeds** before making a final verdict
- **Document everything** :-  even clean investigations build pattern recognition over time and create an audit trail

---

## 🛠️ Skills Demonstrated

- IP reputation analysis
- ASN and geolocation interpretation
- Threat intelligence tool usage (VirusTotal)
- SOC analyst decision-making
- Investigation documentation

---

## 🔗 Related Logs

- [SOC Day 01 — Security Operations Centre](./SOC-Day01-SecurityOperationsCenter.md)
- [SOC Day 02 — Cyber Kill Chain](./SOC-Day02-CyberKillChain.md)
- [TryHackMe — Networking](./TryHackMe-Networking.md)
