## Lab Learning Objectives
- Launch a cloud VM and configure firewall access (ports 22, 80, 443).
- Install and run a basic Apache web server.
- Purchase and manage a domain name via a registrar.
- Link domain to VM public IP using DNS A record.
- Verify domain resolution using ping and nslookup.
- Obtain and install a TLS certificate via Let’s Encrypt.
- Understand DNS propagation, redundancy, and failover behaviour.

## Lab Setup and Tasks
- Launch Ubuntu VM using Amazon EC2, Azure, or DigitalOcean.
- Ensure inbound ports 22 (SSH), 80 (HTTP), and 443 (HTTPS) are open.
- Install Apache: `sudo apt install apache2`.
- Record public IP address of the VM. Access in browser to confirm Apache page.
- Register a domain (Namecheap, GoDaddy, Cloudflare, Route 53, etc).
- Create an A record pointing your domain to the public IP of your server.
- Wait for DNS propagation and test with browser, ping, and nslookup.
- Install Certbot: `sudo apt install certbot python3-certbot-apache`.
- Run: `sudo certbot --apache` to generate and install the certificate.
- Check site: HTTPS lock icon should appear in browser.

## Activity 1: Domain, DNS
**1. Domain Name Registered**
- A registered domain from Duckdns.org/domain
<img width="947" height="678" alt="image" src="https://github.com/user-attachments/assets/bfcb9435-aa17-4f73-b92b-122a7ff241a8" />

**2. A Record Created**
- DNS A record pointing your domain to your VM's public IP

**3. Apache Installed**
- Apache2 running and accessible on port 80
<img width="1244" height="413" alt="image" src="https://github.com/user-attachments/assets/acc4a247-e59d-4d4e-8165-13b072702dde" />
<img width="720" height="132" alt="image" src="https://github.com/user-attachments/assets/7103218b-9da7-44ce-a583-30a47f0ce27d" />
<img width="933" height="374" alt="image" src="https://github.com/user-attachments/assets/32fd4be1-2301-49e2-a8f8-bb9c584cf51b" />

**4. Public IP to Domain Mapping Verified**
- Test using nslookup, dig, and browser to confirm DNS is working
<img width="825" height="611" alt="image" src="https://github.com/user-attachments/assets/09751efb-79af-4249-a808-e5bbe62e5ae9" />
<img width="819" height="451" alt="image" src="https://github.com/user-attachments/assets/2577263a-4d12-4471-a1e4-7fd04d33d89b" />

**5. Screenshot: Apache Welcome Page via Domain**
- Open http://yourdomain.com and capture the Apache welcome page
<img width="1899" height="1090" alt="image" src="https://github.com/user-attachments/assets/944d9091-a89c-4997-a05d-184c745c81a9" />

**6. Screenshot: DNS Test Output**
- Output of nslookup yourdomain.com or dig
<img width="825" height="611" alt="image" src="https://github.com/user-attachments/assets/09751efb-79af-4249-a808-e5bbe62e5ae9" />

## Activity 2: Let’s Encrypt TLS Certificate Setup
You secure your domain with HTTPS by installing a free Let's Encrypt TLS certificate using Certbot.
**1. Certbot Installed**
- Certbot and Apache plugin installed via Snap
<img width="1850" height="677" alt="image" src="https://github.com/user-attachments/assets/c5669640-d307-42e7-b772-4bc477d6d0bf" />
<img width="504" height="42" alt="image" src="https://github.com/user-attachments/assets/ba138cd5-0506-4ecd-900b-1994862cda64" />
installation confirmation

**2. HTTPS Enabled on Domain**
- https://yourdomain.com should show a secure lock icon
<img width="919" height="527" alt="image" src="https://github.com/user-attachments/assets/b07496fa-c5c9-4264-ac3c-3b1ea2c9295d" />

**3. Valid TLS Certificate**
- Certificate issued by Let’s Encrypt (viewable in browser)

**4. Screenshot: HTTPS with Lock Icon**
- Browser screenshot showing lock and certificate issuer

**5. Screenshot Success Message: Certbot**
- Output of sudo certbot --apache command

**6. Screenshot: Renewal Dry-Run Output**
- Output of sudo certbot renew --dry-run showing success

**certbot installed via snap**
<img width="1891" height="655" alt="image" src="https://github.com/user-attachments/assets/663750d9-dc63-4ce7-9218-810a96906ede" />

**certificate successfully issued**
<img width="915" height="107" alt="image" src="https://github.com/user-attachments/assets/18e68b2c-2c2e-4c50-bce3-e6324252e575" />
