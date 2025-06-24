# Elevate Labs Cybersecurity Internship - Day 2 Task  
**Phishing Email Analysis Report**  
*By Harsh Gupta*  

## 🎯 Task Objective  
Analyze a phishing email sample to identify malicious characteristics using email headers and security tools.  

## 🔍 Analysis Summary  
### Key Phishing Indicators Found:  
1. **Sender Address Spoofing**  
   - `From:` banco.bradesco@atendimento.com.br (impersonating Bradesco Bank)  
   - `Return-Path:` root@ubuntu-s-1vcpu-1gb-35gb-intel-sfo3-06 (mismatched)  

2. **Suspicious Origin**  
   - Originating IP: `137.184.34.4` (generic cloud server)  
   - `X-MS-Exchange-Organization-AuthAs: Anonymous` (no authentication)  

3. **Authentication Failures**  
   - **SPF:** `temperror` (validation failure)  
   - **DKIM:** `none` (unsigned message)  
   - **DMARC:** `temperror` + `compauth=fail` (policy violation)  

4. **Social Engineering Tactics**  
   - Urgent subject: *"CLIENTE PRIME - BRADESCO LIVELO: Seu cartão tem 92.990 pontos LIVELO expirando hoje!"*  
   - Fake loyalty points expiration scare  

## 🛠️ Tools Used  
1. **EmailAnalyzer** (Kali Linux)  
   - Command:  
     ```bash
     python3 email-analyzer.py -f sample-1.eml -H -d -l -a
     ```  
2. **MXToolbox** Email Header Analyzer  
   - [Online Report](https://mxtoolbox.com/Public/Tools/EmailHeaders.aspx?huid=db5d475d-7bfa-4112-b0cd-861909b50924)  

## 📝 Key Prevention Tips  
| Tactic | Defense Action |  
|--------|----------------|  
| Suspicious Sender | Verify domain authenticity (e.g., `@bradesco.com.br` ≠ `@atendimento.com.br`) |  
| Urgent Language | Pause and verify claims via official channels |  
| Hidden Links | Hover to preview URLs before clicking |  
| Attachments | Never open unexpected files |  
| Auth Failures | Check SPF/DKIM/DMARC in headers |  
| Compromised Data | Enable MFA + immediate password reset |  

## ⚠️ If You Suspect Phishing  
1. 🚫 Don’t click links/download attachments  
2. 📧 Report to IT/security team  
3. 🗑️ Delete email (inbox + trash)  
4. 🔐 Change credentials if compromised  

## 📁 Files Included  
- `HARSH GUPTA_internshiptaskday2.pdf` (Full analysis report)  
- `sample-1.eml` (Phishing email sample)  

## 🔗 Resources  
- [EmailAnalyzer Tool](https://github.com/keraattin/EmailAnalyzer)  
- [MXToolbox Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)  
- [SPF/DKIM/DMARC Explained](https://dmarc.org/)  
