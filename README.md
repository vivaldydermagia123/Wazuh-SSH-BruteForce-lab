# Wazuh-SSH-BruteForce-lab
this project demonstrating SSH Bruteforce detection using Wazuh SIEM

## Objective
Simulate an SSH brute force attack and detect it using Wazuh SIEM to demonstrate SOC monitoring and analysis skills.

## Environment
- Ubuntu 24.04
- Wazuh all-in-one (Manager, Indexer, Dashboard)
- OpenSSH Server
- Single VM lab

## Attack Simulation
- Multiple SSH login attempts using invalid and valid users
- Manual brute force attempts via SSH client

## Detection
- Log source: /var/log/auth.log
- Wazuh Rules:
  - 5710: Attempt to login using a non-existent user (Level 5)
  - 5715: Multiple authentication failures (Level 8)

## Analysis
- Repeated failed authentication attempts indicate a brute force attempt
- Events are mapped to MITRE ATT&CK technique T1110 (Brute Force)

## Response Recommendation
- Block source IP using firewall or Wazuh Active Response
- Enforce SSH hardening:
  - Disable root login
  - Enable fail2ban
  - Use key-based authentication

## Evidence
See screenshots folder for attack and detection evidence.
