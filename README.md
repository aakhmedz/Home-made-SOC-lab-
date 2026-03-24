# Soc Detection Lab (Splunk + Kali)

## Overview
This project simulates a Security Operations Center (SOC) environment using a Linux-based lab. Real-world cyberattacks were executed from a Kali Linux virtual machine and detected using Splunk running on a separate system.

## Tools Used
- Splunk Enterprise (SIEM)
- Kali Linux (attacker + target environment)
- Nmap (network reconnaissance)
- Hydra (brute-force attacks)
- Netcat (reverse shell access)
- Linux system logs (/var/log/auth.log, /var/log/syslog)

## Lab Architecture
The lab consists of a Kali Linux virtual machine running on a Linux Mint host, with Splunk deployed on a separate laptop for centralized log collection and analysis.

(Add diagram later)

## Attacks Simulated
- Port Scanning (Nmap)
- SSH Brute Force Attacks (Hydra)
- Reverse Shell Access (Netcat)
- Authentication Attempts (successful and failed logins)

## Detection Engineering
- Brute Force Detection (failed SSH login attempts)
- Successful Login Detection (accepted SSH sessions)
- Network Usage Spike Detection (time-based anomaly detection)
- Login Pattern Analysis (correlating failed and successful logins)
- Suspicious Remote Shell Activity (unauthorized command execution behavior)

## Results
- Successfully detected simulated attacks using Linux log data
- Identified brute-force activity through authentication logs
- Observed abnormal behavior during reverse shell sessions
- Built alerts and dashboards for monitoring suspicious activity

## Key Skills Demonstrated
- SIEM configuration and usage (Splunk)
- Linux log analysis and monitoring
- Threat detection using SPL queries
- Basic detection engineering and alert creation
- Security event investigation and analysis

