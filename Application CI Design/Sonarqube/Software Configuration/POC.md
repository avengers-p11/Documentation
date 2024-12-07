# **Documentation of Ansible role**

| **Author** | **Created on** | **Version** | **Last updated by** | **Last edited on** | **Reviewer L0** |
|------------|-------------|-----------|--------------|-------------|-----------|
| Mohit Saini | 05-12-24 | Version 1.1 | Mohit Saini | 06-12-24 | Khushi |


# **Table of Contents**

1.  [Introduction](#introduction)

2.  [Pre-requsities](#pre-requisties)

3.  [Steps for Ansible role](#steps-for-ansible-role)

4.  [Conclusion](#conculsion)

5.  [Contact Information](#contact-information)

6. [References](#references)

 
 
 # Introduction

Ansible roles are basically playbooks broken up into a known file structure.


 # Pre-requisties
 1. Ansible Insalled
 2. Pip and boto3 installed
 3. install aws cli should be configured


## Steps for ansible role

**Steps 1. Update your OS**
```
sudo apt update
```
![image](https://github.com/user-attachments/assets/d7736006-9474-4307-8cc3-a7eb3bdd07d5)

**Steps 3. Ansbilbe installed**
```
sudo apt install ansible
```

**Steps 4. Verify ansible version**

```
ansible --version
```
![image](https://github.com/user-attachments/assets/43195b42-50e8-4912-b9b9-2e30f619ecf5)


**Steps 5. Create ansible role** 

```
ansible-galaxy init sonar
```
![image](https://github.com/user-attachments/assets/35fffe9d-783a-43d3-9083-042c1377bfa0)

**Steps 6. Change the direcotry current to my role**
```
cd sonar
```
![image](https://github.com/user-attachments/assets/99e5a27c-1bf5-4f73-8a6a-70cd7a9624b6)

**Steps 7. After configure my role direcorty structure**
```
tree
```
![image](https://github.com/user-attachments/assets/2ea509a9-c7b9-426d-9155-369833f717ff)


**Steps 8. pip and boto3 installation**
```
sudo apt install python3-pip
```
![image](https://github.com/user-attachments/assets/3619b1aa-9259-4be3-80dc-14ff4015cc2d)

```
pip install boto
```

![image](https://github.com/user-attachments/assets/382c2609-6922-4e77-8ae0-306803add6d0)


**Run the ansible role**
```
ansible-playbook -i <inventory-name> <playbook-name>
```
![image](https://github.com/user-attachments/assets/34a1077c-6c4d-4987-b64d-d49ea1b65773)
![image](https://github.com/user-attachments/assets/1e76698b-65b2-424e-b40c-fdd5e2f8caf1)



# Conclusion
Roles are a way to make code in playbooks reusable by putting the functionality into generalized libraries that can be then used in any playbook as needed.

# Contact Information

| **Name**    | **Email address**         |
|-------------|---------------------------|
| Mohit Saini | mohit.saini.snaatak@mygrurukulam.co |

# References

| **Link** | **Description** |
|----------------------------------------------------|--------------------|
| https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html | Ansible Installation |
| https://medium.com/@mattpwest/setting-up-sonarqube-with-ansible-fcabadee6953 | Ansible role for Sonar |
