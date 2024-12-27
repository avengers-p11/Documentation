
# SSL POC
---

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 15-11-24      | Neelesh  Kumar             | 28-11-24           |khushi malhotra  | | |

---

## Table of Content
- [Introduction](#introduction)
- [Why Use Certbot Over Other Tools?](#why-use-certbot-over-other-tools)
- [Pre-requisities](#pre-requisites) 
- [Environment Setup](#environment-setup)
- [Additional Notes](#additional-notes)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)

## Introduction
The goal of this document is to demonstrate a **Proof of Concept (POC)** for setting up SSL certificates on a domain using **Certbot**, a free and automated certificate authority by **Let's Encrypt**. SSL ensures secure, encrypted communication between a user's browser and the server, protecting sensitive data and enhancing trust.

---

# Why Use Certbot Over Other Tools?

Certbot offers several advantages, making it a preferred choice for managing SSL certificates:

1. **Free and Open-Source:** Certbot is entirely free, with no hidden costs, as it uses Let's Encrypt, a free certificate authority.
2. **Automation:** Automates the process of obtaining, installing, and renewing SSL certificates, reducing manual intervention.
3. **Ease of Use:** Provides simple commands for generating and managing SSL certificates, even for beginners.
4. **Wide Compatibility:** Works seamlessly with popular web servers like Apache and Nginx on multiple operating systems.
5. **Community Support:** As a widely used tool, it has an active community and comprehensive documentation to assist users.
6. **Secure and Trusted:** Certificates issued by Let's Encrypt via Certbot are recognized and trusted by all major browsers.
7. **Environmentally Friendly:** Promotes HTTPS adoption globally without incurring extra costs or complexity.

Compared to other SSL management tools, Certbot stands out for its simplicity, automation, and zero-cost approach.

---
 
## Pre-requisites
Ensure the following before proceeding:
1. **Domain Name**: A domain pointing to your server's public IP via DNS A/AAAA records.
2. **Web Server**: A running web server such as Apache or Nginx on a Linux-based system.
3. **Server Access**: SSH access to the server with `sudo` privileges.
4. **Certbot**: Available for installation through the server’s package manager.

---

## Environment Setup

### Step1: Install Certbot
Run the following commands to install Certbot and its dependencies:

#### For Nginx
```sh
sudo apt update
sudo apt install certbot python3-certbot-nginx -y
```

#### For Apache
```sh
sudo apt update
sudo apt install certbot python3-certbot-apache -y
```

---

### Step2: Configure Web Server

#### Nginx Example

1. **Create a new Nginx server block:**
```sh
sudo nano /etc/nginx/sites-available/default
```

2. **Add the following configuration:**
```sh
server {
listen 80;
server_name example.com; # Edit this to your domain name
client_max_body_size 100M;
 
  index index.html index.php;
  root /var/www/html/example.com/;  # change your code directory

   access_log  /var/log/nginx/example.com/access.log;           #Add ssl access log file on the server
   error_log   /var/log/nginx/example.com/error.log;             #Add ssl error log file on the server

 }
```

3. **Create directory for access.log and error.log file in infinitygurdian.shop:**
```sh
mkdir /var/log/nginx/example.com/
```

4. **Test and reload Nginx:**
```sh
sudo nginx -t
sudo systemctl reload nginx
```

#### Apache Example

1. **Enable the necessary Apache modules:**
```sh
sudo a2enmod ssl rewrite
```

2. **Edit the virtual host file:**
```sh
sudo nano /etc/apache2/sites-available/example.com.conf
```

3. **Add the following virtual host block:**
```sh
<VirtualHost *:80>
    ServerName example.com
    ServerAlias www.example.com
    DocumentRoot /var/www/example
</VirtualHost>
```

4. **Enable the site and reload Apache:**
```sh
sudo a2ensite example.com
sudo systemctl reload apache2
```

---

### Step3: Obtain SSL Certificates

Run Certbot to request SSL certificates and automatically configure your web server:

#### For Nginx:
```sh
sudo certbot --nginx -d example.com -d www.example.com
```

#### For Apache:
```sh
sudo certbot --apache -d example.com -d www.example.com
```

#### What Certbot Does:
- Validates your domain ownership via HTTP challenge.
- Automatically configures your web server to use the SSL certificate.

---

### Step4: Verify SSL Certificate
- Open your domain in a browser: https://example.com
- Look for the padlock icon to confirm the SSL certificate is active.

---

### Step5: Test SSL Renewal(Optional)
Certbot sets up automatic renewal for your SSL certificates. To test this, run the following command:

```sh
sudo certbot renew --dry-run
```
If successful, your certificates are automatically renewed without manual intervention.

---

## Additional Notes
>- Certbot uses Let's Encrypt, which provides certificates valid for 90 days. Regular renewals are required.
>- Certificates are stored in `/etc/letsencrypt/live/`.

---

## Conclusion
The POC demonstrates the use of Certbot to set up SSL certificates for a domain with Nginx or Apache web servers. Certbot automates domain validation, certificate installation, and server configuration. It also supports automatic certificate renewal. Following the outlined steps ensures secure HTTPS access to your domain with minimal manual intervention.

---

## Contact Information

| Name| Email Address      |
|-----|--------------------------|
| Neelesh kumar | nilesh.rajput.snaatak@mygurukulam.co || GitHub | URL |
|----------|---------|
|  devneelesh921  |  https://github.com/devneelesh921  |

---

## References

| Reference Name       | Description                                  | Link                                                                 |
|-----------------------|----------------------------------------------|----------------------------------------------------------------------|
| Certbot Documentation | Official documentation for Certbot usage.   | [Certbot Documentation](https://certbot.eff.org/docs/)              |
| Let's Encrypt         | Free SSL/TLS certificates provider.         | [Let's Encrypt](https://letsencrypt.org/)                           |
| SSL Documentation     | Detailed documentation on SSL               | [SSL Documentation](https://github.com/MyGurukulam-p11/Documentation/blob/Pritam_scrum59/SSL/Documentation/README.md)       |
