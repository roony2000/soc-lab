## Report Date: 06-06-2026
* ALERT: Suspected Backdoor Access
* SEVERITY: High
* ANALYST: Rayan

## WHO:
* Host: University Network Device

## WHAT:
* A malicious program was installed on a 
university network device, sending automated
beacon signals every 6 minutes to an external
attacker (C2 communication).

## WHEN:
* Pattern: Every 6 minutes (Beaconing)
Behavior: Consistent and automated

## WHERE:
* Network: University Environment

## WHY:
 - Regular 6-minute beaconing = automated malware
 - Indicates active C2 communication
 - Attacker has persistent remote access
 - Risk of spreading to other network devices

# VERDICT: 
* True Positive

## RECOMMENDED ACTION:
1. Isolate the affected host from network
2. Escalate to L2 for malware analysis
3. Preserve device logs before any changes
