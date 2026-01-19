## Linux Services, SSH, Firewalls & Compression
**Learning Objectives**

This lab uses Linux as a service host. 

Configuration of Apache, SSH, network settings, firewall rules, user accounts, and use ocmpression tools for transferring files.

The activities are collaborative and tests basic system administrationn capabilities. 

1. Apache Web Server Installed
   - Screenshot or terminal output of sudo apt install apache2 and Apache running at http://127.0.0.1.
     
2. Modified index.html Page
- Edited /var/www/html/index.html and screenshot showing personalized content when visited via browser or neighbor’s IP.

3. IP Address Identified and Shared
- Output of ip a showing local and loopback IPs. Partner's IP exchanged and used to access each other's webserver.

4. Nmap Port Scan Results 
- Output screenshot of nmap [partner’s IP] showing open ports before and after Apache is removed.

5. Firewall (UFW) Status and Rules 
Outputs of:
- sudo ufw status verbose before and after enabling
- Port 80 allowed and verified via partner’s Nmap scan

6. SSH Enabled and Tested 
- Output of successful login via ssh to partner’s machine using both default and explicitly declared usernames.

7. New User Created and Verified 
- Command and confirmation of user added via sudo adduser, with /etc/passwd showing new entry.

8. Compression and Decompression Tested 
Screenshots of: 
- tar cf, bzip2, bunzip2, and tar -xvf
- Output of ls -la showing archive size comparison

9 SCP File Transfers Between Machines Output or screenshots showing successful use of scp to copy: • A file • A directory (bonus)

10. /etc/hosts File Modified 
- Screenshot showing added custom hostname (e.g., 8.8.8.8 GoogleEpicDNS) and successful ping GoogleEpicDNS.

11. nslookup and whois Commands Run Output of:
- nslookup google.com
- whois google.com (after installing whois)

12. Public vs Private IP Comparison 
- Screenshot of ip a and result from https://whatismyipaddress.com, with short explanation.

13. Hardware Info Extracted Output from: 
- lsusb
- lspci
- less /proc/cpuinfo with CPU core count identified.

14. Redirected Output Tested 
- Output file from: lsusb > output_of_lsusb, viewed using cat and less.
- File size shown using ls -la.


15. Extension Challenge 1 Completed
-SSH into partner’s machine and create a file on their desktop: Hi_[partner’s name].

16. Extension Challenge 2 Completed 
- Attempt to launch gedit over SSH and note if successful.
- Explain result (X11 forwarding limitation or GUI requirement).

17. Extension Challenge 3 Completed 
- Use scp to copy multiple files between systems; include scp command used and success message or transfer log.

18. Extension Challenge 4 Completed (Bonus) 
- Download top 10 books from Gutenberg, compress them with tar and bzip2, then transfer to partner via scp.

19. Two VMs Networked (External/Online Students) 
- Output of ip a showing both VM IPs, successful ping, and ssh between cloned machines.

20. Reflection Paragraph (Optional)
- A short reflection (100–200 words) on working with Linux networking, SSH, and file compression/transfers.


📝 Suggested Submission Format
· A .zip file containing:
o Screenshots (.png or .jpg)
o Terminal outputs (.txt or screenshots)
o Compressed archive (books.tar.bz2)
o Reflection (.txt or .docx)

o Any .c or .html files edited
