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

Create ansible role 


asible-galazy init sonar-setup

## Run the ansible role**
```
ansible-playbook -i <inventory-name> <playbook-name>
``` 
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
