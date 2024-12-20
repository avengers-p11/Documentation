
# **POC to Setup Jenkins**

| **Author** | **Created on** | **Version** | **Last updated by** | **Last edited on** | **Reviewer L0** |
|------------|-------------|-----------|--------------|-------------|-----------|
| Pravesh Kumar | 06-12-24 | Version 1.1 | Pravesh Kumar | 20-12-24 |  |


## **Table of Contents**

1. [Introduction](#introduction)
2. [**What is ansible**](#what-is-ansible)
3. [**Why ansible**](#why-ansible)
4. [Pre-requsities](#pre-requisties)
5. [Steps for Ansible role](#steps-for-ansible-role)
6. [Conclusion](#conculsion)
7. [Contact Information](#contact-information)
8. [References](#references)

 
 
 ## Introduction

Ansible roles are basically playbooks broken up into a known file structure.


## What is ansible
Ansible Roles are a powerful way to organize and reuse automation tasks. They provide a standardized structure for grouping related tasks, variables, files, templates, and handlers. This modular approach makes your playbooks more manageable, reusable, and easier to maintain.


## Why ansible?
Ansible Roles are a powerful mechanism for organizing and reusing automation tasks.

 ## Pre-requisties

|Pre-requisite	|Description|
|-----|------|
|Ansible| Ensure Ansible is installed on your system.|
|pip and boto3| Install pip for Python 3 and then install the boto3 library, which is required for AWS interactions.|
|AWS CLI| Install and configure the AWS CLI to authenticate and interact with AWS services.|


### Steps for ansible role

**Steps 1. Update your OS**
```
sudo apt update
```
![Screenshot 2024-12-06 at 7 12 34 PM](https://github.com/user-attachments/assets/25d580c3-3065-4dee-8b33-5ff39691554d)


**Steps 3. Ansbilbe installed**
```
sudo apt install ansible
```

**Steps 4. Verify ansible version**

```
ansible --version
```
![Screenshot 2024-12-06 at 7 11 11 PM](https://github.com/user-attachments/assets/4a49dfd9-2041-46f7-bb47-6a972e524275)



**Steps 5. Create ansible role** 

```
ansible-galaxy init Jenkins_role
```
![Screenshot 2024-12-06 at 6 59 21 PM](https://github.com/user-attachments/assets/75b3f8ce-4251-4f9c-9ae4-c79a469837e8)



**Steps 6. Change the direcotry current to my role**
```
cd Jenkins_role
```
![Screenshot 2024-12-06 at 7 00 36 PM](https://github.com/user-attachments/assets/ca46cc2a-bf3b-4a25-8ee0-71c5e745c984)


**Steps 7. After configure my role direcorty structure**
```
tree
```
![Screenshot 2024-12-06 at 6 56 41 PM](https://github.com/user-attachments/assets/7bcc2a48-c45e-43ce-bb62-815769064168)



**Steps 8. pip and boto3 installation**

### pip
Its a package manager for Python used to install and manage Python libraries. It is essential for managing dependencies in Python projects. 

###boto3
The AWS SDK (Software Development Kit) for Python, enabling developers to interact with various AWS services like EC2, S3, Lambda, and more from Python applications.

```
sudo apt install python-pip
```
![Screenshot 2024-12-20 at 8 47 19 PM](https://github.com/user-attachments/assets/0b712784-8f42-46a6-9b8d-26d08a3b8a96)



```
pip install boto
```

```
sudo apt install python3-boto
```

![Screenshot 2024-12-06 at 7 21 07 PM](https://github.com/user-attachments/assets/05cf6b57-9a20-494c-a9fe-3ecc28eba1b4)



## Run the ansible role**
```
ansible-playbook -i aws_ec2.yml <playbook-name>
```
```
ansible-playbook -i aws_ec2.yml /home/ubuntu/jenkins/install_jenkins/tests/test.yml
```

![Screenshot 2024-12-20 at 8 40 32 PM](https://github.com/user-attachments/assets/35686fe1-4ed5-4ca2-9ada-d4397ba66b8d)


## Conclusion
Roles are a way to make code in playbooks reusable by putting the functionality into generalized libraries that can be then used in any playbook as needed.

## Contact Information

| **Name** | **Email address**            | **Github ID**
|----------|-------------------------------|-------------------|
| Pravesh Kumar    |  pravesh.kumar611@gmail.com           | Pravesh899 |

---

## References

| **Link** | **Description** |
|----------------------------------------------------|--------------------|
| https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html | Ansible Installation |
| [ansible_role](https://github.com/avengers-p11/ansible/blob/main/jenkins/) | Ansible role for jenkins |
