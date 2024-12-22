# Version Control System (Github)Setup: POC

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 28-11-24      | Neelesh  Kumar             | 28-11-24           |Shikha tripathi  | | |     

## Table of Contents
1. [Purpose](#purpose)
2. [Pre-requisites](#pre-requisites)
   - [System Requirements](#system-requirements)
   - [Dependencies](#dependencies)
3. [Architecture](#architecture)
4. [Step-by-step installation of GitHub](#step-by-step-installation-of-github)
5. [Conclusion](#Conclusion)
6. [Contact Information](#contact-information)
7. [References](#References)


## Purpose
This Poc demonstrates how to set up and use GitHub as a Version Control System. GitHub provides a centralized platform for collaborative software development, offering features like version control, issue tracking, and project management.

## Pre-requisites

### System Requirements

| Hardware Specifications | Minimum Recommendation |
|-------------------------|------------------------|
| RAM                     | 1 GB                   |
| Disk                    | 8 GB free space        |
| OS                      | Windows 10, macOS 10.14, Ubuntu 18.04 or later |

### Dependencies

| Name    | Version | Description |
|---------|---------|-------------|
| Git     | 2.34    | Distributed version control system |


## Architecture

![Screenshot from 2024-12-12 11-44-36](https://github.com/user-attachments/assets/5b5af6b5-47db-4c7e-887d-04d5439ebc9f)


## Step-by-step installation of GitHub

1. Install Git:
   ```bash
   # Windows (using Chocolatey)
   choco install git

   # macOS (using Homebrew)
   brew install git

   # Ubuntu
   sudo apt-get update
   sudo apt-get install git
   ```
![Screenshot from 2024-12-22 16-22-56](https://github.com/user-attachments/assets/ff7b9b1b-f752-4536-bdab-c676268a8afd)


2. Create a GitHub account at [github.com](https://github.com)

3. Create a new repository on GitHub:
   - Click the "+ or addnew" icon in the top-right corner
   - Select "New repository"
   - Name your repository
   - click on private(to keep your repository private)
   - Click "Create repository"
  
   
![Screenshot from 2024-12-22 16-25-12](https://github.com/user-attachments/assets/b449d827-8a23-40c3-b789-446b6d3e32d0)



4. Set up local repository:
```bash
 mkdir vcs-setup-repo
 cd vcs-setup-repo/
 echo "# vcs-setup-poc-" >> README.md
 git init
 git add README.md 
 git status
 git commit -m "this is my first vcs setup"
 git branch -M main
 git remote add origin https://github.com/devneelesh921/vcs-setup-poc-.git
 git push -u origin main
 cd .ssh
 cat id_rsa.pub
 git remote add sshorigin git@github.com:devneelesh921/vcs-setup-poc-.git
 git push sshorigin main
 
```
![Screenshot from 2024-12-22 16-28-37](https://github.com/user-attachments/assets/294d4f15-9bcc-4788-8448-357b65b7a500)
![Screenshot from 2024-12-22 16-31-14](https://github.com/user-attachments/assets/8ac26578-ca6c-4e95-996a-3dfc417a3de0)
![Screenshot from 2024-12-22 16-32-18](https://github.com/user-attachments/assets/553c665f-345f-4b60-96ed-10be9c453b3f)
![Screenshot from 2024-12-22 16-33-36](https://github.com/user-attachments/assets/bb3e28e8-7af7-474a-97a3-17318da1ff0c)
![Screenshot from 2024-12-22 16-34-20](https://github.com/user-attachments/assets/9acadc71-4b05-42e8-98d4-0f58d2dcccc8)
![Screenshot from 2024-12-22 16-34-57](https://github.com/user-attachments/assets/2429fa9f-5923-41d5-8912-2be9ec3c83a3)
![Screenshot from 2024-12-22 16-38-27](https://github.com/user-attachments/assets/d0c338d5-0f14-49e1-9b76-f94842942323)
![Screenshot from 2024-12-22 16-39-11](https://github.com/user-attachments/assets/43f4077a-d7fe-4df5-a5de-cd1083f73d0d)
![Screenshot from 2024-12-22 16-40-35](https://github.com/user-attachments/assets/0d067949-4395-4d0c-9132-43a8c84a26a3)
![Screenshot from 2024-12-22 16-41-01](https://github.com/user-attachments/assets/ad9691f7-57b2-45f8-945c-9240a9f34b7e)

## Conclusion

In this Proof of Concept (PoC), we demonstrated the basic process of creating a repository, cloning it, and pushing changes. This workflow allows developers to track modifications, collaborate smoothly, and ensure an organized approach to managing project files and updates. By following these steps, teams can streamline their development efforts and enhance productivity across the board.

## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Neelesh kumar | nilesh.rajput.snaatak@mygurukulam.co || GitHub | URL |
|----------|---------|
|  devneelesh921  |  https://github.com/devneelesh921  |

## References
|Links | Description|
|-------|-----------|
|https://www.geeksforgeeks.org/introduction-to-bitbucket/?ref=ml_lbp| For  Bitbucket |
|https://www.geeksforgeeks.org/introduction-to-github/?ref=ml_lbp| For Github|
|https://www.tutorialspoint.com/gitlab/gitlab_introduction.htm|For Gitlab|



