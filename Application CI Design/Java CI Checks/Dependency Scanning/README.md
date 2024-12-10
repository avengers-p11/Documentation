#    **Docmentation and POC of Java Dependency Scanning**

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer L0**  | **Reviewer L1**   | **Reviewer L2**   |
|-----------------------|----------------|-------------|---------------------------|---------------------|------------------|-------------------|----------------|
| Mohit Saini      |   27-11-24       | v1 | Mohit Saini          |     27-11-24            | Khushi   |      |     |


![image](https://github.com/user-attachments/assets/71afe6e0-2f2f-4ea9-8d74-7ed95a6248d7)


**Table of Contents**

1. [**Introduction**](#introduction)
2. [**What**](#what-is-dependency-scanning)
3. [**Why**](#why)
4. [**Different Tools used in Dependency Scanning**](#different-tools-dependency-scanning)
5. [**Tool POC**](owsap-dependency-check-using-maven)
6. [**Conclusion**](#conclusion)
7. [**Contact Information**](#contact-information)
8. [**References**](#references)



# Introduction
A situation in which you need something or someone and are unable to continue normally without them.Dependency is when one thing needs to happen before another thing can happen. It describes the relationship among activities and specifies the particular order in which they need to be performed. 


# What is Dependency Scanning 

Dependency scanning is a tool that analyzes an application's dependencies for known vulnerabilities. Dependency scanning can help you identify and address security risks in your application during development and testing.

# Why

| **Reason**                   | **Explanation**                                                                 |
|------------------------------|---------------------------------------------------------------------------------|
| **Identify Vulnerabilities**  | Scanning helps detect security issues in third-party libraries and dependencies.|
| **Enhance Security**          | Ensures dependencies don't introduce security risks to the application.        |
| **Ensure Compliance**         | Helps meet industry security and regulatory requirements.                      |
| **Prevent Exploits**          | Avoids using outdated or vulnerable dependencies that can be exploited.        |
| **Cost-Effective**            | Detecting and fixing issues early is less expensive than dealing with them later.|
| **Maintain Software Quality** | Keeps dependencies up-to-date and free from vulnerabilities to maintain safe and reliable software. |


# Different Tools used in Dependency Scanning
The Dependency-Check tool provides checks for vulnerable components that can be run from the command line. Here is the list of tools. 
| **Tool Name**               | **Description**                                                      | **Features**                                                     | **Pros**                                                         | **Cons**                                                          |
|-----------------------------|----------------------------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|
| **OWASP Dependency-Check**   | Scans project dependencies for known vulnerabilities.                | Automated scanning, integrates with Maven, Gradle, and Jenkins.  | Open-source, detailed reports, supports many formats.           | Can generate false positives, slower for large projects.         |
| **Snyk**                     | Finds and fixes vulnerabilities in open-source dependencies.         | Monitors dependencies, fix issues with PRs, integrates with CI/CD. | Easy to use, integrates with major CI/CD tools, active community. | Free version limited to a small number of tests, expensive for large teams. |
| **WhiteSource**              | Provides open-source security management, including dependency scanning. | Real-time security alerts, license compliance, detailed reporting. | Easy to integrate with build tools, great for enterprise use.   | Can be expensive for smaller teams, complexity in configuration. |
| **Sonatype Nexus Lifecycle** | Provides full lifecycle management for open-source dependencies.     | Vulnerability scanning, license compliance, detailed analytics.  | Strong integration with CI/CD pipelines, enterprise-ready.      | High cost, may be complex for small teams.                       |

# Tool POC (OWASP Dependency-Check using Maven)

## Prerequisites 

## System Specifications
| **Specification**          | **Details**                                                      |
|----------------------------|------------------------------------------------------------------|
| **Operating System**        | Linux (Ubuntu, CentOS, Amazon Linux 2, etc.)                    |
| **Java Version**            | Java 8 or higher (JDK). Set **JAVA_HOME** environment variable. |
| **Memory**                  | Minimum 512 MB RAM (Recommended: 2 GB or more for larger projects). |
| **Disk Space**              | Minimum 1 GB of free disk space for installation and dependencies. |
| **Maven Version**           | Apache Maven 3.x (latest stable version).                       |
| **Network**                 | Internet connection for downloading dependencies from Maven repositories. |
| **IDE Support** (Optional)  | Eclipse, IntelliJ IDEA, or Visual Studio Code with Maven plugins. |



## **Step 1. First create the instance t2.micro or as per your bussiness needs.**

## **Step 2. Update and Upgrade System Packages**

```
sudo apt update
```
![image](https://github.com/user-attachments/assets/9b9ae16e-6312-4826-aae7-27788803d1bf)

## **Step 3. Java installation**

```
sudo apt install -y openjdk-17-jdk
```
![image](https://github.com/user-attachments/assets/204ef06f-6d5a-40d4-beff-3c765702f5c1)

##  **Step 4. verify the installed Java version**
```
java -version
```

##  **Step 5. Maven installation**

```
sudo apt install maven
```
![image](https://github.com/user-attachments/assets/2b35ffaa-8da6-4d30-98a4-77509c0e1087)

##  **Step 6. Clone the repo from github**

```
sudo git clone OT-MICROSERVICES/salary-api
```
![image](https://github.com/user-attachments/assets/ef93c8ec-79a9-4225-b60b-b089ce6beafd)


##  **Step 7. Change the repo choose the github repo which is cloned already**
```
cd salary-api
```

##  **Step 7. Dependency checking**
```
mvn org.owasp:dependency-check-maven:check
```
![image](https://github.com/user-attachments/assets/69071e0a-34e6-47e4-a91e-e82601d7d79b)

##  **Dependency Report**
![image](https://github.com/user-attachments/assets/e2c935e2-b2e1-49d8-8048-5a0d726637da)




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
