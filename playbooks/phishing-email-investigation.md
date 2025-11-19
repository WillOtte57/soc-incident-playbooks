# Phishing Email Investigation Playbook

## 1. Description

This playbook describes how to handle a suspected phishing email that has been reported by a user or detected by an email security tool.

---

## 2. Detection

**Possible detection sources:**
- User reports a suspicious email
- Email security gateway flags an email
- SIEM alert for known phishing patterns or malicious URLs

**Initial questions:**
- Who received the email?
- Did anyone click a link or open an attachment?
- When was the email received?

---

## 3. Triage & Analysis

1. **Collect the email details:**
   - Sender address
   - Recipient(s)
   - Subject
   - Time received

2. **Examine technical indicators:**
   - Check email headers for:
     - Spoofed sender domains
     - Mismatched "From" and "Return-Path"
   - Hover over links (do not click) and check:
     - Suspicious or misspelled domains
     - Use of URL shorteners

3. **Check URLs and attachments:**
   - Submit URLs to a safe URL reputation service (if available)
   - Check attachments with antivirus/sandbox tools (if available)

4. **Decide:**
   - Is this likely phishing?
   - Is it clearly benign?

---

## 4. Containment

If phishing is confirmed or strongly suspected:

1. Instruct the user:
   - Do not click any links
   - Do not reply to the email
   - Do not open any attachments

2. If the user already clicked:
   - Ask what they clicked and when
   - Ask if they entered any credentials

3. Work with email/admin tools to:
   - Quarantine or delete the email from all mailboxes (if possible)
   - Block the sender domain or IP
   - Block malicious URLs at the proxy or firewall

---

## 5. Eradication

- Remove any malicious files or attachments from endpoints.
- If credentials were entered on a fake page:
  - Force password reset for affected accounts.
  - Invalidate active sessions or tokens (if possible).

---

## 6. Recovery

- Confirm no signs of further malicious activity on:
  - Email accounts
  - Workstations
  - Related systems

- Restore normal access if any temporary blocks were applied.

---

## 7. Lessons Learned

- Update email filtering rules if needed.
- Consider adding the example to phishing awareness training.
- Document:
  - What worked well
  - What took too long
  - What could be automated in the future

---

## 8. Notes

This is a beginner-friendly playbook and focuses on basic steps. In a real SOC, tools like SIEMs, EDR, and email gateways would provide more automation and data for deeper analysis.

