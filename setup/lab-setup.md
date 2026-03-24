# Lab Setup

## Environment Overview
- Host System: Linux Mint (bare metal)
- Attacker System: Kali Linux VM
- SIEM: Splunk Enterprise (running on separate laptop)

## Logging Configuration

The lab uses native Linux log files as the primary data source for monitoring and detection.

### Logs Collected
-Monitor /var/log/auth.log : Authentication events 
-Monitor /var/log/syslog : General system activity

These logs were selected to capture:
- Failed and successful login attempts
- System-level activity during attacks
- Indicators of brute-force and unauthorized access

## Splunk Forwarder Configuration

The Splunk Universal Forwarder was installed on the Linux Mint host system to collect and forward logs to the Splunk instance.

### Data Inputs Configured
sudo ./splunk add monitor /var/log/auth.log 
sudo ./splunk add monitor /var/log/syslog 

Logs were forwarded in real-time to Splunk for indexing and analysis.

## Data Flow

Kali Linux (attacker)
→ Generates attack activity (Nmap, Hydra)
→ Events logged in Linux Mint system logs
→ Splunk Forwarder collects logs
→ Logs sent to Splunk (remote laptop)
→ Detection and alerting performed in Splunk

## Outcome

This setup enabled centralized monitoring of Linux-based activity and allowed detection of:
- SSH brute-force attacks
- Authentication anomalies
- Network activity spikes
- Privilege Escalation
