# Secure socket layer (SSL) Documentation

| **Author** | **Created on** | **Version** | **Last edited on** | **Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Raman Tripathi  | 20-12-24      | V1.1  | 20-12-24           |  |


## Table of Contents

- [Introduction](#introduction)
- [Why SSL ?](#why-ssl)
- [SSL Advantages](#ssl-advantages)
- [Disadvantages of SSL](#disadvantages-of-ssl)
- [How it is work ?](#how-ssl-works)
- [How to get SSL](#how-to-get-ssl)
- [Different SSL provider](#different-ssl-provider)
- [Comparison between SSL providers ](#comparison-between-ssl-providers)
- [Recommendation](#recommendation)
  
## Introduction

SSL (Secure Sockets Layer) is an encryption protocol that secures data transfer between a server and a client. When SSL is implemented, data is transferred in an encrypted form, making it difficult for unauthorized individuals to understand or intercept it. Nowadays, the upgraded version of SSL, called TLS (Transport Layer Security), is used, which is even more secure and efficient.



## Why SSL ?

Originally, data on the web was transmitted in plaintext, making it easy for anyone who intercepted the message to read it. For example, if someone logged into their email account, their username and password would travel across the Internet unprotected.

SSL was created to solve this problem and protect user privacy. By encrypting data between a user and a web server, SSL ensures that anyone who intercepts the data sees only a scrambled mess of characters. This keeps the user’s login credentials safe, visible only to the email service.

## SSL Advantages 
   1. **Data Encryption:**
SSL encrypts the data exchanged between the client and server, ensuring that sensitive information, such as passwords and credit card details, is protected from eavesdropping.

   2. **Authentication:**
SSL verifies the identity of the website you're connecting to, preventing man-in-the-middle attacks and ensuring that you are communicating with the legitimate server.

   3. **Trust and Credibility:**
SSL enhances user trust by displaying a padlock icon and "https" in the URL. This signals to users that the site is secure and safe to use.

   4. **SEO Benefits:**
Search engines like Google prioritize websites with SSL, improving their search rankings and overall visibility in search results.

## Disadvantages of SSL

1. **Performance Overhead**  
   SSL/TLS encryption and decryption require additional computational resources. This can introduce some latency, especially on high-traffic websites or servers with limited resources, potentially affecting site performance.

2. **Cost**  
   While there are free SSL certificates (like Let’s Encrypt), many SSL certificates, especially extended validation (EV) certificates, can come with significant costs, particularly for larger organizations or businesses needing higher levels of security and trust.

3. **Complexity in Implementation**  
   Configuring SSL correctly requires technical expertise. Misconfiguration can lead to security vulnerabilities, such as weak encryption, certificate errors, or SSL/TLS handshake issues.


## How SSL works ?
![image](https://github.com/user-attachments/assets/54c7e181-4a15-4946-ad29-b66a3cc91389)


 #### **TCP Handshake:**
 - Before SSL begins, the client and server establish a TCP connection.
 - The TCP handshake ensures reliable communication between the two parties. This is done in three steps:
  - The client sends a SYN (synchronize) packet to the server.
  - The server responds with a SYN-ACK (synchronize-acknowledge) packet.
  - The client replies with an ACK (acknowledge) packet, completing the handshake.

#### **Certificate Check:**
- The server sends its SSL/TLS certificate to the client. This certificate contains:
- The server's public key.
- Information about the server's identity (domain name, organization details, etc.).
- The certificate's validity period.

#### **Key Exchange (Asymmetric Encryption):**
- Asymmetric Encryption in Action:

    - The client generates a random session key, which will be used for symmetric encryption during data transmission.
    - The client encrypts the session key using the server’s public key (found in the certificate).

- Server Decrypts the Session Key:

    - The server uses its private key to decrypt the encrypted session key.

    - Now, both the client and server share the same session key securely.


#### **Data Transmission (Symmetric Encryption):**

- Secure Data Transmission:

    - All data transmitted between the client and server is now encrypted with the session key.

## How to get SSL ? 

- ## Prerequisites
1. **A domain name:** Ensure the domain points to your server (via DNS A or CNAME records).
2. **Server access:** Root or sudo access to your server.
3. **Web server:** Apache or Nginx installed and running.
4. **Certbot installed:** Let’s Encrypt’s tool for automating SSL certificate management.

---

## Step 1: Install Certbot
#### On Ubuntu/Debian
```bash
sudo apt update
sudo apt install certbot python3-certbot-nginx
```
#### On CentOS/RHEL
```bash
sudo yum install epel-release
sudo yum install certbot python3-certbot-nginx
```

#### Step 2:Obtain an SSL Certificate
```bash
sudo certbot --nginx -d yourdomain.com
```

#### Step 3: Verify Installation
Access your website using https://<Domain-name> to confirm the SSL certificate is working.

#### Step 4:  Renewal Process
```bash
sudo certbot renew

```
## Different SSL provider 


- Let's Encrypt  
- DigiCert  
- GlobalSign  
- Comodo (Sectigo)  

## Comparison between SSL providers 
| **Criteria**         | **Let’s Encrypt**                               | **DigiCert**                                  | **GlobalSign**                                | **Comodo (Sectigo)**                           |
|----------------------|-------------------------------------------------|----------------------------------------------|----------------------------------------------|------------------------------------------------|
| **Pricing**          | Free                                            | High (premium)                               | High (premium)                               | Low to Moderate                                |
| **Certificate Types**| DV (Domain Validation)                          | DV, OV (Organization Validation), EV (Extended Validation) | DV, OV, EV                                    | DV, OV, EV                                     |
| **Issuance Speed**   | Very fast (automated)                          | Moderate (depends on validation level)       | Moderate (depends on validation level)       | Fast (especially DV)                           |
| **Support**          | Limited (community-based)                      | Excellent (24/7 support for paid customers)   | Excellent (24/7 support for paid customers)   | Good (24/7 support for paid customers)         |
| **Wildcard Support** | Yes (free)                                      | Yes (paid)                                   | Yes (paid)                                    | Yes (affordable)                               |


## Recommendation
To use Let’s Encrypt easily, set up Certbot to automatically renew your certificate every 90 days. Keep an eye on the expiration dates to make sure everything stays active. Make your website secure by using TLS 1.2+ and enabling HSTS to force HTTPS. If you have multiple subdomains, you can use a wildcard certificate to cover them all.


## Contact information

| Name| Email Address      |
|-----|--------------------------|
| Raman Tripathi | raman.tripathi.snaatak@mygurukulam.co |

| GitHub | URL |
|----------|---------|
|  Raman-tripathi07  |  https://github.com/Raman-tripathi07  |

## References

|Description  |   Link |
|:------------------:|:-------------------:|
| Working of SSL | https://youtu.be/0yw-z6f7Mb4?si=4SVd-CKbyLVlqplA
| Let’s Encrypt | https://letsencrypt.org/
| Introduction of SSL | https://www.geeksforgeeks.org/secure-socket-layer-ssl
