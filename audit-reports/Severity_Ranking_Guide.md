# 🚨 Severity Ranking Guide

> Based on Owen’s video: [**Is This A Critical? How To Rank Vulnerability Severity**](https://www.youtube.com/watch?v=f4UdAnHUpSE)  
> and insights from **Pashov’s Severity Matrix**.

---

## 🧭 Table of Contents

- [Pashov's Severity Ranking System](#pashovs-severity-ranking-system)
  - [Critical](#critical)
  - [High](#high)
  - [Medium](#medium)
  - [Low](#low)

---

# ⚖️ Pashov's Severity Ranking System

| **Severity**        | **Impact: High** | **Impact: Medium** | **Impact: Low** |
| -------------------- | ---------------- | ------------------ | ---------------- |
| **Likelihood: High**   | 🔥 **Critical** | ⚠️ **High** | 🟠 **Medium** |
| **Likelihood: Medium** | ⚠️ **High** | 🟠 **Medium** | 🟡 **Low** |
| **Likelihood: Low**    | 🟠 **Medium** | 🟡 **Low** | 🟢 **Low** |

---

## 🧨 Critical

> You *know* a critical when you see one 😎

These are the vulnerabilities that can **drain the protocol**, **brick withdrawals**, or **cause system-wide griefing**.  
If an attacker can **steal ≥20% of total value** or make all funds unrecoverable — that’s **Critical**.

### 🔍 How to Tell It’s Critical (vs High)

- **Guaranteed impact?**
  - Relies on front-running in a private mempool → not guaranteed → High / Medium  
  - 100% exploitable and profitable → **Critical**

- **Who’s affected?**
  - All users or protocol-wide impact → **Critical**  
  - Only a single special user → **High**

- **Time to impact?**
  - Takes months → **High**  
  - Takes days → **Critical**

---

## ⚠️ High

Attacks that are **complex or capital-intensive**, but with **serious consequences**.  
They may not end the protocol, but they’ll definitely **hurt**.

### 💥 Examples

- TWAP / Oracle / Reference price manipulation  
- Exploiting logic with high-value capital positions  
- **Griefing** or **DoS** attacks  
  > e.g. making the protocol waste ~$500/day in gas  

### 🔍 How to Tell It’s High (vs Medium)

- Rare but catastrophic → **High**  
- Rare with mild impact → **Medium**  
- Likely with massive impact → **High / Critical**  
- Likely with moderate impact → **High**

---

## 🟠 Medium

These are **“not catastrophic but not ignorable”** issues.  
They don’t break the system but can cause **minor financial loss**, **centralization risk**, or **unexpected behavior**.

### 💥 Examples

- Incorrect rounding that slightly affects balances  
- Config or logic issues that could escalate  
- Centralization or access control weaknesses  

### 🔍 How to Tell It’s Medium (vs Low)

- Will careful users notice it?
  - ✅ Yes → **Medium**
  - ❌ No → **Low**

- Could it become serious in future conditions?
  - ✅ Yes → **Medium**
  - ❌ No → **Low**

---

## 🟢 Low

Minor findings with **no real impact** — such as gas inefficiencies, missing events, or best-practice recommendations.  
They don’t pose a security risk but improve code quality.

> 💡 *Owen’s take:* Combine gas, QA, and best practices into **Low** findings.  
> Fewer categories = simpler, more consistent audits.

---

## 🧩 TL;DR — Think Like an Attacker

| 🧠 **Question** | 🎯 **If Yes → Severity** |
| --------------- | ------------------------ |
| Can it **steal value** or **block users**? | 🔥 **Critical** |
| Can it **hurt the protocol** but not destroy it? | ⚠️ **High** |
| Can it **annoy users** or **waste resources**? | 🟠 **Medium** |
| Can it **teach better code habits**? | 🟢 **Low** |

---

### 🧠 Final Tip:
Severity is not just about the **bug**, it’s about the **context**.  
Ask yourself: *“If I were the attacker, how bad could this get?”*  
That’s how you rank it right.
