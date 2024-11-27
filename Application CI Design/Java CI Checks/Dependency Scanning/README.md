#    **Dependency Scanning**

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer L0**  | **Reviewer L1**   | **Reviewer L2**   |
|-----------------------|----------------|-------------|---------------------------|---------------------|------------------|-------------------|----------------|
| Mohit Saini      |   27-11-24       | v1 | Mohit Saini          |     27-11-24            |    |      |     |


![image](https://github.com/user-attachments/assets/71afe6e0-2f2f-4ea9-8d74-7ed95a6248d7)


**Table of Contents**

1. [**Introduction**](#introduction)
2. [**What**](#what-is-dependency-scanning)
3. [**Why**](#why)
4. [**Different Tools**](#different-tools)
5. [**Conclusion**](#conclusion)
6. [**Contact Information**](#contact-information)
7. [**References**](#references)



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


# Different Tools
The Dependency-Check tool provides checks for vulnerable components that can be run from the command line. Here is the list of tools. 
| **Tool Name**               | **Description**                                                      | **Features**                                                     | **Pros**                                                         | **Cons**                                                          |
|-----------------------------|----------------------------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|
| **OWASP Dependency-Check**   | Scans project dependencies for known vulnerabilities.                | Automated scanning, integrates with Maven, Gradle, and Jenkins.  | Open-source, detailed reports, supports many formats.           | Can generate false positives, slower for large projects.         |
| **Snyk**                     | Finds and fixes vulnerabilities in open-source dependencies.         | Monitors dependencies, fix issues with PRs, integrates with CI/CD. | Easy to use, integrates with major CI/CD tools, active community. | Free version limited to a small number of tests, expensive for large teams. |
| **WhiteSource**              | Provides open-source security management, including dependency scanning. | Real-time security alerts, license compliance, detailed reporting. | Easy to integrate with build tools, great for enterprise use.   | Can be expensive for smaller teams, complexity in configuration. |
| **Sonatype Nexus Lifecycle** | Provides full lifecycle management for open-source dependencies.     | Vulnerability scanning, license compliance, detailed analytics.  | Strong integration with CI/CD pipelines, enterprise-ready.      | High cost, may be complex for small teams.                       |
| **Black Duck**               | Identifies security vulnerabilities in open-source components.       | Automated scanning, vulnerability and license management.        | Comprehensive vulnerability database, strong reporting.         | Expensive, requires enterprise subscription for full features.   |
| **FOSSA**                    | Provides dependency analysis and license compliance.                 | Real-time alerts, vulnerability scanning, integrates with GitHub. | Easy integration, good for managing licenses and vulnerabilities.| Can be costly, limited features in free version.                 |
| **Semgrep**                  | Static analysis tool that supports dependency scanning for security flaws. | Code scanning, security vulnerabilities detection in dependencies. | Fast scanning, easy to integrate, customizable rules.           | Can require significant tuning for larger codebases.             |


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
