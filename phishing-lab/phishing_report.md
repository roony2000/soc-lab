# Phishing Email Analysis Report

## Analyst Information
- Name: Roony
- Date: 2026-06-02
- Tools Used: whois, cat

## Email Details
- From: security-alert@paypa1.com
- To: victim@company.com
- Subject: [URGENT] Your account has been suspended - Action Required
- Date: Mon, 01 Jun 2026 03:47:22 +0000

## Red Flags Found

### 1. Fake Sender Domain
- Legitimate: paypal.com
- Phishing: paypa1.com (number 1 instead of letter L)
- Technique: Typosquatting

### 2. Suspicious IP Address
- IP: 185.220.101.47
- Type: Tor Exit Node
- Country: Germany (DE)
- Network: ForPrivacyNET
- Risk: Attacker is hiding real identity using Tor
- No logs kept — untraceable

### 3. Malicious URL
- URL: http://paypal-secure-login.suspicious-domain.xyz/verify
- Legitimate PayPal URL: paypal.com
- Red Flag: Completely different domain
- WHOIS Result: Domain not found — likely temporary

### 4. Social Engineering Tactics
- Urgency: "Action Required", "24 hours"
- Fear: "permanent account closure"
- Impersonation: Pretending to be PayPal Security Team

## Attack Flow
1. Victim receives email from fake PayPal address
2. Fear and urgency push victim to click the link
3. Fake login page steals credentials
4. Attacker gains access to real PayPal account

## Conclusion
This is a confirmed Phishing email. All indicators point to a 
deliberate attempt to steal PayPal credentials through social 
engineering and domain spoofing.

## Recommended Actions
- Block IP: 185.220.101.47
- Block domain: paypa1.com
- Report to: abuse@for-privacy.net
- Alert all employees about this phishing campaign
- Add detection rule in email security tool
