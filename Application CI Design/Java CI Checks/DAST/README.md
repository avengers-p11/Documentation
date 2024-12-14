#    **Documentation and POC of DAST (Dynamic Application Security Testing) in Java CI Checks**

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer L0**  | **Reviewer L1**   | **Reviewer L2**   |
|-----------------------|----------------|-------------|---------------------------|---------------------|------------------|-------------------|----------------|
| Mohit Saini      |   27-11-24       | v1 | Mohit Saini          |     09-12-24            |Khushi & Shreya    |      |     |

![image](https://github.com/user-attachments/assets/4aa0c132-1fbb-45bc-ad5f-2a631586676a)




**Table of Contents**

1. [**Introduction**](#introduction)
2. [**What is DAST?**](#what-is-dast)
3. [**Types of AST**](#types-of-ast)
4. [**Why DAST?**](#why-dast)
5. [**Different Tools  used in  DAST**](#different-tools-dast)
6. [**DAST using OWSAP ZAP**](#dast-using-owsap-zap)
7. [**Conclusion**](#conclusion)
8. [**Contact Information**](#contact-information)
9. [**References**](#references)



# Introduction
Application Security Testing (AST) is the process of finding and fixing security problems in software to keep it safe from attacks.This document describes the security testing of applications. 


# Types of AST

![image](https://github.com/user-attachments/assets/8ce0cc40-5f78-4ba2-8bcd-b3f622ac2692)

**1. Static Application Security Testing (SAST)**: Analyzes the source or binary code without running the application to find vulnerabilities early.

**2. Dynamic Application Security Testing (DAST)**: Tests a running application to find vulnerabilities that occur during runtime.

**3. Interactive Application Security Testing (IAST)**: Combines SAST and DAST by analyzing the application both at runtime and in the code.

**4. Software Composition Analysis (SCA)**: Scans open-source libraries and dependencies for known vulnerabilities.

**5. Penetration Testing**: Simulates real-world attacks to identify security weaknesses by ethical hackers.


# What is DAST?

Dynamic Application Security Testing (DAST) is a method of testing a web app by simulating attacks to find security weaknesses. It checks the app from the outside, like a hacker, and looks for any problems or vulnerabilities.

# Why DAST?

| **Point**                           | **Explanation**                                                                 |
|-------------------------------------|---------------------------------------------------------------------------------|
| **Helps developers find security issues** | DAST identifies security vulnerabilities early in the development process.     |
| **Catching problems early is cheaper** | It's easier and less expensive to fix issues when found early in the SDLC.     |
| **Unfound vulnerabilities lead to breaches** | Leaving vulnerabilities unchecked can lead to data breaches and financial loss. |
| **Unchecked vulnerabilities damage reputation** | Security issues can harm the company's reputation if they go unaddressed.     |
| **DAST reduces human error**        | Helps reduce mistakes made during the Software Development Life Cycle (SDLC).  |


# Different Tools used in DAST


| **Tool Name**                | **Description**                                                                 | **Features**                                                  | **Why**                                                   | **Pros**                                                            | **Cons**                                                            |
|------------------------------|---------------------------------------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|
| **OWASP ZAP**                 | Open-source security testing tool.                                              | Automated scanners, vulnerability detection, active and passive scanning. | Ideal for developers looking for a free, open-source solution for DAST. | Free, open-source, extensive documentation, active community. | Limited advanced features compared to paid tools. Can be complex to set up. |
| **Burp Suite**                | Comprehensive platform for web application security testing.                    | Intercepting proxy, vulnerability scanning, custom extensions.   | Perfect for penetration testers and security experts.           | Advanced scanning, customizable, integrates with other tools.   | Expensive, may require expertise to fully utilize.              |
| **Acunetix**                  | Automated security scanner for web applications.                                | Detects SQL injection, XSS, and other vulnerabilities.            | Great for quickly identifying common web vulnerabilities.       | Fast scanning, easy to use, covers a wide range of vulnerabilities. | Pricey, fewer customization options for advanced users.         |
| **AppSpider**                 | Dynamic application security testing tool.                                      | Scanning for Java frameworks, automated vulnerability discovery. | Ideal for automating security testing across Java applications. | Customizable, automates complex scans, supports Java frameworks. | High cost, can generate false positives if not tuned correctly.  |

# DAST using OWASP ZAP

## Steps 1. Update your OS
```
sudo apt update
```
![image](https://github.com/user-attachments/assets/25efe10a-a28c-43e0-93df-15433df596da)


## Steps 2. Install OWSAP ZAP
```
sudo snap install zaproxy --classic
```
![image](https://github.com/user-attachments/assets/ee3f6be2-2f44-4a2f-93d1-80ba231962ed)


## Steps 3. Launch OWSAP ZAP
```
zaproxy
```

Ensure that your application or api should be running before using this service.

![image](https://github.com/user-attachments/assets/a371523d-95e0-4d8b-88c1-44e3f3024146)

## Steps 4. Enter the API URL into the 'Attack' input field for scanning

![image](https://github.com/user-attachments/assets/08480cbc-13a6-4d47-9239-e7e1db242f0a)

## Steps 5. Wait for result
![image](https://github.com/user-attachments/assets/034011ce-c53e-439c-99c6-36c6c1f16d1e)


## Steps 6. Result

![image](https://github.com/user-attachments/assets/3fac393c-5c80-4bfb-af4e-58c12c0d3096)


 ## **Steps 7. Report** 
| Link         | Description         |
|--------------|------------------------|
| [DAST](https://github.com/avengers-p11/Documentation/blob/main/Application%20CI%20Design/Java%20CI%20Checks/DAST/JAVA-DAST.pdf)| Report |
#


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
