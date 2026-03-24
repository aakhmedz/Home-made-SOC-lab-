# Successful Login After Multiple Failures

## Description
Detects a successful login that occurs after multiple failed login attempts, indicating a possible credential compromise.

## SPL Query
source="/var/log/auth.log"  ("Failed password" OR "Accepted password") | rex "from (?<src_ip>\d+\.\d+\.\d+\.\d+)" | eval event_type=if(searchmatch("Failed password"), "fail","success") | stats count(eval(event_type="fail")) as fails count(eval(event_type="success")) as success by src_ip | where fails > 5 AND success > 0

## Alert Configuration
- Trigger Condition: Number of results > 0
- Severity: Critical
- Schedule: Every 5 minutes
- Alert Type: Scheduled

## Use Case
- Credential compromise following brute-force attack

## Evidence
![Login Success](../results/screenshots/login-success.png)

## Result
A successful login was observed after multiple failed attempts, confirming potential credential compromise.
