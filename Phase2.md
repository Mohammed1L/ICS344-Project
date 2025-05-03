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
