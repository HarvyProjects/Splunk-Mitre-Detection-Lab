## Step 3 – Simulated Brute Force Attack (MITRE T1110.001)

### Objective:
Simulate a brute force attack on a Linux system and verify that the resulting failed SSH login attempts are captured and ingested into Splunk for detection.

---

### What Was Done:

1. Installed and started SSH server:
   ```bash
   sudo apt update
   sudo apt install openssh-server -y
   sudo systemctl enable ssh
   sudo systemctl start ssh
2. Simulated brute force attack
3. ```bash
   for i in {1..10}; do ssh fakeuser@localhost; done
4. Verified logs in Linux terminal
5. ```bash
   sudo grep "Failed password" /var/log/auth.log
6.Added /var/log/auth.log to Splunk

7.Verified in Splunk using:
### Screenshot – Brute Force Logs in Splunk  
![Failed Password Logs](images/failed_password.png)





