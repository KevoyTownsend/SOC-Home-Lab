# SOC-Home-Lab
Home lab using Wazuh, pfSense and Wazuh Agent
Project Overview
This project demonstrates the design and operation of a small-scale Security Operations Center (SOC) home lab focused on log collection, threat detection, and alert investigation. Using Wazuh as a SIEM, the lab simulates an SSH brute-force attack against a monitored Linux endpoint and documents how the activity was detected and analyzed.
The objective of this project is to showcase practical SOC workflows, including alert triage, correlation, and investigation, rather than tool configuration alone.

Lab Architecture
Core components:
- Wazuh Manager – Centralized log analysis and alerting
-	Wazuh Agent (Linux) – Monitored endpoint
-	pfSense Firewall – Network perimeter and logging
-	Attacker Machine (Kali Linux) – Simulated threat actor
All systems were deployed in a virtualized lab environment.

 Objectives
-	Configure centralized log collection using Wazuh
-	Monitor authentication activity on a Linux endpoint
-	Simulate an SSH brute-force attack
-	Detect malicious behavior through SIEM alerts
-	Investigate and correlate events to confirm attack patterns

Attack Simulation
An SSH brute-force attack was conducted from a Kali Linux system targeting the monitored Linux endpoint. Multiple failed authentication attempts were generated in rapid succession to emulate common real-world attack behavior.

Detection & Alerting
Wazuh successfully generated alerts indicating repeated SSH authentication failures consistent with brute-force activity. The alerts were triggered based on event frequency and pattern recognition rather than a single failed login attempt.

Investigation & Analysis
The alert was investigated using Wazuh’s event correlation and contextual analysis features. By reviewing surrounding events, the following indicators were observed:
-	Multiple failed SSH login attempts
-	Events occurring milliseconds apart
-	Repeated triggering of the same authentication-related rule
-	Consistent targeting of the same monitored host
Note: The source.ip field was not consistently populated due to log parsing limitations. Despite this, attack confirmation was achieved through correlation of timestamps, event frequency, and agent-level context.

Evidence (Screenshots)
Screenshots included in this repository demonstrate:
-	Attack execution from the attacker machine
-	Wazuh alert generation for SSH brute-force activity
-	Contextual analysis showing repeated failed authentication attempts

Key Skills Demonstrated
-	SIEM log ingestion and monitoring
-	Security alert triage and investigation
-	Event correlation and pattern analysis
-	Linux authentication monitoring
-	SOC-style documentation and reporting

Limitations & Future Improvements
-	Custom rules and decoders were not implemented to maintain focus on SOC investigation workflows
-	Future enhancements may include:
  -	Custom detection tuning
  -	Automated response actions
  - Integration with additional threat intelligence sources

Disclaimer
This project was conducted in a controlled lab environment for educational and portfolio purposes only. No production systems were involved.
