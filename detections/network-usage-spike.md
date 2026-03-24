# Network Usage Spike Detection

## Description
Detects abnormal increases in system or network activity over time, which may indicate reconnaissance or attack behavior.

## SPL Query
index=* | timechart span=1m count

## Alert Configuration
- Trigger Condition: Visual spike in activity
- Severity: Medium
- Schedule: Every 5 minutes
- Alert Type: Scheduled

## Use Case
- Nmap scanning
- General anomalous behavior

## Evidence
![Network Detection](../results/screenshots/Network-Spike-Detection.png)

## Result
A spike in activity was observed during Nmap scanning, indicating reconnaissance behavior.
