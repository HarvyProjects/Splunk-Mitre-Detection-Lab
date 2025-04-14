# Step 1 – Enabling auditd & Ingesting Logs

## Objective:
Prepare the Linux system for detection by enabling detailed logging. The goal is to capture both system-level activity (via `auditd`) and authentication attempts (via `auth.log`) and ingest those logs into Splunk for analysis.

---

## What Was Done:

### 1. Enabled `auditd` (Linux Auditing Daemon)
`auditd` is a built-in Linux service that keeps track of what’s happening behind the scenes, like when someone runs commands such as `curl` or `ssh`. It helps monitor and log system activity for security and troubleshooting.


**Bash Commands:**

This updates my systems package list to make sure I get the latest version: 

`sudo apt update`


This command luanhces the install for `auditd` and its plug ins:

`sudo apt install auditd audispd-plugins -y`

This makes it so `auditd` starts automatically every time the system boots:

`sudo systemctl enable auditd`

Starts the service right now:

`sudo systemctl start auditd`

### 2. Located Key Log Files

    /var/log/audit/audit.log: Logs captured by auditd, used for detecting system-level actions.

    /var/log/auth.log: Captures SSH login attempts, sudo usage, and other authentication events.

These files are critical for both detecting brute force attacks (T1110.001) and HTTP-based command & control via curl (T1071.001).


### 3. Ingested Logs into Splunk

Using the Splunk Web UI:

    Add Data > Monitor > File & Directory

    Pointed to:

        /var/log/auth.log

        /var/log/audit/audit.log

    Set the sourcetypes as:

        auth_log for auth logs

        linux_audit for audit logs


### Splunk Add Data – Review Page  

This screenshot shows the final review screen during the log ingestion process in Splunk. It confirms that the selected log files (`auth.log` and `audit.log`) are correctly configured for monitoring and ready to be indexed.
![Review Page](images/Screenshot%20from%202025-04-10%2017-53-30.png)
### Splunk Search Results – Log Ingestion
This screenshot verifies that `/var/log/auth.log` and `/var/log/audit/audit.log` were successfully added as monitored file inputs in Splunk, enabling detection of login attempts and system command executions.
![Search Results](images/Screenshot%20from%202025-04-10%2018-01-01.png)
