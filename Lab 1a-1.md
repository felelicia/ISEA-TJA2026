## 1a-1 Virtualisation & Linux Setup 

## Purpose of Lab Activity 1: 
Set up a Linux environment on my personal computer using virtualisation technologies. 

Install VirtualBox, download and boot an Ubuntu-based Linux image. 

Gain exposure to the process of configuring network settings in a virtualised environment. 

## Setup Instructions: 

1. Installing VirtualBox, the VirtualBox application installed and visible in the Start Menu. 
<img width="940" height="449" alt="image" src="https://github.com/user-attachments/assets/83b898b7-4ec8-419d-97de-661a0fcfffd3" />
<img width="97" height="119" alt="image" src="https://github.com/user-attachments/assets/ed711344-5e8c-450d-b9ce-fa5eade0bea7" />

2. Downloaded Ubuntu 25.10 LTS ISO image from the official Ubuntu website. Screenshot shows the downloaded file. 
<img width="1902" height="1079" alt="image" src="https://github.com/user-attachments/assets/db3aa427-eb7f-4d57-9e7e-bfd2e604b90a" />
<img width="724" height="37" alt="image" src="https://github.com/user-attachments/assets/bcea0530-841e-43fe-9845-998d7950ba4b" />

3. Created a new Virtual Machine in VirtualBox named 'vm1' with 2048 MB RAM and 20 GB disk. Screenshot would show VM settings (RAM, boot order, ISO mounted).
<img width="940" height="653" alt="image" src="https://github.com/user-attachments/assets/43fe1a66-030b-4f79-a009-bfc694e6e05d" />
<img width="940" height="430" alt="image" src="https://github.com/user-attachments/assets/6a4545ff-bdd0-47b2-b86c-f7ebb5faf56e" />
<img width="940" height="687" alt="image" src="https://github.com/user-attachments/assets/0ae4f7cc-de9e-4b74-92a7-83998991a682" />
<img width="940" height="687" alt="image" src="https://github.com/user-attachments/assets/6fa500b5-e27a-436f-a261-c7fb15d75aab" />

4. Booted VM in VirtualBox using ISO and installed Ubuntu, with successful login screen of Ubuntu desktop.
<img width="940" height="678" alt="image" src="https://github.com/user-attachments/assets/c054296f-d4ad-4fe4-bbcb-d32b17da6b27" />

5. Configuring network settings to allow NAT internet access, showing VirtualBox Network settings page with NAT selected. 
<img width="1284" height="767" alt="image" src="https://github.com/user-attachments/assets/815cd16e-5c87-46f7-8b13-0f8b71de8581" />

6. Verified Ubuntu running with GUI access. Screenshot would show Ubuntu desktop and with Terminal open.
<img width="940" height="587" alt="image" src="https://github.com/user-attachments/assets/2e106d3e-9a6d-4942-99d0-785f19d8ed2d" />

7. Installed Guest Additions inside Ubuntu. Evidence would include successful execution of `sudo apt install virtualbox-guest-utils virtualbox-guest-x11` and reboot.
<img width="1270" height="785" alt="image" src="https://github.com/user-attachments/assets/98dc9080-e56c-4160-8d92-362b79d4314a" />

8. Enabled SSH server (advanced option). Screenshot would show `sudo apt install openssh-server` and `systemctl status ssh` confirming active service. 
Reboot and confirm successful setup
<img width="1273" height="789" alt="image" src="https://github.com/user-attachments/assets/535f29e4-e189-4fd0-b4db-a3f6a7adc9f2" />
<img width="768" height="179" alt="image" src="https://github.com/user-attachments/assets/5a2ff043-51b7-4880-bbed-187d28acc005" />

## Reflection Questions 
**Challenges faced during installation or network setup:** 
During the Ubuntu installation, some challenges include creating resources such as RAM and memory space, which can affect system performance if set too low.
<img width="940" height="651" alt="image" src="https://github.com/user-attachments/assets/d0b6f9f5-02df-458e-be26-48e6c3a4cfcd" />
Ubuntu did not connect to the internet immediately at the start due to incorrect adapter settings or disabled network drivers, requiring troubleshooting in VirtualBox’s network configuration. 
<img width="1280" height="921" alt="image" src="https://github.com/user-attachments/assets/e73d8456-e217-4ea5-95d7-c42285ebb55f" />

