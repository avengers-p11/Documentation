# SSL Implementation

---

| **Author** | **Created on** | **Version** | **Last edited on** | **Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Raman Tripathi  | 20-12-24      | V1.1  | 20-12-24           |  |

---

## Table of Content
- [Introduction](#introduction)
- [Pre-requisities](#pre-requisities)
- [Implementation Steps](#implementation-steps)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [Reference](#reference)

## Introduction
This document explains about the implementation of SSL certificate on the domain as per POC. Here we are using certbot which an open source SSL Certification authority and the server we are using is Nginx server.

---

## Pre-requisities

- **Domain Name:** Domain DNS configured to point to the server (A/AAAA records).
- **Web server:** Install nginx server on your VM.
---

## Implementation Steps

### Install Certbot
#### Update system packages and install Certbot:

![Screenshot from 2024-11-18 23-41-31](https://github.com/user-attachments/assets/412c0007-2e54-4cb9-afe6-10be45e89eba)

### Verify Server Configuration
#### Check Nginx to ensure your domain is served:

![Screenshot from 2024-11-18 23-53-50](https://github.com/user-attachments/assets/422d597b-1f22-4f62-aa27-aca901403e3e)


### Obtain SSL Certificate
#### Run the Certbot command for your domain:

![Screenshot from 2024-11-18 23-57-50](https://github.com/user-attachments/assets/854bb35e-dc9f-48b5-ad5f-94fc03321f2c)


### Update Web Server Configuration
#### Certbot automatically updates the server configuration. Verify:

![Screenshot from 2024-11-19 00-35-12](https://github.com/user-attachments/assets/53cafcb0-65ee-4ce3-9763-be7630a57396)


Look for the listen 443 ssl block added by Certbot.


### Restart Web Server
#### Reload the server to apply changes:

![Screenshot from 2024-11-18 23-55-37](https://github.com/user-attachments/assets/f118f19d-0df5-4b52-b267-b2f6fe183be8)


### Validate SSL
#### Open https://infinitygurdians.shop in a browser and ensure it shows a secure lock icon.

![Screenshot from 2024-11-19 00-21-41](https://github.com/user-attachments/assets/2ea0e567-6c38-4021-9c28-3a9b4efe0ffa)


---

## Conclusion
The domain now uses SSL encryption provided by Let’s Encrypt, improving security and user trust. The process is free and includes automated renewal for uninterrupted protection.

---

## Contact Information

| Name| Email Address      |
|-----|--------------------------|
| Raman Tripathi | raman.tripathi.snaatak@mygurukulam.co |

| GitHub | URL |
|----------|---------|
|  Raman-tripathi07  |  https://github.com/Raman-tripathi07  |

---

## Reference

| Reference Name       | Description                                  | Link                                                                 |
|-----------------------|----------------------------------------------|----------------------------------------------------------------------|
| SSL POC | POC on how you can set up a SSL for your Domain | [SSL POC](https://github.com/MyGurukulam-p11/Documentation/tree/Kaustubh_Scrum-60/DNS_&_SSL_Management/DNS/SSL_POC#ssl-poc)             |
| SSL Documentation     | Detailed documentation on SSL               | [SSL Documentation](https://github.com/MyGurukulam-p11/Documentation/blob/Pritam_scrum59/SSL/Documentation/README.md)       |

