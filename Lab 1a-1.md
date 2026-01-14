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
open settings in VM insert screenshot here

6. Verified Ubuntu running with GUI access. Screenshot would show Ubuntu desktop and with Terminal open.
<img width="940" height="587" alt="image" src="https://github.com/user-attachments/assets/2e106d3e-9a6d-4942-99d0-785f19d8ed2d" />

7. Installed Guest Additions inside Ubuntu. Evidence would include successful execution of `sudo apt install virtualbox-guest-utils virtualbox-guest-x11` and reboot.

8. Enabled SSH server (advanced option). Screenshot would show `sudo apt install openssh-server` and `systemctl status ssh` confirming active service. 
Reboot and confirm successful setup

## Reflection Questions 

**1. What challenges did you encounter during the virtual machine setup?** 

One of the main challenges was correctly configuring the virtual machine’s resources, such as allocating enough RAM and storage without affecting the host system’s performance. Choosing the appropriate network mode (NAT or Bridged) also required careful consideration to ensure internet connectivity. Additionally, understanding VirtualBox settings like boot order and installing Ubuntu from an ISO file took some time for first-time setup.


**2. What did you learn about virtualisation tools and their differences?** 

This lab highlighted how virtualisation tools like VirtualBox act as hypervisors, allowing multiple operating systems to run on a single physical machine. Different tools may vary in performance, user interface, and feature sets, such as snapshot support, networking options, and hardware compatibility. VirtualBox stands out for being free, cross-platform, and beginner-friendly, making it suitable for educational use.


**3. How confident do you feel using Ubuntu after completing this lab?** 

After completing the lab, confidence in using Ubuntu increased significantly. Basic tasks such as navigating the desktop, using the terminal, managing files, and installing software using package managers became more familiar. The lab provided hands-on exposure to Linux fundamentals in a controlled environment, reducing hesitation when working with Ubuntu.


**4. In what ways can a virtualised Linux environment help in industry scenarios?** 

A virtualised Linux environment is valuable in industry for software development, testing, and cybersecurity training. It allows teams to safely test applications, simulate servers, and reproduce production environments without risking live systems. Virtual machines also support rapid deployment, system isolation, and cost efficiency, making them ideal for development, DevOps, and IT operations.


**5. What would you do differently if setting up another VM?** 

If setting up another VM, better planning of resource allocation would be done to optimise performance. The network configuration would be chosen based on the intended use case from the start. Installing VirtualBox Guest Additions early would improve display resolution and system integration. Snapshots would also be taken before major changes to allow easy recovery.

## 📝 Optional Reflection/Report Prompts
A short report or reflection answering: 

**1. What are the advantages of using virtual machines for testing and development?** 
VirtualBox Ubuntu allows a safe and remote environment from the host operating system, in this case Windows.
With the virtual environment, we can experiment with Linux commands, install packages and configure services without risking the main system components.
Multiple operating systems with the virtual machines can run concurrently on the same computer, which is useful for development and practice for IT users.

**2. What challenges did you face during installation or network setup?** 
During the Ubuntu installation, some challenges include creating resources such as RAM and memory space, which can affect system performance if set too low.
<img width="940" height="651" alt="image" src="https://github.com/user-attachments/assets/d0b6f9f5-02df-458e-be26-48e6c3a4cfcd" />
Ubuntu did not connect to the internet immediately at the start due to incorrect adapter settings or disabled network drivers, requiring troubleshooting in VirtualBox’s network configuration. 
<img width="1280" height="921" alt="image" src="https://github.com/user-attachments/assets/e73d8456-e217-4ea5-95d7-c42285ebb55f" />


**3. What are the differences between NAT and Bridged networking in VirtualBox?** 
NAT (Network Address Translation) allows Ubuntu to access the internet through the host machine while remaining isolated from the local network.
It is simpler to configure and more secure, making it suitable for basic usage, updates, and learning Linux.

Bridged Networking connects the Ubuntu virtual machine directly to the same network as the host.
The VM receives its own IP address and can communicate with other devices on the network, useful for bi-directional testing, such as hosting servers or testing network services, but it may expose the VM to network security risks.

**4. What did you learn about Linux distributions (distros) from your reading?** 
From reading about Linux distributions, it becomes clear that Ubuntu is one of many Linux distros, each designed for different purposes.
Ubuntu is beginner-friendly, well-documented, and widely supported, making it a good choice for new Linux users.
Other distros may focus on performance, security, or customisation.
