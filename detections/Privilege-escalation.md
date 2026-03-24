# Privilege Escalation Activity Detection

## Description
Detects attempts to escalate privileges using commands such as `su` or `sudo`, which may indicate unauthorized access or misuse of elevated permissions.

## SPL Query
source="/var/log/auth.log" ("FAILED SU" OR "session opened for user root" OR "sudo")

## Alert Configuration
- Trigger Condition: Number of results > 0
- Severity: High
- Schedule: Every 5 minutes
- Alert Type: Scheduled

## Use Case
- Attempt to gain root access after initial compromise

## Evidence
![Privilege Escalation](results/screenshots/Privilege-Escalation-Detection.png)


## Result
Privilege escalation attempts were detected during testing, including failed and successful attempts to switch to root.
