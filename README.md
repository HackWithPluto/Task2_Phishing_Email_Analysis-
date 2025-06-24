# Phishing Email Analysis Report

## Task Objective

identify and analyze phishing characteristics in a suspicious email. This task helped me develop threat detection, email header analysis, and social engineering awareness skills.

---


## Analysis Summary

| Indicator                     |Details |
|------------------------------|---------|
| **Spoofed Sender Address**   | The email claims to be from *Stellar Development Foundation*, but is sent from `r.diaz@una.edu.ar`, a university domain. |
| **Suspicious Link**          | The "Check Eligibility" button links to `https://foundationxlmdevelopment.com/`, a lookalike phishing domain. |
| **Urgency in Language**      | Subject: “$1.90 Per XLM – Act Now…” and phrases like “Act Now to Participate” create fear of missing out (FOMO). |
| **Financial Incentive**      | Promises inflated returns ($1.90/XLM) to lure users into clicking the link. |
| **Social Engineering**       | Uses urgency, rewards, and branding to manipulate the user emotionally. |
| **Technical Legitimacy (SPF/DKIM)** | (but misleading) | SPF and DKIM passed — indicating the email is sent from a valid domain (likely compromised). |
| **Branding Mismatch**        | The sender domain is not `@stellar.org`, and the linked domain is a lookalike. |

---

## Header Analysis (MXToolbox)

- **SPF Status:**  Pass
- **DKIM Status:**  Pass
- **DMARC Status:** None (policy not enforced)
- **Source IP:** `52.53.164.228` (Amazon EC2) — common in mass mail attacks
- **Authenticated domain:** `una.edu.ar` (legitimate academic domain but likely compromised)

---


## Tools Used

| Tool | Purpose |
|------|---------|
| [MXToolbox Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx) | To analyze and verify SPF/DKIM/DMARC |
| Email Client (Outlook) | To render `.eml` and inspect link behavior |
| Screenshot Tool | To capture evidence of phishing links |
| WHOIS Lookup | To inspect domain registration for fake domain |

---

## Final Conclusion

This email is a **targeted phishing attack** impersonating Stellar Foundation. Despite passing SPF and DKIM checks, the email includes:
- A **fake reward offer**
- **Urgency** to act
- A **malicious link**
- A **spoofed identity**

The attack appears to originate from a **compromised mail server** at `una.edu.ar`, and was relayed using Amazon EC2 — a method often seen in phishing campaigns.

---

## Files

| File | Description |
|---------------|-------------|
| `sample-4593.eml` | Original raw phishing email sample |
| `sample_mail.pdf` | Original phishing email sample |
| `EmailHeaderAnalysis.pdf` | Header analysis output from MXToolbox |
| `screenshots.png` | Visual proof of malicious link in the email body |

---

## Learning Outcome

-  Identified spoofing and phishing indicators
-  Analyzed email headers and authentication status
-  Strengthened understanding of social engineering
