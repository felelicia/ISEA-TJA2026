## Linux Services, SSH, Firewalls & Compression
**Learning Objectives**

This lab uses Linux as a service host. 

Configuration of Apache, SSH, network settings, firewall rules, user accounts, and use ocmpression tools for transferring files.

The activities are collaborative and tests basic system administrationn capabilities. 

1. Apache Web Server Installed
- Screenshot or terminal output of sudo apt install apache2 and Apache running at http://127.0.0.1.
<img width="940" height="576" alt="image" src="https://github.com/user-attachments/assets/bce9e09b-cf9d-4e39-9f9c-e1350c7ccb36" />
<img width="1282" height="782" alt="image" src="https://github.com/user-attachments/assets/4535c9ae-cbe3-4303-8772-69dfa3b10f97" />
     
2. Modified index.html Page
- Edited /var/www/html/index.html and screenshot showing personalized content when visited via browser or neighbor’s IP.
<img width="1284" height="791" alt="image" src="https://github.com/user-attachments/assets/826096cb-bb57-45dd-b639-c3f973a4ec9e" />

3. IP Address Identified and Shared
- Output of ip a showing local and loopback IPs. Partner's IP exchanged and used to access each other's webserver.
<img width="825" height="319" alt="image" src="https://github.com/user-attachments/assets/2920bb13-fe50-4382-a906-a4ca6cf14c65" />

4. Nmap Port Scan Results 
- Output screenshot of nmap [partner’s IP] showing open ports before and after Apache is removed.

5. Firewall (UFW) Status and Rules 
Outputs of:
- sudo ufw status verbose before and after enabling
- Port 80 allowed and verified via partner’s Nmap scan
<img width="682" height="241" alt="image" src="https://github.com/user-attachments/assets/7f1c26a5-3a70-42df-9415-8d15299ad570" />

6. SSH Enabled and Tested 
- Output of successful login via ssh to partner’s machine using both default and explicitly declared usernames.

7. New User Created and Verified 
- Command and confirmation of user added via sudo adduser, with /etc/passwd showing new entry.
<img width="758" height="756" alt="image" src="https://github.com/user-attachments/assets/265513dc-f0e6-4e36-a3a6-267e7246f35c" />

8. Compression and Decompression Tested 
Screenshots of: 
- tar cf, bzip2, bunzip2, and tar -xvf
<img width="883" height="389" alt="image" src="https://github.com/user-attachments/assets/e35693fe-6104-4a71-a049-72bb8e540373" />

- Output of ls -la showing archive size comparison
<img width="588" height="578" alt="image" src="https://github.com/user-attachments/assets/421b689f-8358-4c72-97ac-c94c8170c84a" />

9. SCP File Transfers Between Machines
- Output or screenshots showing successful use of scp to copy:
- A file
- A directory (bonus)
<img width="685" height="142" alt="image" src="https://github.com/user-attachments/assets/6e9a3a10-5cd4-4e73-aac4-3edf0bcc92f7" />
<img width="598" height="653" alt="image" src="https://github.com/user-attachments/assets/993bd39d-3521-45f5-8139-76d20d294ed8" />

10. /etc/hosts File Modified 
- Screenshot showing added custom hostname (e.g., 8.8.8.8 GoogleEpicDNS) and successful ping GoogleEpicDNS.
<img width="1201" height="762" alt="image" src="https://github.com/user-attachments/assets/3d311be8-4849-42eb-8230-9b85f232793a" />

11. nslookup and whois Commands Run Output of:
- nslookup google.com
<img width="700" height="514" alt="image" src="https://github.com/user-attachments/assets/5da0c13c-a9a6-49d9-aeb4-697c6658a44d" />
- whois google.com (after installing whois)
<img width="1121" height="767" alt="image" src="https://github.com/user-attachments/assets/e0f03706-1128-4816-9084-a20097c12c76" />

12. Public vs Private IP Comparison 
- Screenshot of ip a and result from https://whatismyipaddress.com, with short explanation.
<img width="830" height="275" alt="image" src="https://github.com/user-attachments/assets/ec39cd2e-0b11-4472-9858-e3e2ae0777ef" />
<img width="1264" height="777" alt="image" src="https://github.com/user-attachments/assets/d81e26d5-ca90-4e0e-8219-4dd7503f4f63" />
The private IP address is used internally for communication within a local network or virtual environment and is not directly accessible from the internet. 

The public IP address is exposed externally to the internet, assigned by an ISP or cloud provider. Network Address Translation (NAT) allows multiple devices with private IP addresses to share a single public IP when accessing external networks.

13. Hardware Info Extracted Output from: 
- lsusb
<img width="516" height="73" alt="image" src="https://github.com/user-attachments/assets/11d0bc0e-cf9a-48df-9309-fdb202ad7293" />

- lspci
<img width="873" height="221" alt="image" src="https://github.com/user-attachments/assets/3d1e7ca6-c24f-498d-8e21-877e35084036" />

- less /proc/cpuinfo with CPU core count identified.
<img width="1215" height="766" alt="image" src="https://github.com/user-attachments/assets/b36b7f98-c392-42e4-a012-05d827e23a1c" />

14. Redirected Output Tested 
- Output file from: lsusb > output_of_lsusb, viewed using cat and less.
<img width="1206" height="776" alt="image" src="https://github.com/user-attachments/assets/40d41583-b941-4c54-b3ac-ac4963a01264" />
<img width="521" height="89" alt="image" src="https://github.com/user-attachments/assets/4282e040-c0c7-412a-ad36-075e4e44068a" />
<img width="1209" height="776" alt="image" src="https://github.com/user-attachments/assets/a3675066-f025-4038-938d-9f480491dfb2" />

- File size shown using ls -la.
<img width="529" height="39" alt="image" src="https://github.com/user-attachments/assets/b8619ca0-865d-43a6-91c5-f5ea2f9c8459" />

15. Extension Challenge 1 Completed
-SSH into partner’s machine and create a file on their desktop: Hi_[partner’s name].
<img width="903" height="571" alt="image" src="https://github.com/user-attachments/assets/7a4495a6-4249-495e-a725-6b1e11d07376" />

16. Extension Challenge 2 Completed 
- Attempt to launch gedit over SSH and note if successful.
<img width="518" height="53" alt="image" src="https://github.com/user-attachments/assets/f77927a7-c465-446a-9aed-89cd09ae5ff9" />

- Explain result (X11 forwarding limitation or GUI requirement).
This happens because gedit is a graphical application requires GUI to display windows, SSH only forwards CLI. To run GUI applications remotely, X11 forwarding must be enabled.

17. Extension Challenge 3 Completed 
- Use scp to copy multiple files between systems; include scp command used and success message or transfer log.
<img width="577" height="52" alt="image" src="https://github.com/user-attachments/assets/26a786b1-0211-4ecd-8a38-8cda37ad5944" />

o Reflection (.txt or .docx)

o Any .c or .html files edited
