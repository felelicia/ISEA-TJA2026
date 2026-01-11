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

## Experimentation and Advanced Tasks
- Who issued the SSL certificate for murdoch.edu.au and csn.murdoch.edu.au?
- Can you use a subdomain to point to another student’s server?
- Create two A records with different IPs. Observe failover behaviour.
- Shutdown server and observe DNS delay in failover. Discuss why.
- Reflect on DNS load balancing, round-robin, and high-availability use cases.

## Budget and Cost Monitoring
- Visit EC2 Billing Dashboard to monitor charges.
- Set a budget and create usage alerts under AWS Budgets.
- Terminate unused instances to avoid unnecessary charges.
- Avoid running expensive instance types (e.g. with GPUs) if not required.
- Disable domain auto-renew if not continuing use post-semester.

## Activity 1: Domain, DNS
**1. Domain Name Registered**
- A registered domain from Namecheap, GoDaddy, Route 53, or similar: Duckdns.org/domain

**2. A Record Created**
- DNS A record pointing your domain to your VM's public IP

**3. Apache Installed**
- Apache2 running and accessible on port 80

**4. Public IP to Domain Mapping Verified**
- Test using nslookup, dig, and browser to confirm DNS is working

**5. Screenshot: Apache Welcome Page via Domain**
- Open http://yourdomain.com and capture the Apache welcome page

**6. Screenshot: DNS Test Output**
- Output of nslookup yourdomain.com or dig

**7. (Optional) Subdomain Experiment**
- A record pointing a subdomain (e.g., test.yourdomain.com) to another IP and screenshot of test result

## Activity 2: Let’s Encrypt TLS Certificate Setup
You secure your domain with HTTPS by installing a free Let's Encrypt TLS certificate using Certbot.
**1. Certbot Installed**
- Certbot and Apache plugin installed via Snap

**2. HTTPS Enabled on Domain**
- https://yourdomain.com should show a secure lock icon

**3. Valid TLS Certificate**
- Certificate issued by Let’s Encrypt (viewable in browser)

**4. Screenshot: HTTPS with Lock Icon**
- Browser screenshot showing lock and certificate issuer

**5. Screenshot Success Message: Certbot**
- Output of sudo certbot --apache command

**6. Screenshot: Renewal Dry-Run Output**
- Output of sudo certbot renew --dry-run showing success

**7 (Optional) Expired Certificate Simulation**
- Screenshot or explanation of what happens when the cert isn't renewed (if explored)

## Reflection Questions
- What is the role of DNS in Internet presence?
- Why does DNS propagation take time?
- How does Let’s Encrypt validate domain ownership?
- What are the risks if TLS is not configured on a public-facing site?
- What could happen if you leave your cloud VM running for months?
- Output of sudo certbot renew --dry-run showing success

**7. (Optional) Expired Certificate Simulation**
- Screenshot or explanation of what happens when the cert isn't renewed (if explored)
