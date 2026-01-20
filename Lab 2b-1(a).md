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
<img width="1907" height="1067" alt="image" src="https://github.com/user-attachments/assets/5880315c-f116-4ed2-8d93-16b5055a31da" />

4. Connected to the VM using provided SSH command (`ssh -key.pem ubuntu@IP`).
<img width="1356" height="734" alt="image" src="https://github.com/user-attachments/assets/06d7b7ec-bb64-472b-b6e3-6058ecb2e08a" />

   
6. Run `sudo apt update` and install Apache using `sudo apt install apache2`.
<img width="1899" height="1123" alt="image" src="https://github.com/user-attachments/assets/49415ba4-cb10-4858-8ba3-02c72467aade" />
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/a2e0cb7e-bd7e-4618-a8a5-11634392cc4b" />

7. Access the server using its public IP in a browser (via HTTP). With given public IP address: http://54.169.104.145/
<img width="1891" height="1082" alt="image" src="https://github.com/user-attachments/assets/fe4abd7a-a2f4-4b12-8620-a946ad066a95" />

8. Modify `/var/www/html/index.html` using nano and test the changes live.
<img width="1919" height="1139" alt="image" src="https://github.com/user-attachments/assets/f0a570fa-1bbe-43dd-be74-db8570f113d1" />


9. Download and copy files to `/var/www/html/` using `wget` and `sudo cp`.
<img width="1273" height="471" alt="image" src="https://github.com/user-attachments/assets/cab1157e-f6e5-4809-b690-dc9620bb8491" />
<img width="1052" height="466" alt="image" src="https://github.com/user-attachments/assets/85dbdcec-b232-4e3f-bd82-243fcb96d9e8" />

## File Transfer & Permissions 
- Use `wget` to download remote files to your VM.
- Use `sudo cp` to move them into the web directory.
<img width="934" height="315" alt="image" src="https://github.com/user-attachments/assets/36e5ccfe-c9b2-49ba-a6e6-9e0922e7dbe5" />

## Reflection answering:
**- How does cloud hosting compare to local hosting?**
Cloud hosting is easier to navigate as compared to local hosting. Resources such as CPU, storage, and memory can be adjusted on demand without purchasing physical hardware. Cloud providers like AWS include details with minimises human supervision, whereas local hosting requires more money and maintenance, and is more vulnerable to hardware errors. However, local hosting can be cheaper for very small, fixed workloads and offers full physical control over the server.
**- What would you need to secure this server?**
To secure the EC2 Ubuntu server, we need the configuring of AWS Security Groups to allow only necessary ports (22, 80, and 443), disabling password-based SSH logins in favor of key-based authentication, and regularly applying system updates. Backups and intrusion detection tools are also needed to strengthen network security.
**- What alternatives to EC2 would you consider and why?**
Alternatives to EC2 include managed cloud platforms such as AWS Lightsail, Azure Virtual Machines, and Google Compute Engine, which offer simpler configuration and predictable pricing. For application-focused hosting, AWS Elastic Beanstalk reduce infrastructure management by handling scaling and deployments automatically to reduce human workload. For smaller projects or learning environments,DigitalOcean Droplets is suited for beginner-friendly users to experiment virtual servers. The choice depends on the required level of control, scalability, and the user's purpose.
