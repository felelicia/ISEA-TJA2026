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

1. Creating Test Files and Directories
<img width="1009" height="139" alt="image" src="https://github.com/user-attachments/assets/a4784eae-d43e-4d6a-b4a9-7213179a93de" />

2. Writing Bash Script
- Create a script /home/ubuntu/testscript.sh:
#!/bin/bash

now=$(date +"%d_%m_%y_%H%M")

cp -R /home/ubuntu/Documents/* /home/ubuntu/backup/

zip -r /home/ubuntu/$now.zip /home/ubuntu/backup/*

Optional: move backup to home for easy access
mv /home/ubuntu/$now.zip /home/ubuntu/

# Transfer backup to cloud server
scp -i /home/ubuntu/key.pem /home/ubuntu/$now.zip ubuntu@<cloud_server_ip>:/home/ubuntu/
3. Granting Execute Permissions

4. Moving the Script to /usr/bin/
- Now we can execute it system-wide:

5. Schedule Cron Job
- Edit /etc/crontab to run script hourly:

- Reload cron:

6. Test Key-Based SSH
- Ensure key.pem has correct permissions:

- Accept remote host fingerprint:

- Confirm scp uploads backup successfully.


## Extension Tasks and Challenges
**Challenge 1. Boot-Time Execution**
- Configure script to run at system startup using rc.local or systemd:

- Alternatively, create a systemd service:

**Challenge 2. MOTD Customisation**
- Install tools

- Edit /etc/motd or ~/.bashrc:

- Personalized messages display at login.
