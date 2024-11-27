#    **DAST**

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer L0**  | **Reviewer L1**   | **Reviewer L2**   |
|-----------------------|----------------|-------------|---------------------------|---------------------|------------------|-------------------|----------------|
| Mohit Saini      |   27-11-24       | v1 | Mohit Saini          |     27-11-24            |    |      |     |

![image](https://github.com/user-attachments/assets/4aa0c132-1fbb-45bc-ad5f-2a631586676a)




**Table of Contents**

1. [**Introduction**](#introduction)
2. [**What**](#what-is-dast)
3. [**Types of AST**](#types-of-ast)
4. [**Why**](#why-dast)
5. [**Different Tools**](#different-tools)
6. [**Conclusion**](#conclusion)
7. [**Contact Information**](#contact-information)
8. [**References**](#references)



# Introduction
Application Security Testing (AST) is the process of finding and fixing security problems in software to keep it safe from attacks.This document describes the security testing of applications. 


# Types of AST

![image](https://github.com/user-attachments/assets/8ce0cc40-5f78-4ba2-8bcd-b3f622ac2692)

**Static Application Security Testing (SAST)**: Analyzes the source or binary code without running the application to find vulnerabilities early.

**Dynamic Application Security Testing (DAST)**: Tests a running application to find vulnerabilities that occur during runtime.

**Interactive Application Security Testing (IAST)**: Combines SAST and DAST by analyzing the application both at runtime and in the code.

**Software Composition Analysis (SCA)**: Scans open-source libraries and dependencies for known vulnerabilities.

**Penetration Testing**: Simulates real-world attacks to identify security weaknesses by ethical hackers.


# What is DAST

Dynamic Application Security Testing (DAST) is a method of testing a web app by simulating attacks to find security weaknesses. It checks the app from the outside, like a hacker, and looks for any problems or vulnerabilities.

# Why DAST

| **Point**                           | **Explanation**                                                                 |
|-------------------------------------|---------------------------------------------------------------------------------|
| **Helps developers find security issues** | DAST identifies security vulnerabilities early in the development process.     |
| **Catching problems early is cheaper** | It's easier and less expensive to fix issues when found early in the SDLC.     |
| **Unfound vulnerabilities lead to breaches** | Leaving vulnerabilities unchecked can lead to data breaches and financial loss. |
| **Unchecked vulnerabilities damage reputation** | Security issues can harm the company's reputation if they go unaddressed.     |
| **DAST reduces human error**        | Helps reduce mistakes made during the Software Development Life Cycle (SDLC).  |


# Different Tools
Here are some tools for DAST. 

| **Tool Name**                | **Description**                                                                 | **Features**                                                  | **Why**                                                   | **Pros**                                                            | **Cons**                                                            |
|------------------------------|---------------------------------------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|
| **OWASP ZAP**                 | Open-source security testing tool.                                              | Automated scanners, vulnerability detection, active and passive scanning. | Ideal for developers looking for a free, open-source solution for DAST. | Free, open-source, extensive documentation, active community. | Limited advanced features compared to paid tools. Can be complex to set up. |
| **Burp Suite**                | Comprehensive platform for web application security testing.                    | Intercepting proxy, vulnerability scanning, custom extensions.   | Perfect for penetration testers and security experts.           | Advanced scanning, customizable, integrates with other tools.   | Expensive, may require expertise to fully utilize.              |
| **Acunetix**                  | Automated security scanner for web applications.                                | Detects SQL injection, XSS, and other vulnerabilities.            | Great for quickly identifying common web vulnerabilities.       | Fast scanning, easy to use, covers a wide range of vulnerabilities. | Pricey, fewer customization options for advanced users.         |
| **AppSpider**                 | Dynamic application security testing tool.                                      | Scanning for Java frameworks, automated vulnerability discovery. | Ideal for automating security testing across Java applications. | Customizable, automates complex scans, supports Java frameworks. | High cost, can generate false positives if not tuned correctly.  |
| **Nessus**                    | Vulnerability scanner that performs DAST on web applications.                   | Scans for network-based and web server vulnerabilities.          | Suitable for scanning both network and application vulnerabilities. | Fast scans, covers network and web vulnerabilities, easy to use. | Limited in-depth analysis for web apps compared to other tools. |
| **Qualys Web Application Scanning (WAS)** | Cloud-based DAST tool for Java applications.                                    | Continuous monitoring, automated scanning, vulnerability detection. | Ideal for businesses needing continuous and automated monitoring. | Cloud-based, automated vulnerability detection, integrates easily. | Can be expensive for smaller teams, requires an internet connection. |
| **Rapid7 InsightAppSec**      | Real-time dynamic security testing tool.                                        | Scanning for vulnerabilities in Java applications in real-time.  | Suitable for real-time, automated vulnerability detection.     | Real-time scanning, integrates well with CI/CD pipelines.        | Expensive, may require training to use effectively.              |
| **Checkmarx**                 | Offers both SAST and DAST for application security testing.                     | Integration with Java apps, real-time dynamic and static testing. | Good for organizations looking for a complete security testing suite. | Covers both static and dynamic testing, strong Java support.     | High cost, can be complex to set up and configure.               |


# Conclusion

Application Security Testing (AST) identifies and fixes security issues in software to prevent attacks. DAST tests apps during real-world attacks, helping find vulnerabilities early. Using tools like OWASP ZAP and Burp Suite ensures apps are secure before deployment, protecting both the app and the company's reputation.

#  Contact Information


| **Name**    | **Email address**         |
|-------------|---------------------------|
| Mohit Saini | mohit.saini.snaatak@mygurukulam.co |


# References

| **Link** | **Description** |
|------------------------------------------------------|------------------|
| https://www.ibm.com/topics/dynamic-application-security-testing| DAST and types |
| https://www.techmagic.co/blog/dast| DAST tool |
