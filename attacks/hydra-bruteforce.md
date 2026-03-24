# Hydra SSH Brute Force Attack

## MITRE ATT&CK Mapping: T1110 (Brute Force)

## Command
hydra -l <username> -P Secret.tcx ssh://<target-ip>

## Description
Executed a brute-force attack against the SSH service using a wordlist to attempt multiple password combinations.

## Purpose
Simulate credential-based attack targeting SSH authentication.

## Observed Behavior
- Multiple "Failed password" entries in /var/log/auth.log
- Repeated login attempts from same IP address

## Detection Link
Detected using brute-force detection and login correlation rules in Splunk.
