
# **POC to Setup Jenkins**

| **Author** | **Created on** | **Version** | **Last updated by** | **Last edited on** | **Reviewer L0** |
|------------|-------------|-----------|--------------|-------------|-----------|
| Pravesh Kumar | 06-12-24 | Version 1.1 | Pravesh Kumar | 06-12-24 |  |


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
```
sudo apt install python3-pip
```
![image](https://github.com/user-attachments/assets/3619b1aa-9259-4be3-80dc-14ff4015cc2d)

```
pip install boto
```

![image](https://github.com/user-attachments/assets/382c2609-6922-4e77-8ae0-306803add6d0)


## Run the ansible role**
```
ansible-playbook -i <inventory-name> <playbook-name>
``` 
# Conclusion
Roles are a way to make code in playbooks reusable by putting the functionality into generalized libraries that can be then used in any playbook as needed.

# Contact Information

| **Name** | **Email address**            | **Github ID**
|----------|-------------------------------|-------------------|
| Pravesh Kumar    |  pravesh.kumar611@gmail.com           | Pravesh899 |

---

# References

| **Link** | **Description** |
|----------------------------------------------------|--------------------|
| https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html | Ansible Installation |
| https://www.softwaretestinghelp.com/ansible-roles-jenkins-integration-ec2-modules | Ansible role for jenkins |
