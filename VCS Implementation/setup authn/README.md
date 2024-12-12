
# VCS Authentication Setup

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 29-11-24      | Neelesh  Kumar             | 29-11-24           |shreya jaiswal  | | |     



---

## Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Authentication Methods](#authentication-methods)
4. [Setup Instructions](#setup-instructions)
    - [SSH Key Authentication](#ssh-key-authentication)
    - [Personal Access Tokens (PATs)](#personal-access-tokens-pats)
    - [OAuth Authentication](#oauth-authentication)
5. [Best Practices](#best-practices)
6. [References](#references)

---

## Introduction

Authentication in VCS ensures only authorized users can access or modify repositories. This document focuses on popular methods like SSH keys, Personal Access Tokens (PATs), and OAuth to secure repository access.

---

## Prerequisites

- A Git-based VCS (e.g., GitHub, GitLab, Bitbucket, etc.)
- Git installed locally (`git --version` to check).
- An active account on your VCS provider.

---

## Authentication Methods

1. **SSH Key Authentication:** Securely authenticate using SSH keys.
2. **Personal Access Tokens (PATs):** Use tokens instead of passwords for HTTPS.
3. **OAuth Authentication:** Authenticate via third-party OAuth providers.

---

## Setup Instructions

### SSH Key Authentication

 ## 1.Generate an SSH Key Pair:
   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
Follow the prompts to save the key (default location: ~/.ssh/id_rsa).

   Add the SSH Key to Your VCS:
       Copy the public key:
     ```
     cat ~/.ssh/id_rsa.pub
       ```
   Go to your VCS provider and add the key under SSH Keys in your profile settings.

Test SSH Connection:
```
    ssh -T git@github.com
```
  
 Replace github.com with your VCS provider's domain.
 ![Screenshot from 2024-11-29 14-22-16](https://github.com/user-attachments/assets/ffb69990-396a-4561-8edb-bdbf0ff41c06)
![Screenshot from 2024-11-29 14-22-24](https://github.com/user-attachments/assets/5c355f31-023a-4379-aece-933e85846095)
![Screenshot from 2024-11-29 14-22-35](https://github.com/user-attachments/assets/55db4e84-001b-4935-8cf3-f7b24593e2f8)
![Screenshot from 2024-11-29 14-22-59](https://github.com/user-attachments/assets/d1cf378a-93ca-48b4-b469-34fce553a30a)
![Screenshot from 2024-11-29 14-23-56](https://github.com/user-attachments/assets/889089c2-08d3-417f-af27-98dc1724285f)

![Screenshot from 2024-11-29 14-25-37](https://github.com/user-attachments/assets/4a87e0a5-d964-4b84-bde7-404e4652bb3d)

## 2.Personal Access Tokens (PATs)

   Generate a Token:
        Log in to your VCS provider.
        Navigate to Settings > Developer Settings > Personal Access Tokens.
        Create a token with the necessary scopes (e.g., repo access).
![Screenshot from 2024-12-12 12-01-54](https://github.com/user-attachments/assets/e8a145cb-6442-4954-9270-5c47f2ff784f)
![Screenshot from 2024-12-12 12-02-05](https://github.com/user-attachments/assets/9cd740cb-c63c-4ad7-aafc-e5e95d2a4998)
![Screenshot from 2024-12-12 12-02-12](https://github.com/user-attachments/assets/6a1eca1a-fdf4-4eea-b0c7-dbcd71108cc8)

   Use the Token: Replace your password with the token when cloning or pushing via HTTPS:

    git clone https://github.com/username/repository.git

   Enter the token when prompted for the password.

## 3.OAuth Authentication
`
    Enable OAuth Apps:
        Go to Settings > Applications in your VCS provider account.
        Register a new OAuth application.

  `  Authenticate via Third-Party Tools:
        Use tools like GitHub CLI or your IDE's built-in OAuth integration.
        Example for GitHub CLI:

        gh auth login
![Screenshot from 2024-12-12 12-02-24](https://github.com/user-attachments/assets/adf6e4cb-3134-4c85-b4d2-451a358d15d7)

## Best Practices

# Security Best Practices for Automation

| Best Practice                     | Description                                                                  |
|-----------------------------------|------------------------------------------------------------------------------|
| **Use SSH for Automation**        | Secure method that avoids storing passwords.                                 |
| **Avoid Sharing Tokens**          | Treat tokens like passwords; ensure they are not exposed.                    |
| **Rotate Tokens Regularly**       | Periodically update Personal Access Tokens (PATs) to minimize security risks. |
| **Enable Two-Factor Authentication (2FA)** | Add an additional layer of security for better protection.                   |
| **Use Scoped Tokens**             | Limit the scope of PATs to specific operations for enhanced security.         |



## References

| Platform          | Guide                                                                 |
|--------------------|----------------------------------------------------------------------|
| **GitHub**         | [https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/about-authentication-to-github](#https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/about-authentication-to-github)                                    |




##  Contact Information

| Name| Email Address      |
|-----|--------------------------|
| Neelesh kumar | nilesh.rajput.snaatak@mygurukulam.co || GitHub | URL |
|----------|---------|
|  devneelesh921  |  https://github.com/devneelesh921  |








