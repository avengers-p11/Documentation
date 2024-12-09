
# Documentation on Jenkins Setup using Ansible role


![image](https://github.com/user-attachments/assets/08c6c855-bb92-4bb4-a626-c33e8a47ca1e)




| **Author**          | **Created on** | **Version** | **Last edited on** | **L0 Reviewer**  | **L1 Reviewer** | **L2 Reviewer** |
|---------------------|----------------|-------------|--------------------|------------------|-----------------|-----------------|
| Pravesh Kumar       | 06-12-2024     | V1          | 06-12-2024         | Pravesh Kumar  |                 |                 |


**Table of Contents**

1. [**Introduction**](#introduction)
2. [**What is ansible**](#what-is-ansible)
3. [**Why ansible**](#why-ansible)
4. [**Steps for creating Ansible role**](#Steps-for-creating-ansible-role)
5. [**Folder Structure**](#folder-structure)
5. [**Command to run playbook**](#command-to-run-playbook)
8. [**Conclusion**](#conclusion)
9. [**Contact Information**](#contact-information)
10. [**References**](#references)

# Introduction
Ansible is a powerful automation tool that lets you manage and configure your infrastructure efficiently. It uses a simple language called YAML to define tasks and playbooks.

# What is ansible
Ansible Roles are a powerful way to organize and reuse automation tasks. They provide a standardized structure for grouping related tasks, variables, files, templates, and handlers. This modular approach makes your playbooks more manageable, reusable, and easier to maintain.


# Why ansible?
Ansible Roles are a powerful mechanism for organizing and reusing automation tasks.

# Why Use Ansible Roles?

| **Reason**                     | **Description**                                                                                       |
|--------------------------------|-------------------------------------------------------------------------------------------------------|
| **Simplify Complex Deployments** | Organizes tasks into reusable, modular components, making complex setups easier to manage.           |
| **Reduce Human Error**           | Ensures consistent execution of tasks through automation, reducing the chance of manual mistakes.     |
| **Accelerate Deployment Times**  | Speeds up deployments by reusing predefined tasks and configurations.                                |
| **Improve Consistency and Compliance** | Standardizes configurations, ensuring uniformity across environments and aiding regulatory compliance. |
                                  |
# Steps for creating Ansible role

[Reffer the POC for jenkins setup](https://github.com/avengers-p11/Documentation/tree/main/Application%20CI%20Design/Jenkins/Software%20Configuration/POC%20to%20setup%20Jenkins)

# Folder Structure

![image](https://github.com/user-attachments/assets/899ee4f3-0dbd-4bec-94e2-85688bbf3ad3)



# Command to run playbook

``` sh
ansible-playbook -i <inventory-file> <playbook-name>
```

# Conclusion
Ansible Roles offer a modular approach to automate infrastructure, making deployments efficient, consistent, and less error-prone.



# Contact Information

| **Name** | **Email address**            | **Github ID**
|----------|-------------------------------|-------------------|
| Pravesh Kumar    |  pravesh.kumar611@gmail.com           | Pravesh899 |

---

# References

| **Link** | **Description**            |
|----------|-------------------------------|
|[Ansible Documentation](https://docs.ansible.com/ansible/latest/index.html)| Ansible community documentation|
