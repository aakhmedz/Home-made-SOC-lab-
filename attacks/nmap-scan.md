# Nmap Port Scan

## MITRE ATT&CK MAPPING: T1046 (Network Service Scanning) 

## Command
nmap -sS <target-ip>

## Description
Performed a SYN scan against the target system to identify open ports and simulate reconnaissance activity.

## Purpose
Simulate attacker behavior during the reconnaissance phase.

## Observed Behavior
- Increased number of connection attempts
- Spike in system activity logs

## Detection Link
Detected using network usage spike detection in Splunk.
