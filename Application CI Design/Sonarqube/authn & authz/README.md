
# Detailed documentation of SonarQube Authentication and Authorization

#### ![image](https://github.com/user-attachments/assets/dd227152-b1cf-4da0-a001-a3887bb2b68f)



| **Author**          | **Created on** | **Version** | **Last edited on** | **L0 Reviewer**  | **L1 Reviewer** | **L2 Reviewer** |
|---------------------|----------------|-------------|--------------------|------------------|-----------------|-----------------|
| Mohit Saini         | 01-12-2024     | V1          | 02-12-2024         | Khushi Malhotra  |                 |                 |


# **Table of Contents**

| **S. No.** | **Section**                                                                |
|------------|----------------------------------------------------------------------------|
| 1          | [**Introduction**](#introduction)                                         |
| 2          | [**What is Authentication and Authorization?**](#what-is-authentication-and-authorization?) |
| 3          | [**Why ?**](#why?)                                                           |
| 4          | [**Different Types of Authentication Methods**](#different-types-of-authentication-methods) |
| 5          | [**Different Types of Authorization Methods**](#different-types-of-authorization-methods) |
| 6          | [**Conclusion**](#conclusion)                                             |
| 7          | [**Contact Information**](#contact-information)                           |
| 8          | [**References**](#references)                                             |




# Introduction
 This documentation provides a comprehensive guide to implementing and managing secure access controls in SonarQube through authentication and authorization mechanisms.

# What is Authentication and Authorization?
**Authentication** is proving who you are (like with a password).
\
**Authorization** is deciding what you can do (like access certain files or run specific programs).

# Why ?
SonarQube is a powerful tool for analyzing code quality and security. To protect the integrity of your codebase and ensure that only authorized individuals can access and modify critical information, it employs authentication and authorization mechanisms.

| **Category**           | **Description**                                      |
|-------------------------|----------------------------------------------------|
| **Security**            | Ensures only authorized users access SonarQube and protects the codebase from changes. |
| **Data Privacy**        | Keeps sensitive code secure by limiting access.    |
| **Role-Based Control**  | Assigns roles with specific permissions for tasks like analyzing code or reviewing reports. |
| **Auditing & Compliance** | Tracks user activity to meet security rules.          |


# Different types of Authentication methods

![image](https://github.com/user-attachments/assets/aab40b69-2d6f-43d3-9939-f32bae64c8d8)


| **Authentication Method**       | **Description**                                                                                                                                         |
|----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Password-Based Authentication**| Users provide a username and password to authenticate.                                                                                                 |
| **Two-Factor Authentication (2FA)**| Combines something you know (password) with something you have (e.g., smartphone for a code) for added security.                                          |
| **Biometric Authentication**    | Uses physical characteristics like fingerprints, facial recognition, or retinal scans to authenticate users.                                           |
| **Token-Based Authentication**  | Users log in once to receive a token (e.g., JWT), used for future requests without re-entering credentials.                                                   
| **OAuth (Open Authorization)**   | A token-based standard that allows third-party apps to access a user's resources without exposing their password (used by Google, Facebook, etc.).      |
| **LDAP Authentication**         | Uses Lightweight Directory Access Protocol (LDAP) to authenticate users, common in enterprise environments with centralized user directories.          |
| **SAML (Security Assertion Markup Language)**| A protocol used for Single Sign-On (SSO), where an identity provider (IdP) authenticates the user and passes a token to the service provider.            |
| **Social Media Authentication** | Users authenticate using their social media accounts (e.g., Google, Facebook, LinkedIn) to access other services.                                       |
| **Smart Card Authentication**   | Uses a smart card with authentication data (often combined with a PIN) to authenticate a user.                                                         |


# Different types of Authorization methods

![image](https://github.com/user-attachments/assets/bcf4f305-bd58-49e3-ae2f-a7021f8c7db5)


| **Authorization Method**           | **Description**                                                                 |
|------------------------------------|---------------------------------------------------------------------------------|
| **Built-in Roles**         | Predefined roles like Admin, User, and Codeviewer with specific permissions.                                 |
| **Custom Permissions**     | Admins can define and assign custom permissions for more control over actions.                               |
| **Project-Level Permissions** | Set permissions for different projects, e.g., admin rights for one project, viewing rights for another.    |
| **Group Management**       | Group users and assign permissions to groups for easier management.                                           |

#
![image](https://github.com/user-attachments/assets/5897766f-65a7-42d1-b473-33efad1bbd9f)


# Conclusion
 In our project, we use Built-in Authentication for user management, Project-based Permissions for assigning roles and access levels based on responsibilities, and SonarQube User Tokens for secure integration and API access. SonarQube user tokens are versatile and used across various scenarios. They are commonly employed in CI/CD pipelines for authenticating tasks in Jenkins, GitLab, or GitHub to run code analysis seamlessly. Tokens also enable secure API access, allowing automation of tasks like project creation, fetching quality metrics, and managing permissions.

#  Contact Information


| **Name**    | **Email address**         |
|-------------|---------------------------|
| Mohit Saini | mohit.saini.snaatak@mygurukulam.co |


# References

| **Link** | **Description** |
|------------------------------------------------------|------------------|
| [Authentication](https://www.sonarsource.com/blog/sonarqube-ldap-sso/)| Sonar authentication and authorization |
| [Authentication and Authorization](https://docs.sonarsource.com/sonarqube-server/9.9/instance-administration/authentication/overview/#:~:text=SonarQube%20comes%20with%20an%20onboard,for%20Bitbucket%2C%20and%20authentication.)| Sonar authentication and authorization|





