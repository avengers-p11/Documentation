# SSL Implementation

---

| **Author** | **Created on** | **Version** | **Last edited on** | **Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Raman Tripathi  | 20-12-24      | V1.1  | 23-12-24           |  |

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

![Screenshot 2024-12-27 at 3 35 00 PM](https://github.com/user-attachments/assets/285e9522-2419-4c29-bceb-457eeea4a9b0)


### Verify Server Configuration
#### Check Nginx to ensure your domain is served:

![Screenshot from 2024-11-18 23-53-50](https://github.com/user-attachments/assets/422d597b-1f22-4f62-aa27-aca901403e3e)


### Obtain SSL Certificate
#### Run the Certbot command for your domain:

![Screenshot 2024-12-27 at 5 15 35 PM](https://github.com/user-attachments/assets/0dfecdb4-57a4-4efd-8f57-abf3e510234a)



### Update Web Server Configuration
#### Certbot automatically updates the server configuration. Verify:

![Screenshot from 2024-11-19 00-35-12](https://github.com/user-attachments/assets/53cafcb0-65ee-4ce3-9763-be7630a57396)


Look for the listen 443 ssl block added by Certbot.


### Restart Web Server
#### Reload the server to apply changes:

![Screenshot 2024-12-27 at 5 20 05 PM](https://github.com/user-attachments/assets/9744ade3-dc82-4a71-a929-4b648632a997)

### Validate SSL
#### Open https://ua.otmservice.site in a browser and ensure it shows a secure lock icon.


![Screenshot 2024-12-27 at 5 15 59 PM](https://github.com/user-attachments/assets/1de5f0ae-38dc-4119-9e88-62a9b253040e)

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

