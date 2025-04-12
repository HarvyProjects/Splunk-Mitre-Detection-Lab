# Splunk Mitre Detection Lab
This project simulates and detects adversary behavior using Splunk and maps it to the MITRE ATT&CK framework.


**Lab Workflow Overview** 

**Step 1:**	*Enabling auditd & Ingesting Logs*

**Step 2:**	*Simulating Brute Force and curl Attacks*

**Step 3:**	*Writing SPL Detection Queries*

**Step 4:**	*Building a Detection Dashboard*

**Step 5:**  *Creating Alerts* 


**Environment** 

- **Host OS**: Ubuntu 
- **Log Collection Tools**: auditd or Sysmon for Linux
- **SIEM Platform**: Splunk 
- **Scripting/Automation**: Bash
- **Attack Simulation**: Atomic Red Team 




---

## Project Summary

This project simulates real-world attacker behavior on a Linux system and uses Splunk to detect and visualize the activity. Each detection is aligned to a specific MITRE ATT&CK technique. The goal was to gain hands-on experience in threat detection, log ingestion, and SPL development — while building something directly relevant to SOC and Threat Analyst roles.

---

## What I Learned

- How to ingest system and auth logs into Splunk from Ubuntu
- Simulated attacks using bash commands (SSH brute force + curl)
- Wrote SPL queries to detect T1110.001 and T1071.001 techniques
- Created Splunk dashboards to visualize and monitor threats
- Documented the project like a real-world analyst or engineer would

---

## Tools & Skills Used

- **Splunk Enterprise (free version)**
- **Linux (Ubuntu)**
- **auditd / auth.log**
- **Bash scripting**
- **MITRE ATT&CK Framework**
- **Search Processing Language (SPL)**
- **Threat Detection & Dashboards**
