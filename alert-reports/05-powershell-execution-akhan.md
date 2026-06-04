# Alert Report: Suspicious PowerShell Execution

**Date:** April 3, 2025  
**Analyst:** Rayan  
**Severity:** High  

## WHO
User: A.Khan  
Host: LPT-IT-012  

## WHAT
A.Khan opened a Word document that automatically 
executed PowerShell. PowerShell downloaded 
a malicious payload from evil-c2.ru

## WHEN
April 3rd 2025 at 08:45

## WHERE
Host: LPT-IT-012  
C2 Server: evil-c2.ru (Russian domain)  
Process: powershell.exe  
Parent Process: winword.exe  

## WHY
- PowerShell launched from Word = abnormal
- "-ep bypass" = security controls bypassed
- evil-c2.ru = known malicious C2 server
- Payload downloaded and executed remotely

## VERDICT
True Positive

## RECOMMENDED ACTION
1. Isolate LPT-IT-012 from network immediately
2. Escalate to L2 for full malware analysis
3. Preserve device logs before any changes
4. Check if other users received same Word file
