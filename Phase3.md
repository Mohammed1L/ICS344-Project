  ## Phase 3: Defense with Fail2Ban
Fail2ban: 
![image](https://github.com/user-attachments/assets/764002e1-11c8-428b-8272-b7e9c0b068eb)
Before:
![image](https://github.com/user-attachments/assets/51b2f25b-bf98-4a5c-bbf9-9b263b702ea2)
Kali Attempts:
![image](https://github.com/user-attachments/assets/947bd50f-12cf-4115-a36b-7e4412068252)
Meta blocked the ip after 6 wrong attempts (after):
![image](https://github.com/user-attachments/assets/ce5b0e11-bf45-4623-a3fd-2878cc7affc5)
![image](https://github.com/user-attachments/assets/683b4a0d-bf8d-4a26-ac91-7f76c5a12bcb)

- Installed and configured Fail2Ban on Metasploitable3
- Monitored `/var/log/auth.log`
- Banned attacker IP `192.168.100.79` after 6 failed attempts
- ✅ Confirmed using `fail2ban-client status sshd`

---

## How to Run
1. Metasploitable3 as victim
2. Kali as attacker + Splunk server
3. Forwarder runs on victim and sends logs to Splunk
4. Visualize and defend
