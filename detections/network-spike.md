# Network Usage Spike Detection

## Description
Detects abnormal increases in network activity over time, which may indicate port scanning, brute-force attacks, or data exfiltration.

## SPL Query
index=* | timechart span=1m count

## Use Case
- Nmap scans
- Hydra attacks
- Traffic anomalies

## Severity
Medium

## Result
Alert successfully triggered during attack simulation.
