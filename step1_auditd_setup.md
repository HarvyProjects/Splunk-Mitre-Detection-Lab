# Step 1 – Auditd Log Ingestion

## What Was Done:
- Installed and started `auditd` on Ubuntu
- Ran test commands to generate logs:
  - `sudo su`
  - `cat /etc/shadow`
- Ingested `/var/log/audit/audit.log` into Splunk via Add Data interface
- Verified successful ingestion with:
  ```spl
  index=* sourcetype=linux_audit![Screenshot from 2025-04-10 18-01-01](https://github.com/user-attachments/assets/f266b4ba-d392-412f-aaed-60ed3a2683c9)


### Splunk Add Data – Review Page
![Review Page](file:///home/punjabigoku/Pictures/Screenshots/Screenshot%20from%202025-04-10%2017-53-30.png)

### Splunk Search Results – Log Ingestion
![Search Results](file:///home/punjabigoku/Pictures/Screenshots/Screenshot%20from%202025-04-10%2018-01-01.png)
]\
