
# **POC to Setup Jenkins**

| **Author** | **Created on** | **Version** | **Last updated by** | **Last edited on** | **Reviewer L0** |
|------------|-------------|-----------|--------------|-------------|-----------|
| Pravesh Kumar | 06-12-24 | Version 1.1 | Pravesh Kumar | 20-12-24 |  |


## **Table of Contents**

1. [Introduction](#introduction)
2. [Pre-requsities](#pre-requisties)
3. [Steps for Ansible role](#steps-for-ansible-role)
4. [Output](#output)
5. [Conclusion](#conculsion)
6. [Contact Information](#contact-information)
7. [References](#references)

 
 
 ## Introduction

Ansible roles are basically playbooks broken up into a known file structure.


 ## Pre-requisties

|Pre-requisite	|Description|
|-----|------|
|Ansible| Ensure Ansible is installed on your system.|
|pip and boto3| Install pip for Python 3 and then install the boto3 library, which is required for AWS interactions.|
|AWS CLI| Install and configure the AWS CLI to authenticate and interact with AWS services.|


### Steps for ansible role

**Step 1. Update your OS**
```
sudo apt update
```
![Screenshot 2024-12-06 at 7 12 34 PM](https://github.com/user-attachments/assets/25d580c3-3065-4dee-8b33-5ff39691554d)


**Step 3. Ansbilbe installed**
```
sudo apt install ansible
```

**Step 4. Verify ansible version**

```
ansible --version
```
![Screenshot 2024-12-20 at 9 13 40 PM](https://github.com/user-attachments/assets/7df16a11-da90-47ed-9343-e7bd7336d14f)



**Step 5. Create ansible role** 

```
ansible-galaxy init install_jenkins
```
![Screenshot 2024-12-20 at 9 06 35 PM](https://github.com/user-attachments/assets/c06ee123-e16d-4379-9c1f-40673060f6a9)


**Step 6. Change the direcotry current to my role**
```
cd install_jenkins
```
![Screenshot 2024-12-20 at 9 10 25 PM](https://github.com/user-attachments/assets/5b0570ac-4eaa-4f12-80e3-11aa47978be4)



**Step 7. After configure my role direcorty structure**
```
tree
```
![Screenshot 2024-12-20 at 9 03 46 PM](https://github.com/user-attachments/assets/09cb2896-e534-465f-b6aa-393e48d74442)




**Step 8. pip and boto3 installation**

### pip
Its a package manager for Python used to install and manage Python libraries. It is essential for managing dependencies in Python projects. 

### boto3
The AWS SDK (Software Development Kit) for Python, enabling developers to interact with various AWS services like EC2, S3, Lambda, and more from Python applications.

```
sudo apt install python-pip
```
![Screenshot 2024-12-20 at 8 47 19 PM](https://github.com/user-attachments/assets/0b712784-8f42-46a6-9b8d-26d08a3b8a96)

```
sudo apt install python3-pip
```

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

## Output

![Screenshot 2024-12-20 at 9 08 39 PM](https://github.com/user-attachments/assets/92b1a12e-b21b-45fb-8f34-75fdf22d69a6)

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
