# 📧 Phishing Email Analysis – Cyber Security Internship Task 2

This repository contains the analysis of two email samples to demonstrate understanding of **phishing characteristics**, **email authentication protocols (DMARC/SPF/DKIM)**, and **threat detection** practices.

---

## 🔍 Email Samples Analyzed

### 1. ❌ **Phishing Email – Netflix Password Reset**

- **Sender:** `netflix@webnotifications[.]net`
- **Subject:** Password expiring soon
- **Reason it's phishing:**
  - Fake sender domain
  - Urgent language ("Password expiring soon")
  - Suspicious reset link (not visible in screenshot, but assumed)
  - Grammar issues ("Netflix are requesting...")
  - No personal account info
  - Spoofed branding
- **Tool Used for Analysis:** [MXToolbox Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)
- **Likely Result:** DMARC, SPF, or DKIM would fail due to spoofed domain.

---

### 2. ✅ **Legitimate Email – CTFtime.org Membership Request**

- **Sender:** `noreply@ctftime.org`
- **Subject:** Membership request notification
- **Reason it's legitimate:**
  - Official domain and email address
  - Calm, relevant tone with clear context
  - Correct grammar and formatting
  - Direct links to `ctftime.org` domain
  - DMARC record published with `p=none` for monitoring
- **Tool Used for Analysis:** [Mail-Tester](https://www.mail-tester.com/)
- **Result:** SPF/DKIM/DMARC likely pass (verified via domain check)

---

## 🛠 Tools Used

| Tool | Purpose |
|------|---------|
| [MXToolbox](https://mxtoolbox.com/EmailHeaders.aspx) | Header and SPF/DKIM/DMARC analysis for suspicious emails |
| [Mail-Tester](https://www.mail-tester.com/) | Used to check DMARC policy of legitimate domain (`ctftime.org`) |

---

## 🧠 How to Analyze a Suspicious Email

1. **Check the Sender's Email Address:**
   - Look for slight variations in spelling, domain spoofing (e.g., `netflix@webnotifications.net` vs `support@netflix.com`).

2. **Hover Over Links (DON’T Click):**
   - Make sure URLs lead to the official domain (e.g., `https://www.netflix.com`).

3. **Examine Grammar and Language:**
   - Poor grammar, generic greetings ("Dear User"), and urgency are red flags.

4. **Verify Headers Using Tools:**
   - Tools like MXToolbox show SPF, DKIM, and DMARC results to detect spoofing.

5. **Confirm with Known Sources:**
   - Never reset passwords or enter details unless you're 100% sure of the sender's authenticity.

---

## 📌 Conclusion

This task helped demonstrate how phishing emails can mimic trusted brands using social engineering and technical deception, and how basic email header analysis can be used to spot and report them.

---

### 📎 Files Included

- `phishing_analysis.md` – Detailed breakdown of the Netflix phishing email
- `legitimate_email_analysis.md` – Analysis of the CTFtime.org email
- Screenshots folder – Visual evidence of both emails

---
🛡️ What is DMARC?
DMARC(Domain-based Message Authentication, Reporting, and Conformance) is an email authentication protocol that uses SPF and DKIM records to verify the sender's identity. When a DMARC check fails, the email might be:

Sent from a spoofed domain

Not aligned with SPF(Sender Policy Framework)/DKIM(DomainKeys Identified Mail).

Not authorized by the domain owner