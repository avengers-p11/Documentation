#    **Docmentation and POC of Dependency Scanning**

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer L0**  | **Reviewer L1**   | **Reviewer L2**   |
|-----------------------|----------------|-------------|---------------------------|---------------------|------------------|-------------------|----------------|
| Mohit Saini      |   27-11-24       | v1 | Mohit Saini          |     09-12-24            |  Khushi & Shreya  |      |     |


![image](https://github.com/user-attachments/assets/71afe6e0-2f2f-4ea9-8d74-7ed95a6248d7)


**Table of Contents**

1. [**Introduction**](#introduction)
2. [**What is Dependency Scanning?**](#what-is-dependency-scanning?)
3. [**Why Dependency Scanning?**](#why-dependency-scanning?)
4. [**Different Tools**](#different-tools)
5. [**OWASP Dependency-Check using Maven**](owsap-dependency-check-using-maven)
6. [**Conclusion**](#conclusion)
7. [**Contact Information**](#contact-information)
8. [**References**](#references)



# Introduction
A situation in which you need something or someone and are unable to continue normally without them.Dependency is when one thing needs to happen before another thing can happen. It describes the relationship among activities and specifies the particular order in which they need to be performed. 


# What is Dependency Scanning?

Dependency scanning is a tool that analyzes an application's dependencies for known vulnerabilities. Dependency scanning can help you identify and address security risks in your application during development and testing.

# Why Dependency Scanning?

| **Reason**                   | **Explanation**                                                                 |
|------------------------------|---------------------------------------------------------------------------------|
| **Identify Vulnerabilities**  | Scanning helps detect security issues in third-party libraries and dependencies.|
| **Enhance Security**          | Ensures dependencies don't introduce security risks to the application.        |
| **Ensure Compliance**         | Helps meet industry security and regulatory requirements.                      |
| **Prevent Exploits**          | Avoids using outdated or vulnerable dependencies that can be exploited.        |
| **Cost-Effective**            | Detecting and fixing issues early is less expensive than dealing with them later.|
| **Maintain Software Quality** | Keeps dependencies up-to-date and free from vulnerabilities to maintain safe and reliable software. |


# Different Tools
The Dependency-Check tool provides checks for vulnerable components that can be run from the command line. Here is the list of tools. 
| **Tool Name**               | **Description**                                                      | **Features**                                                     | **Pros**                                                         | **Cons**                                                          |
|-----------------------------|----------------------------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|
| **OWASP Dependency-Check**   | Scans project dependencies for known vulnerabilities.                | Automated scanning, integrates with Maven, Gradle, and Jenkins.  | Open-source, detailed reports, supports many formats.           | Can generate false positives, slower for large projects.         |
| **Snyk**                     | Finds and fixes vulnerabilities in open-source dependencies.         | Monitors dependencies, fix issues with PRs, integrates with CI/CD. | Easy to use, integrates with major CI/CD tools, active community. | Free version limited to a small number of tests, expensive for large teams. |
| **WhiteSource**              | Provides open-source security management, including dependency scanning. | Real-time security alerts, license compliance, detailed reporting. | Easy to integrate with build tools, great for enterprise use.   | Can be expensive for smaller teams, complexity in configuration. |
| **Sonatype Nexus Lifecycle** | Provides full lifecycle management for open-source dependencies.     | Vulnerability scanning, license compliance, detailed analytics.  | Strong integration with CI/CD pipelines, enterprise-ready.      | High cost, may be complex for small teams.                       |

# OWASP Dependency-Check using Maven

## **Before starting dependency test, ensure that you have Maven installed on your system. If not, please follow the instructions in the following resource**

## Related Resources
| Link         | Description         |
|--------------|------------------------|
| [Maven](https://github.com/avengers-p11/Documentation/tree/main/Application%20CI%20Design/Java%20CI%20Checks/Static%20Code%20Analysis#tool-poc-sonarqube ) |Tool POC| 


##  Step 1. Clone the repo from github

```
sudo git clone OT-MICROSERVICES/salary-api
```
![image](https://github.com/user-attachments/assets/ef93c8ec-79a9-4225-b60b-b089ce6beafd)


##  Step 2. Change the repo choose the github repo which is cloned already
```
cd salary-api
```

##  Step 3. Dependency checking
```
mvn org.owasp:dependency-check-maven:check
```
![image](https://github.com/user-attachments/assets/69071e0a-34e6-47e4-a91e-e82601d7d79b)

## Step 4. Dependency Result
![image](https://github.com/user-attachments/assets/e2c935e2-b2e1-49d8-8048-5a0d726637da)


## Steps 5. Report Link
| Link         | Description         |
|--------------|------------------------|
| [Artifact](https://github.com/avengers-p11/Documentation/blob/main/Application%20CI%20Design/Java%20CI%20Checks/Bugs%20Analysis/salary-0.1.0-RELEASE.jar.original)           |File |
| [Dependency Scanning](https://github.com/avengers-p11/Documentation/blob/main/Application%20CI%20Design/Java%20CI%20Checks/Unit%20Testing%20/report)| Report |
#



# Conclusion

To safeguard your applications, prioritize dependency scanning as an essential part of your development workflow. By doing so, we can protect our users, our organization's reputation, and bottom line.

#  Contact Information


| **Name**    | **Email address**         |
|-------------|---------------------------|
| Mohit Saini | mohit.saini.snaatak@mygurukulam.co |


# References

| **Link** | **Description** |
|------------------------------------------------------|------------------|
| https://docs.gitlab.com/ee/user/application_security/dependency_scanning/| Dependancy Scanning |
| https://finitestate.io/blog/best-java-scanner| Dependancy Scanning tool |
