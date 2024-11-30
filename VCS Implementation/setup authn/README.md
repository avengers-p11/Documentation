
# VCS Authentication Setup

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 29-11-24      | Neelesh  Kumar             | 29-11-24           |  | | |     



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
6. [Troubleshooting](#troubleshooting)
7. [References](#references)

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

## 2.Personal Access Tokens (PATs)

   Generate a Token:
        Log in to your VCS provider.
        Navigate to Settings > Developer Settings > Personal Access Tokens.
        Create a token with the necessary scopes (e.g., repo access).

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

## Best Practices

   Use SSH for Automation: It's secure and avoids storing passwords.
   Avoid Sharing Tokens: Treat tokens like passwords; do not expose them.
   Rotate Tokens Regularly: Update PATs periodically to minimize security risks.
   Enable Two-Factor Authentication (2FA): Add an extra layer of security.
   Use Scoped Tokens: Limit the scope of PATs to specific operations.

## Troubleshooting
   SSH Permission Denied:
        Ensure the correct key is added to your VCS.
        Verify the SSH agent is running:

        eval "$(ssh-agent -s)"
        ssh-add ~/.ssh/id_rsa
        
   Token Expiry Issues:
        Regenerate and replace expired tokens.
        Use a credential manager to avoid re-entering tokens.

## References

   GitHub Authentication Guide
   GitLab SSH Keys Setup
   Bitbucket Authentication


##  Contact Information

| Name| Email Address      |
|-----|--------------------------|
| Neelesh kumar | nilesh.rajput.snaatak@mygurukulam.co || GitHub | URL |
|----------|---------|
|  devneelesh921  |  https://github.com/devneelesh921  |








