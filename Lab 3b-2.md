## Cloud Technology Alternatives
**Class Activity Overview**
- Self-Discover the many other Cloud alternatives for the various Lab activities

## Additional Server Service: MariaDB
**System Preparation**

Update the system and install basic prerequisites. 

sudo apt update && sudo apt upgrade -y 
<img width="1916" height="1138" alt="image" src="https://github.com/user-attachments/assets/bf2ac2c1-0b84-4470-a68a-9bc59d48e18b" />

sudo apt install -y curl wget gnupg lsb-release ca-certificates 
<img width="920" height="369" alt="image" src="https://github.com/user-attachments/assets/cbf0592b-bb82-4298-8d71-00081b915bce" />

(Optional but recommended) 

sudo reboot 
<img width="941" height="268" alt="image" src="https://github.com/user-attachments/assets/9bce774d-df50-42e9-9486-f809af8bb7ff" />

Install MariaDB (Database Server) 

Step 1: Install MariaDB Server sudo apt install -y mariadb-server mariadb-client 
<img width="1912" height="1086" alt="image" src="https://github.com/user-attachments/assets/e9b40a4c-bf36-4e2a-a507-71936fbd303c" />

Step 2: Start and enable MariaDB 

- sudo systemctl start mariadb
- sudo systemctl enable mariadb 
<img width="941" height="692" alt="image" src="https://github.com/user-attachments/assets/6e97fb8e-36cd-4f93-9526-f45b5cf7cae1" />

Step 3: Secure MariaDB installation 

sudo mysql_secure_installation 

Recommended answers: 
- Set root password → Y
- Remove anonymous users → Y
- Disallow remote root login → Y
- Remove test database → Y
- Reload privilege tables → Y
<img width="926" height="1121" alt="image" src="https://github.com/user-attachments/assets/817a2374-6d7f-4ba0-adbf-1b270daf5701" />

Step 4: Verify MariaDB 

sudo mysql -u root -p 


Inside MariaDB shell: 

SHOW DATABASES; 
EXIT;
<img width="930" height="576" alt="image" src="https://github.com/user-attachments/assets/b6cd13eb-01c8-4e58-8edf-c614cdcedc0b" />
