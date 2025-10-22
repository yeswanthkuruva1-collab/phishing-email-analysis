# 🕵️‍♂️ Phishing Email Analysis Report

## 🎯 Objective
Identify and document phishing characteristics in a suspicious email sample by examining its content and headers.

---

## 🧰 Tools Used
- **Email Client / Saved Email File** – for viewing the raw message and metadata  
- **Free Online Header Analyzer** – to inspect email routing and authentication  
  - [MxToolbox Email Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)  
  - [Google Admin Toolbox Messageheader](https://toolbox.googleapps.com/apps/messageheader/)

---

## 📧 1. Email Overview
| Field | Detail |
|--------|---------|
| **Subject** | Important: Verify your account immediately |
| **Sender Address** | support@micr0soft-verification.com |
| **Received Date** | 22 October 2025 |
| **Attachment / Links** | https://secure-microsoft-login.net |
| **Email Type** | HTML with embedded link |

---

## 🧾 2. Header Analysis
**Key Findings from Header Analyzer:**

| Parameter | Observation | Indicator |
|------------|--------------|------------|
| **SPF** | Failed – sending domain not authorized | ⚠️ Suspicious (spoofing risk) |
| **DKIM** | Not signed | ⚠️ Missing integrity verification |
| **DMARC** | None | ⚠️ No domain policy enforcement |
| **Return-Path** | reply-to: help@phishmail.ru | ⚠️ Mismatch with sender domain |
| **Received From IP** | 185.123.45.67 (Blacklisted in Spamhaus) | ⚠️ Known malicious source |

---

## 🧠 3. Content Analysis
| Indicator | Example / Observation | Why It’s Suspicious |
|------------|------------------------|----------------------|
| **Urgent Call to Action** | "Verify your account immediately to avoid suspension." | Creates panic to prompt hasty action |
| **Impersonation** | Claims to be from “Microsoft Support” but uses misspelled domain | Brand spoofing |
| **Suspicious Links** | Hover link: https://secure-microsoft-login.net | Domain not owned by Microsoft |
| **Grammatical Errors** | “Your account are in danger” | Poor grammar typical in phishing |
| **Generic Greeting** | “Dear User” | Lack of personalization |
| **Attachment or Link Prompt** | Requests credential verification | Attempts to harvest login details |

---

## ✅ 4. Conclusion
The analyzed email shows multiple **phishing indicators**, including:
- Failed SPF/DKIM/DMARC authentication  
- Sender domain spoofing  
- Urgent, fear-based language  
- Suspicious URLs  
- Generic greeting and grammatical errors  

**Assessment:** 🔴 High likelihood of phishing attempt.  
**Recommendation:** Do **not** click any links or download attachments. Report and delete the message.

---

## 📚 5. References
- [MxToolbox Email Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)  
- [Google Admin Toolbox Messageheader](https://toolbox.googleapps.com/apps/messageheader/)  
- [CISA Phishing Guidance](https://www.cisa.gov/resources-tools/resources/stopthinkconnect-phishing-tips)

---

### 🗂️ Suggested Repository Structure


