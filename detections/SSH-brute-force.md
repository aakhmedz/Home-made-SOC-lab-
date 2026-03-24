# SSH Brute Force Detection - Multiple Failed Logins

## Description
Detects multiple failed SSH login attempts from a single IP address, indicating a potential brute-force attack.

## SPL Query
source="/var/log/auth.log"  "Failed password" | rex "from (?<src_ip>\d+\.\d+\.\d+\.\d+)" | stats count by src_ip | where count > 5

## Alert Configuration
- Trigger Condition: Number of results > 0
- Threshold: More than 5 failed attempts
- Severity: High
- Schedule: Every 5 minutes
- Alert Type: Scheduled 

## Use Case
- Hydra brute-force attack against SSH service

## Evidence
![Brute Force Alert](results/screenshots/SSH-Bruteforce-detection.png)

## Result
Multiple failed login attempts were detected from the attacker IP during brute-force simulation.
