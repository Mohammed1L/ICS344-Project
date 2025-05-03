# ICS344-Project
# ICS344 Project: SSH Attack & Defense (Metasploitable3 + Splunk)

## Group Info
- Group Number: 6
- Members:
  - ALHATHAL, MOHAMMAD MAHER 202021080
  - ALDAHASH, MOHAMMED KHALED 202156870
  - ALZAHRANI, BASEL SAEED 202178710
  - Work distribution:
  - Worked together in all phases

---

## Phase 1: Attacking SSH
![image](https://github.com/user-attachments/assets/d369498e-775c-43a8-b4c5-fd65d749397a)
![image](https://github.com/user-attachments/assets/58488a31-4a1f-4235-8028-3c944f453563)
Ping is working 
![image](https://github.com/user-attachments/assets/44a557f7-75a2-4221-82f0-fbf71c270f72)
![image](https://github.com/user-attachments/assets/3cd4143f-8174-48e4-966b-6d4ddcd8990a)
Attacker Machine Ping is working
![image](https://github.com/user-attachments/assets/0fc3821f-402b-4b76-9bb0-f2bec5926478)
![image](https://github.com/user-attachments/assets/a31eb6bd-20ec-486c-adf7-258279ac39ec)
Service that can be attacked
### Task 1.1 - Metasploit Attack
- Exploit: `auxiliary/scanner/ssh/ssh_login`
- Target: Metasploitable3 @ `192.168.100.112`
- Credential: `vagrant:vagrant`
- Result: Shell access gained (proof in screenshots)
![image](https://github.com/user-attachments/assets/6d7402aa-f4d8-4ebe-a320-6f735fdef009)

### Task 1.2 - Python Brute-Force Script
- Wrote custom script using `paramiko`
- Tried usernames: `admin, root, test, user, vagrant`
- ✅ Successfully logged in with `vagrant`
- 📸 Screenshot of failures and success included
![image](https://github.com/user-attachments/assets/d43b43a0-7dff-4821-90aa-92d0f0fd3b27)
![image](https://github.com/user-attachments/assets/d05861ab-b0c4-4f2e-a8f3-586cf62d05f2)

---

## Phase 2: SIEM Analysis with Splunk
![image](https://github.com/user-attachments/assets/6de14177-9284-4aef-862a-314e0a464ead)
Forwarding: 
![image](https://github.com/user-attachments/assets/88fce607-2c7d-4a0f-8cc0-082371f048bc)

- Installed Splunk on Kali and Forwarder on Metasploitable3
- Monitored `/var/log/auth.log`
- Confirmed live log forwarding via:
  ```spl
  index=* source="/var/log/auth.log"
![image](https://github.com/user-attachments/assets/8a447a87-648e-4cb7-a7a0-08f44600bccf)
![image](https://github.com/user-attachments/assets/c9e6f5aa-1141-469e-ac52-2ec354b09598)
Failed Attempts:
![image](https://github.com/user-attachments/assets/432929ac-e9fd-4d90-ad13-c6708e26fcef)
Visualization: 
![image](https://github.com/user-attachments/assets/392e5185-3754-4c1f-8692-e432b9c544ef)

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

---
