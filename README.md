

# Phishing Analysis Report: "Microsoft Account Compromise"

**Date:** 2025-10-22
**Analyst:** [Your Name Here]
**Severity:** High

---

## 1. Executive Summary

This report details the analysis of a phishing email received on [Date]. The email impersonates Microsoft Security and attempts to steal user credentials by creating a false sense of urgency. The campaign relies on a misspelled sender domain and a shortened URL to deceive the victim.

## 2. Indicators of Compromise (IOCs)

Indicators of Compromise (IOCs) are pieces of forensic data that identify a malicious attack.

| Type | Indicator | Notes |
| :--- | :--- | :--- |
| **Sender Email** | `support@microsft-security.com` | Spoofed domain (missing 'o' in "Microsoft"). |
| **Email Subject** | `Urgent Action Required: Your Account Has Been Compromised!` | Uses urgent/threatening language. |
| **Malicious URL** | `http://bit.ly/secure-msft-123` | URL shortener used to hide the true destination. |
| **IP Address** | `(Headers would show originating IP)` | N/A (Header analysis was not performed on this sample). |
| **File Hashes** | `N/A` | No attachments in this sample. |

## 3. Detailed Analysis (The 8 Steps)

This analysis follows the 8-step procedure.

1.  **Email Obtained:** The sample email was acquired for analysis. (See [Appendix A](#appendix-a-email-body)).

2.  **Sender Email Analysis:** The sender address `support@microsft-security.com` is a clear case of **typosquatting**. The attacker registered a domain that looks like the real one ("microsft" vs. "microsoft") to trick users who are not paying close attention.

3.  **Header Analysis:** (Hypothetical) A review of the email headers would likely show:
    * `SPF (Sender Policy Framework)`: **FAIL** or **SOFTFAIL**, indicating the sending server is not authorized by the `microsft-security.com` domain's SPF record.
    * `Received` path: The email would likely originate from an unknown or non-Microsoft server, confirming it is not legitimate.

4.  **Suspicious Links/Attachments:** The email contains one link, `http://bit.ly/secure-msft-123`. The use of a URL shortener (Bitly) is a major red flag, as it is a common technique to hide the final, malicious domain.

5.  **Urgent/Threatening Language:** The email body is filled with psychological triggers to panic the user:
    * "Urgent Action Required"
    * "immediately"
    * "Failure to comply within 24 hours"
    * "permanent account termination"
    This social engineering tactic is designed to make the user act without thinking.

6.  **Mismatched URLs:** Hovering over the link would reveal the `bit.ly` address, which does not match any official Microsoft domain.

7.  **Spelling/Grammar:** The primary error is the misspelled "microsft" in the sender's address. The body text is relatively clean, suggesting a more careful attacker.

8.  **Summary of Phishing Traits:**
    * **Impersonation:** Pretends to be "The Microsoft Security Team."
    * **Urgency & Fear:** Threatens "permanent account termination."
    * **Deceptive Link:** Hides the true destination URL.
    * **Domain Spoofing:** Uses a typosquatted domain.

## 4. Recommendations (Mitigation)

To defend against this type of attack, organizations and users should:

* **User Training:** Educate users to always check the full sender email address for misspellings.
* **Hover-Before-You-Click:** Train users to always hover their mouse over any link to see the true destination before clicking.
* **Security Policies:** Implement email security gateway rules to block or quarantine emails from known typosquatted domains or those that fail SPF checks.
* **Never Use Email Links for Login:** Advise users to never click a link in an email to log into a sensitive account. Instead, they should type the official website (e.g., `account.microsoft.com`) directly into their browser.

---

## Appendix A: Email Body

> **From:** support@microsft-security.com
> **Subject:** Urgent Action Required: Your Account Has Been Compromised!
>
> Dear User,
>
> Our system detected unusual activity on your account from an unrecognized location. For your protection, we have temporarily locked your account.
>
> To restore access, you must verify your identity immediately. Failure to comply within 24 hours will result in permanent account termination.
>
> Please click the link below to secure your account:
>
> http://bit.ly/secure-msft-123
>
> Thank you,
> The Microsoft Security Team
