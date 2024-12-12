# Version Control System (Github)Setup: POC

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 28-11-24      | Neelesh  Kumar             | 28-11-24           |  | | |     

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
![Screenshot from 2024-11-29 13-54-04](https://github.com/user-attachments/assets/125d6413-ac24-4d1c-9f1c-37138468e095)
![Screenshot from 2024-11-29 14-00-16](https://github.com/user-attachments/assets/fc47ab97-1b46-4b91-84be-7f90ffa08699)


2. Create a GitHub account at [github.com](https://github.com)

3. Create a new repository on GitHub:
   - Click the "+ or addnew" icon in the top-right corner
   - Select "New repository"
   - Name your repository
   - click on private(to keep your repository private)
   - Click "Create repository"
  
   
![Screenshot from 2024-11-29 13-49-02](https://github.com/user-attachments/assets/49646b46-922f-40de-bb01-d06aac917a47)



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
![Screenshot from 2024-11-29 14-18-43](https://github.com/user-attachments/assets/c8977e0e-68a1-4459-b276-22deb2f4cecc)
![Screenshot from 2024-11-29 14-18-52](https://github.com/user-attachments/assets/3b9d4f66-c610-4dbc-a5de-2ffcc450d874)
![Screenshot from 2024-11-29 14-18-58](https://github.com/user-attachments/assets/96c7a3e2-872f-46f5-9ad9-9943409f2253)
![Screenshot from 2024-11-29 14-21-55](https://github.com/user-attachments/assets/def53c9a-8f3e-4654-8eaa-4c9b47a40d6d)
![Screenshot from 2024-11-29 14-22-16](https://github.com/user-attachments/assets/01ea0678-3b9c-47b4-9e23-baaa8d32cb48)
![Screenshot from 2024-11-29 14-22-24](https://github.com/user-attachments/assets/a6b95bc6-3e7a-4080-8797-ef309bad9b81)
![Screenshot from 2024-11-29 14-22-35](https://github.com/user-attachments/assets/b021eff6-a792-4c24-9bef-3df02c08f4e6)
![Screenshot from 2024-11-29 14-22-59](https://github.com/user-attachments/assets/e7757b2a-5875-4d53-b6a5-bfc3513f42d4)
![Screenshot from 2024-11-29 14-23-56](https://github.com/user-attachments/assets/cbaa5c9f-67e9-4ecc-aa77-9797262bf703)
![Screenshot from 2024-11-29 14-25-37](https://github.com/user-attachments/assets/94508a9f-f6d7-485a-9d06-b665450e60f9)
![Screenshot from 2024-11-29 14-26-12](https://github.com/user-attachments/assets/b0f89fb0-ab02-4843-be4b-f0e59e72a60f)

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



