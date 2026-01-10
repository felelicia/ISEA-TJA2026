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
• LibreOffice with text typed  
• File manager navigating directories  
• Software installed via Ubuntu Software Centre 
## Terminal Commands Output 
Evidence of CLI exploration, e.g., output screenshots or logs for:  
• ps -e, top, ls, ls -la, ls -alt  
• File creation and editing with touch, nano, gedit, cat, less 
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
