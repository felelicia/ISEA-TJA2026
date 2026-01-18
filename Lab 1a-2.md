## 1a-2 Ubuntu Desktop and Command Line Familiarisation 

## Purpose of Lab Activity 2: 
- Understand the Ubuntu desktop and basic command-line interface (CLI). 
- Use basic terminal commands for navigation, file handling, and user management. 
- Explore system information, process monitoring, and networking tools. 
- Understand software installation via GUI, APT, and source compilation. 
- Compare public/private IPs and experiment with host configuration. 
- Develop beginner C program and compile using GCC.

##  Activity: Ubuntu GUI & CLI Familiarisation + Software Installation Methods 

**📘 Objective**

Develop working knowledge of the Ubuntu Linux environment via GUI and CLI. Learn software installation methods, basic networking, file permissions, and compiling from source. 
## GUI Familiarisation Proof 
Screenshots of:  
• Firefox opened and working  
<img width="1278" height="906" alt="image" src="https://github.com/user-attachments/assets/6e82777b-f870-49de-8d22-f48958b222f3" />

• LibreOffice with text typed  
<img width="1291" height="906" alt="image" src="https://github.com/user-attachments/assets/d410d616-ea45-483a-97be-51b4323fa555" />

• File manager navigating directories
<img width="1285" height="907" alt="image" src="https://github.com/user-attachments/assets/f15d6c27-9e26-48f9-a9f7-33160b98940e" />

• Software installed via Ubuntu Software Centre 
<img width="1494" height="939" alt="image" src="https://github.com/user-attachments/assets/11b7f737-9d6f-46da-8d78-979c9df2b9f6" />

## Terminal Commands Output 
Evidence of CLI exploration, e.g., output screenshots or logs for:  
• ps -e, top, ls, ls -la, ls -alt  
<img width="1203" height="757" alt="image" src="https://github.com/user-attachments/assets/0d08856f-42ff-4546-bd8f-a37fe46508aa" />
<img width="1202" height="758" alt="image" src="https://github.com/user-attachments/assets/5e23a7d5-0662-407d-9168-04e48d1a1d90" />
<img width="1205" height="757" alt="image" src="https://github.com/user-attachments/assets/f8ffb190-2077-4607-b79a-61e034cde811" />

• File creation and editing with touch, nano, gedit, cat, less 
touch
<img width="1208" height="764" alt="image" src="https://github.com/user-attachments/assets/5e732081-e60a-42a7-8271-07cc0e449027" />
<img width="435" height="92" alt="image" src="https://github.com/user-attachments/assets/95a228db-7385-41c5-8726-dcceb5334be8" />
<img width="1205" height="763" alt="image" src="https://github.com/user-attachments/assets/2abf6e73-19e5-4eee-9f47-e9cda8dafd22" />
<img width="903" height="214" alt="image" src="https://github.com/user-attachments/assets/d73fd0fb-b3c7-4379-a123-5e8a6ce9ed20" />
cat
less

## File Operations Practiced 
Screenshot or terminal output showing use of:  
• cp, mv, rm and file listing with size (ls -lah) 
## System Information Commands 
Output or screenshots of:  
• uname -a, lsb_release -a, hostnamectl, /proc/cpuinfo 
## User Privilege Experiment 
Terminal output showing:  
• whoami, sudo whoami  
• Attempting to adduser without and then with sudo 
## Networking Tests 
Evidence of:  
• ip a output  
• Successful ping to local IP or 8.8.8.8  
• Screenshot of Ubuntu network settings window 
## /etc/hosts File Edited 
Screenshot of:  
• sudo nano /etc/hosts editing  
• Successful ping GoogleEpicDNS 
## DNS Lookup Performed 
Output of:  
• nslookup google.com  
• whois google.com 
## Public vs Private IP Reflection 
Screenshot of ip a and result from https://whatismyipaddress.com/ with 1–2 lines explaining the difference 
## Hardware Info Commands 
Output or screenshot for:  
• lsusb, lspci, less /proc/cpuinfo  
• Comparison with GUI “About this Computer” 
## Output Redirection Practiced 
Screenshot of:  
• Command lsusb > output_of_lsusb  
• Viewing output with less, cat  
• Deleting it with rm 
## Software Installed (3 Ways) 
Evidence of all three:  
• SaaS (e.g. login to Office 365 or Google Docs in browser)  
• Binary download (e.g., .deb file like Chrome/Opera)  
• Repository install via Ubuntu Software Centre 
## Command-Line Install via apt 
Evidence of:  
• sudo apt update and sudo apt upgrade  
• sudo apt install vlc or other package  
• Optional: less /etc/apt/sources.list 
## Source Code Compilation 
Deliverables:  
• File hello_world.c with source code  
• Compilation using gcc hello_world.c -o hello_world_executable  
• Execution with ./hello_world_executable  
• If needed: chmod 777 for permission fix 
## Reflection Summary (Paragraph) 
A short reflection (100–200 words) covering:  
• GUI vs CLI experience  
• Software installation methods pros/cons (SaaS, repo, manual, source)  
• Your preference as a user and as a future software developer 

## 📝 Suggested Submission Format: 
- A single .zip file containing:
- Screenshots (named clearly by step)
- Terminal output logs (optional)
- Source code file: hello_world.c
- Compiled file: hello_world_executable (optional)
- Written reflection in .txt, .md, or .docx 
