## Lab: Bash Backup Scripting, Cron Jobs & Cloud Export (Expanded to 12 Hands-On Activities)
**Objective**
Learn how to automate system backups using Bash scripting and cron, and export backups to a remote cloud server securely.

## Activity 1: Create Test Files and Directory Structure
Objective: Prepare a sample directory for backup.
<img width="931" height="372" alt="image" src="https://github.com/user-attachments/assets/771db446-b95f-481d-b3fd-d548db2e3e1c" />

## Activity 2: Write a Basic Bash Script
Objective: Begin your backup script.
<img width="715" height="134" alt="image" src="https://github.com/user-attachments/assets/523b3588-fc29-4048-90dd-e6f8cb8ab367" />

## Activity 3: Use Variables and Date Formatting
Objective: Add timestamped filenames.
<img width="681" height="175" alt="image" src="https://github.com/user-attachments/assets/c5b36836-46e0-4865-bafd-e3a88175d978" />

## Activity 4: Archive Files with cp and zip
Objective: Perform backup of files and compress.
installing zip first
<img width="1442" height="826" alt="image" src="https://github.com/user-attachments/assets/d2e2affe-0d50-403d-952e-ee2ba1327ea8" />
<img width="754" height="356" alt="image" src="https://github.com/user-attachments/assets/e819c83c-e50b-46f3-ab1d-c17b80bff2fe" />

## Activity 5: Rename Files Dynamically
Objective: Show use of variables to rename files.
Already handled correctly using mv /home/ubuntu/backup.zip /home/ubuntu/backup_$now.zip

## Activity 6: Set Permissions and Test Script
Objective: Make script executable and run.
<img width="1869" height="1036" alt="image" src="https://github.com/user-attachments/assets/e57636a8-2ee6-410f-a44f-9e996c0c5380" />
<img width="1001" height="67" alt="image" src="https://github.com/user-attachments/assets/629f5a80-915a-4a3e-89ee-b40a301a295b" />

## Activity 7: Move Script to System Path
Objective: Make your script globally executable.

sudo mv /home/ubuntu/testscript.sh /usr/bin/testscript
sudo chown ubuntu /usr/bin/testscript

Test it by running: testscript
<img width="1240" height="1059" alt="image" src="https://github.com/user-attachments/assets/5b978748-c274-4706-95fa-cf1b159421e3" />

## Activity 8: Automate with Cron
Objective: Schedule script every hour.

sudo nano /etc/crontab
Add:

0 * * * * ubuntu /usr/bin/testscript
<img width="952" height="639" alt="image" src="https://github.com/user-attachments/assets/0d893f30-41e5-4dab-8cd3-7aaaaf8c1c3f" />
<img width="928" height="47" alt="image" src="https://github.com/user-attachments/assets/0d674bb8-5111-4a4a-9b00-4f055d8e6b42" />

## Activity 9: Use scp to Export to Cloud
Objective: Transfer backups to remote server.

scp -i ~/cloudkey.pem /home/ubuntu/$now.zip ubuntu@remote-ip:/home/ubuntu/

<img width="938" height="425" alt="image" src="https://github.com/user-attachments/assets/e994d9e4-de72-4127-be2e-738b3e17fafb" />

## Activity 10: SSH into Remote Server as Root
Objective: Accept host key so cron can scp.

sudo ssh -i ~/cloudkey.pem ubuntu@remote-ip

Then exit.
<img width="935" height="211" alt="image" src="https://github.com/user-attachments/assets/8ee8cf82-e6d8-4641-b9ac-e70b3bfd1679" />
