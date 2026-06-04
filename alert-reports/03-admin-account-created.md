# Alert Report: Unusual Admin Account Created

**Date:** April 2, 2025  
**Analyst:** Rayan  
**Severity:** High  

## WHO
Host: SRV-FIN-001  
Created by: Administrator  

## WHAT
New account "svc_backup99" was created 
on SRV-FIN-001 at 02:30 AM outside 
of normal business hours.

## WHEN
April 2, 2025 at 02:30 AM

## WHERE
Host: SRV-FIN-001  
Account: svc_backup99  

## WHY
- No IT ticket found = unauthorized
- Created at 02:30 AM = no staff working
- IT team confirmed they did NOT create it
- Possibly created by attacker for persistence

## VERDICT
True Positive

## RECOMMENDED ACTION
1. Disable account svc_backup99 immediately
2. Contact Administrator to verify
3. Escalate to L2 for full investigation
