# Alert Report: Email Marked as Phishing

**Date:** March 27, 2025  
**Analyst:** Rayan  
**Severity:** Medium  

## WHO
Recipient: Eddie Huffman, IT Manager  
Email: e.huffman@tryhackme.thm  
Spoofed Sender: support@microsoft.com  

## WHAT
Eddie Huffman received a phishing email 
disguised as Microsoft Teams pricing notice.
Email contained suspicious file: REPORT.rar
Sender identity is spoofed (not real Microsoft)

## WHEN
March 27th 2025 at 19:25

## WHERE
Email: e.huffman@tryhackme.thm  
Spoofed sender: support@microsoft.com  

## WHY
- SPF: Fail = email not from real Microsoft
- DKIM: Fail = sender identity is forged
- Keywords: "urgent, 600% increase, download"
- Attached: REPORT.rar = suspicious file

## VERDICT
True Positive

## RECOMMENDED ACTION
1. Block sender: support@microsoft.com (spoofed)
2. Warn Eddie Huffman not to open REPORT.rar
3. Escalate to L2 for REPORT.rar analysis
4. Check if other employees got same email
