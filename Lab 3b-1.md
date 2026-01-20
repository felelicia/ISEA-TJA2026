## Bash Backup Scripting, Cron Jobs & Cloud Export
**Overview of Lab Activity**
This lab introduces Bash scripting for creating file backups, scheduling them using cron jobs, and exporting them to the cloud. Students will use scripting logic to automate folder archiving, apply timestamps to filenames, and securely upload backups to remote servers.

**Learning Objectives**
- Write Bash scripts to automate tasks (backup, compression, cloud transfer).
- Use variables, loops, and conditional expressions in Bash.
- Schedule automated tasks using cron jobs.
- Move scripts to /usr/bin for system-wide availability.
- Export backup files to a cloud server using `scp` and secure keys.
- Explore boot-time execution and user login enhancements (figlet/neofetch).


## Part 1: Create and Run a Basic Bash Script
Creating the script
<img width="936" height="180" alt="image" src="https://github.com/user-attachments/assets/83b82616-46a5-4539-a265-e8333b6d8d66" />

Give execute permission with: chmod 777 somecode.sh
Then execute:
<img width="590" height="67" alt="image" src="https://github.com/user-attachments/assets/c3e5fd32-42f6-4a0b-8bc3-e721de7b4963" />

## Part 2: Using variables
Modify code to:
<img width="955" height="200" alt="image" src="https://github.com/user-attachments/assets/1ab23a1f-f2ad-412e-bc1a-5862df615fa5" />

Executed output
<img width="492" height="47" alt="image" src="https://github.com/user-attachments/assets/4803faf8-45f2-41b6-8f95-bcdec252fa9e" />


## Part 3: Basic Calculations in Bash
Adding some calculations to our previous code:
<img width="944" height="401" alt="image" src="https://github.com/user-attachments/assets/59f4a521-e1bc-4165-a404-4886476090ce" />

Part 4: Modify Code — Summing Numbers in a Loop
Examine the following code snippet written in Bash.
Execution
<img width="495" height="107" alt="image" src="https://github.com/user-attachments/assets/27cd558a-bc64-47b1-9262-1533310c5ae2" />

Modify the code snippet to sum each number in the sequence.
<img width="952" height="330" alt="image" src="https://github.com/user-attachments/assets/8e0d4d60-f3a8-4f27-b7be-103a809bb52e" />
Execute and run
<img width="580" height="297" alt="image" src="https://github.com/user-attachments/assets/93b71bbf-0edf-4beb-834e-f5bcbf79fdb3" />


## Extension Tasks and Challenges
**Challenge 1. Boot-Time Execution**
- Configure script to run at system startup using rc.local or systemd:

- Alternatively, create a systemd service:
<img width="940" height="331" alt="image" src="https://github.com/user-attachments/assets/9c1752cd-1f85-4557-92ef-db32661279c1" />
<img width="940" height="478" alt="image" src="https://github.com/user-attachments/assets/00a820a3-a919-4df8-a650-9798ad5b97b3" />

**Challenge 2. MOTD Customisation**
- Install tools
<img width="940" height="557" alt="image" src="https://github.com/user-attachments/assets/71361604-83b8-46fd-a61c-910f4a3223ec" />

- Edit /etc/motd or ~/.bashrc:
<img width="940" height="134" alt="image" src="https://github.com/user-attachments/assets/4d394075-a0d4-47b7-91fd-7abb6bf97966" />

- Personalized messages display at login.
<img width="940" height="690" alt="image" src="https://github.com/user-attachments/assets/687afe82-4fc3-407a-b646-3bd1d2c766ad" />
