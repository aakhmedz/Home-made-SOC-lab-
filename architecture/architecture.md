# Lab Architecture

## Overview
This lab is built using a Linux-based environment where attack activity is generated, logged, and analyzed through a centralized SIEM.

## Components

### Kali Linux VM
Used to simulate attacker behavior including:
- Nmap scans
- Hydra brute-force attacks

### Linux Mint Host
Serves as the primary system where logs are generated and collected:
- /var/log/auth.log (authentication events)
- /var/log/syslog (system activity)

### Splunk Universal Forwarder
Installed on the Linux Mint system to monitor and forward log data to Splunk.

### Splunk Enterprise (Laptop)
Used as the SIEM platform for:
- Log ingestion and indexing
- Detection using SPL queries
- Alerting and dashboard visualization

## Data Flow

Attack activity is generated from the Kali Linux VM and recorded in Linux system logs on the host machine. These logs are collected by the Splunk Universal Forwarder and sent to a remote Splunk instance, where they are analyzed to detect suspicious behavior.

## Outcome

This architecture enables centralized monitoring and detection of security events in a Linux-based environment using SIEM tools.
