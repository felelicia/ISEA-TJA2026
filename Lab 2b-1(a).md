🌐 Activity: AWS EC2 Apache Web Server Deployment 
## Lab objective
To use a cloud-based server deployment using Amazon EC2. 
We will be 
- configuring a virtual machine
- installing Apache web server
- serve files online
to understand basic budgeting and cost management in cloud environments.

## Lab set-up and executions
1. Log in to AWS EC2 Console and created a new Ubuntu 20.04 instance (free tier eligible)
<img width="1909" height="1080" alt="image" src="https://github.com/user-attachments/assets/bc17dc6b-5ef0-4c42-a005-2cb03a2e581a" />

2. Named the security group 'ssh-and-web' and allow both SSH and HTTP traffic.
<img width="952" height="1127" alt="image" src="https://github.com/user-attachments/assets/c62b179a-8c73-42ec-a4c7-058ef06235d4" />

3. Downloaded the key pair and saved. To be used for the SSH login via terminal in the next step.
<img width="970" height="570" alt="image" src="https://github.com/user-attachments/assets/1c1209cd-3529-4b95-b8e3-71be22baee5b" />
Successful creation of instance
<img width="940" height="586" alt="image" src="https://github.com/user-attachments/assets/a97a3803-9e04-453e-b727-ad75f0aaa540" />
<img width="1914" height="1083" alt="image" src="https://github.com/user-attachments/assets/b0083922-9468-44f9-a21a-945662043c19" />

4. Connected to the VM using provided SSH command (`ssh -ubuntu kp.pem ubuntu@IP`).
<img width="943" height="390" alt="image" src="https://github.com/user-attachments/assets/86260ec9-7d5c-421a-814f-5a029fdb89dc" />
   
6. Run `sudo apt update` and install Apache using `sudo apt install apache2`.
<img width="1906" height="1083" alt="image" src="https://github.com/user-attachments/assets/c256aa0e-2fdd-4188-b526-f3ec067c142a" />
<img width="1910" height="468" alt="image" src="https://github.com/user-attachments/assets/03c72d99-b9d3-4832-86c3-e6df0699781c" />
Successful installation of Apache <img width="1914" height="1084" alt="image" src="https://github.com/user-attachments/assets/e65d3ae9-4c45-406d-a800-f4029260e07b" />

7. Access the server using its public IP in a browser (via HTTP). With given public IP address: http://47.128.64.33/
<img width="989" height="1137" alt="image" src="https://github.com/user-attachments/assets/c7543e30-692b-438a-839c-c05fa0b66063" />

8. Modify `/var/www/html/index.html` using nano and test the changes live.
<img width="1263" height="771" alt="image" src="https://github.com/user-attachments/assets/880087bd-0d84-44ce-92d3-a2498c8c4f32" />
<img width="1273" height="793" alt="image" src="https://github.com/user-attachments/assets/3a40aa73-676e-47ee-894f-94c4a3e4dd1c" />

9. Download and copy files to `/var/www/html/` using `wget` and `sudo cp`.
<img width="1273" height="471" alt="image" src="https://github.com/user-attachments/assets/cab1157e-f6e5-4809-b690-dc9620bb8491" />

## File Transfer & Permissions 
- Use `wget` to download remote files to your VM.
<img width="1255" height="763" alt="image" src="https://github.com/user-attachments/assets/50928aa2-c73c-4a3b-84ce-fc0dd241756c" />

- Use `sudo cp` to move them into the web directory.
<img width="1250" height="324" alt="image" src="https://github.com/user-attachments/assets/cafbdd57-e4d5-4390-9a5f-f0a84a68124d" />

## Budget and Cost Monitoring in AWS 
- Log into AWS Billing Dashboard via EC2 console. 
- Set up a budget alert to avoid unexpected charges. 
- Review instance charges and terminate unused resources. 
- Avoid launching high-tier or GPU-backed instances.

## Reflection Questions 
- What were the benefits of cloud deployment over local virtualisation? 
- How does Apache serve files, and how did you verify this? 
- What did you learn about file ownership and permissions? 
- What risks are associated with leaving instances running? 
- How would you explain the difference between DNS and /etc/hosts to a client? 

**Reflection file or markdown (reflection.md) answering:**
- How does cloud hosting compare to local hosting?
- What would you need to secure this server?
- What alternatives to EC2 would you consider and why? 
