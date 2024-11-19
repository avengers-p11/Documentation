# **VCS Setup installation guide**

| **Author** | **Created on** | **Version** | **Last updated by** | **Last edited on** | **Reviewer** |
|------------|-------------|-----------|--------------|-------------|-----------|
| Mohit Saini | 18-11-24 | Version 1.1 | Mohit Saini | 18-11-24 |  |

# Table of Contents
1. [Introduction](#introduction)
2. [Types of VCS](#types-of-vcs)
3. [GIT](#git)
4. [GIT Setup Prerequisites](#git-setup-prerequisites)
5. [Git Installation on Ubuntu](#git-installation-on-ubuntu)
   - [Step 1: Update System Packages](#step-1-update-system-packages)
   - [Step 2: Installation of Git](#step-2-installation-of-git)
   - [Step 3: Verify the version of Git](#step-3-verify-the-version-of-git)
   - [Step 4: Configure Git on Ubuntu](#step-4-configure-git-on-ubuntu)
     - [1. Check the public key](#1-check-the-public-key)
     - [2. Create public key](#2-create-public-key)
     - [3. Copy the public key](#3-copy-the-public-key)
     - [4. Click on the Account setting](#4-click-on-the-account-setting)
     - [5. Add New SSH key](#5-add-new-ssh-key)
     - [6. Git clone](#6-git-clone)
6. [Contact Information](#contact-information)
7. [References](#references)


# Introduction

A Version Control System (VCS) is software that facilitates
collaborative work among software developers and enables them to
maintain a comprehensive history of their work.

# Types of VCS

-   **Centralized version control system (CVCS).**

-   **Distributed/Decentralized version control system (DVCS).**

# Git

Git is a distributed version control system that helps developers track
changes in their code, collaborate with others, and manage their source
code efficiently. It is widely used in software development to maintain
project history, resolve conflicts, and enable teamwork

# Git Setup Prerequisites

| **Requirement** | **Details**                                           |
|-----------------|-------------------------------------------------------|
| **OS**          | Ubuntu /Linux-based OS or Windows                     |
| **RAM**         | 1 GB minimum                                          |
| **Disk Space**  | 200 MB for Git installation                           |
| **Processor**   | Any modern processor (Intel or AMD, 1 GHz or faster). |

# [GitHub Installation on Ubuntu]()

This guide provides the steps to install and configure GitHub on Ubuntu.

**Installation Steps**

## Step 1: Update System Packages

``` bash
sudo apt update
```
![image](https://github.com/user-attachments/assets/2e009888-21e6-4070-ad18-917397289fd7)


## Step 2: Installation of Git

**To install Git, use the apt package manager**

``` bash
sudo apt install git -y
```
![image](https://github.com/user-attachments/assets/26a71fbc-4a0d-4ec9-b2aa-8096476e419a)

## Step 3: Verify the version of Git
``` bash
git –version
```
![image](https://github.com/user-attachments/assets/3f58eadd-547d-4691-a24a-80aa2ca910c8)

## Step 4: Configure Git on Ubuntu

Before configuration on local machine of Git your account should be
available on GitHub website.


### Check the public key 

> Go to the ./ssh directory for check public key is available or not
![image](https://github.com/user-attachments/assets/f8000fc6-1ed2-4e0e-ac50-63484f245849)


**If the public key is not available, then create the key**

### Create public key

``` bash
ssh-keygen
```

![image](https://github.com/user-attachments/assets/a8d443b5-a018-431d-a9f4-70125df1387d)


### Copy the public key
copy the public key and go you github account on web browser and singnin. 
![image](https://github.com/user-attachments/assets/eabc3352-0b4f-48b1-a8f6-4dbc341fd617)




### Go to the Account Setting 

Click on right side of your account and click on ssh and gpg key

![image](https://github.com/user-attachments/assets/5b52a234-2281-45da-a7bd-9f98f363e17e)


### Add New SSH key

> Add ssh key by pressing new ssh key button

![image](https://github.com/user-attachments/assets/a220b944-6d2c-4937-afea-c4031d0a2ada)


### Add the title name

Paste the ssh key in key box then click on add ssh key button
![image](https://github.com/user-attachments/assets/145097f4-e9b7-42a9-ba9d-7c6d78c1a868)


### Now click on your repo which want to clone on your local machine. Click on code 🡪 SSH 🡪 copy the code.

![image](https://github.com/user-attachments/assets/3ae3b5aa-5585-4e18-8006-6ffd1fe1b81f)

### Go you system and type the following code which are coped 

## Git Clone


git clone and your repo code

![image](https://github.com/user-attachments/assets/1087ccec-c883-452f-bd23-be8d0ece5db8)

# Contact Information

| **Name**    | **Email address**         |
|-------------|---------------------------|
| Mohit Saini | <it.mohitsaini@gmail.com> |

# References

| **Link** | **Description** |
|-----------------------------------|-------------------------------------|
| [Git installation on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu) | GitHub installation |
| [GitHub SSH Configuraton](https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/GitHub-SSH-Key-Setup-Config-Ubuntu-Linux) | GitHub Configuration |
