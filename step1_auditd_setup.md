# Step 1 – Auditd Log Ingestion

## What Was Done:
- Installed and started `auditd` on Ubuntu
- Ran test commands to generate logs:
  - `sudo su`
  - `cat /etc/shadow`
- Ingested `/var/log/audit/audit.log` into Splunk via Add Data interface
- Verified successful ingestion with:
  ```spl
  index=* sourcetype=linux_audit


  ### Splunk Add Data – Review Page
![Review Page](images/splunk_review_setup.png)

### Splunk Search Results – Log Ingestion
![Search Results](images/splunk_log_results.png)
