
# 🕵️‍♂️ Phishing Email Analysis Project

## 🎯 Objective
Identify phishing characteristics in a suspicious email sample by examining:
- Header information (SPF, DKIM, DMARC, source IP, routing)
- Message content (tone, links, sender identity, grammar)

---

## 🧰 Tools Used
- **Email Client / Saved Email File** – for viewing raw email source and metadata  
- **Free Online Header Analyzers:**
  - [MxToolbox Email Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)
  - [Google Admin Toolbox Messageheader](https://toolbox.googleapps.com/apps/messageheader/)
- **Optional:** Spamhaus IP Lookup, VirusTotal URL Scanner

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
| **SPF** | Failed – sending domain not authorized | ⚠️ Spoofing risk |
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
The email exhibits multiple **phishing indicators**, including:
- Failed SPF/DKIM/DMARC checks  
- Sender domain spoofing  
- Urgent and manipulative language  
- Suspicious external URLs  
- Generic greeting and grammatical mistakes  

**Assessment:** 🔴 **High likelihood of phishing attempt**  
**Recommendation:**  
- Do **not** click links or download attachments  
- **Report** and **delete** the email  
- Consider **blocking sender domain** and updating spam filters

---

## 📚 5. References
- [MxToolbox Email Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)  
- [Google Admin Toolbox Messageheader](https://toolbox.googleapps.com/apps/messageheader/)  
- [CISA Phishing Awareness Tips](https://www.cisa.gov/resources-tools/resources/stopthinkconnect-phishing-tips)





