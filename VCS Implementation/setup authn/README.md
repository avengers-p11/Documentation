
#  Authentication in Jenkins

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 29-11-24      | Neelesh  Kumar             | 29-11-24           |  | | |     


##  Table of Contents
1. [Introduction](#introduction)
2. [What is Authentication in Jenkins?](#what-is-authentication-in-jenkins)
3. [Why is Authentication Important?](#why-is-authentication-important)
4. [Authentication Methods](#authentication-methods)
5. [Limitations](#limitations)
6. [Best Practices](#best-practices)
7. [Types of Authentication in Jenkins](#types-of-authentication-in-jenkins)
8. [POC: Setting up Authentication](#poc-setting-up-authentication)
9. [Conclusion](#conclusion)
10. [Contact Information](#contact-information)
11. [References](#references)

---

##  Introduction

This document gives an overview of how authentication works in Jenkins. Jenkins is an open-source server that helps automate building, testing, and deploying software. To keep Jenkins safe, it uses **authentication** (to verify user identity) and **authorization** (to control what users can do).

---

##  What is Authentication in Jenkins?

Authentication is about checking who a user is. In Jenkins, users must authenticate (prove who they are) to access or interact with the Jenkins server.


---

##  Why is Authentication Important?

| Reason                          | Explanation |
|----------------------------------|-------------|
| **Security**                     | Makes sure only the right people access Jenkins. |
| **Control Access**               | Ensures users can only see and do what they are allowed to. |
| **Auditing and Tracking**        | Logs user actions for tracking and troubleshooting. |
| **Integration with Other Tools** | Allows Jenkins to securely interact with external tools. |
| **Compliance**                   | Helps meet security requirements and standards. |

---

##  Authentication Methods

Jenkins has several ways to handle user login:

| **Method**                         | **Description**                                                                                                                        |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Jenkins Database**               | Jenkins manages usernames and passwords internally.                                                                                     |
| **LDAP (e.g., Active Directory)**  | Jenkins integrates with corporate LDAP, allowing employees to use their existing work credentials.                                       |
|                                    | *Example*: An employee logs into Jenkins with their company email and password (stored in the company’s Active Directory).               |
| **Single Sign-On (SSO)**           | Allows users to log in once and access multiple systems using SAML or OAuth.                                                            |
|                                    | *Example*: A user logs into Jenkins via their Google Workspace account, which also grants them access to other company services.         |
| **API Token**                      | Jenkins users can generate API tokens for programmatic access, instead of using passwords.                                               |
|                                    | *Example*: A user creates an API token in Jenkins and uses it to trigger Jenkins builds via a script or command-line tool.               |
| **SSH Keys**                       | Used for secure logins, often with Git integration, bypassing passwords.                                                                |
|                                    | *Example*: A developer configures Jenkins to log in using their public SSH key, which they also use for Git operations.                 |


---

##  Limitations

| Limitation            | Explanation |
|-----------------------|-------------|
| **Limited Integration**| Jenkins’ built-in database is not always the best for large teams. |
| **Scalability**        | Larger companies may need more scalable authentication methods like LDAP or SAML. |
| **Security**           | External providers often offer stronger, centralized security. |

---

##  Best Practices

To keep Jenkins secure, follow these tips:

| Practice                          | Description |
|------------------------------------|-------------|
| **Use Strong Passwords**           | Require complex passwords to improve security. |
| **Enable Multi-Factor Authentication** | Add another layer of security with MFA. |
| **Rotate Credentials Regularly**   | Change passwords and tokens frequently. |
| **Limit User Privileges**          | Only give users the permissions they need. |
| **Monitor User Activity**          | Keep an eye on logs for suspicious behavior. |
| **Update Jenkins and Plugins**     | Regularly update Jenkins to keep it secure. |


---

##  POC: Setting up Authentication

### 1. Install GitHub Authentication Plugin
- Go to **Manage Jenkins** > **Manage Plugins**.
 
- Search for and install **GitHub Authentication Plugin**.
  
### 2. Configure GitHub Authentication
After installing the plugin, go back to the Jenkins dashboard
**Click on "Manage Jenkins" again**

**Select "Configure Global Security**


**Setting Up an Application in GitHub**

Once you have installed the GitHub authentication plugin, you need to set up an application within GitHub. Here’s how:

*Log into your GitHub account.*


**Scroll to the bottom of the page and click on “Developer settings”.**





**Click on “OAuth Apps” and then on “Register a new application”.**


**Install the GitHub Authentication Plugin in Jenkins**

A.Go to your Jenkins dashboard.

B.Click on Manage Jenkins > Manage Plugins.


C.Search for GitHub Authentication Plugin under the "Available" tab.

D. Install the plugin and restart Jenkins if required.

****3. Configure GitHub OAuth in Jenkins****

**A.Go to Manage Jenkins > Configure Global Security**


**B.Under Security Realm, select GitHub Authentication**


**C.Enter the Client ID and Client Secret that you obtained from GitHub when creating the OAuth App.**



**D.For GitHub Web URI, set https://github.com and For GitHub API URI, set https://api.github.com.**





****Save and Test the Integration:****

**Save the settings and go to the Jenkins login page.**

You should see the option to Login with GitHub.

**Click on the button, and you will be redirected to GitHub to authorize Jenkins**


After granting access, you will be logged into Jenkins using your GitHub credentials.




---

##  Conclusion

Jenkins offers many ways to authenticate users, from using its built-in database to integrating with external providers like LDAP or SAML. The best method depends on the size of your team and the security requirements of your organization.

---

## 📧 Contact Information

| Name| Email Address      |
|-----|--------------------------|
| Neelesh kumar | nilesh.rajput.snaatak@mygurukulam.co || GitHub | URL |
|----------|---------|
|  devneelesh921  |  https://github.com/devneelesh921  |



---

##  References

| Link | Description |
|------|-------------|
| [Jenkins Documentation](https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template) | Jenkins Application Template |
| [GitHub OAuth Setup](https://stackoverflow.com/questions/60559456/configuring-jenkins-with-github-authorization) | Guide to setting up GitHub OAuth |
|[Authentication and Authorization in Jenkins](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/Jenkins/Jenkins%20authn%20%26%20authz/README.md) |Authentication and Authorization in Jenkins|




