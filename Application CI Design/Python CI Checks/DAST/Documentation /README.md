# Python CI Checks | DAST (Dynamic Application Security Testing)

![image](https://github.com/user-attachments/assets/300e1d46-8458-4570-a568-1c0c24c5500f)


| **Author** | **Created on** | **Version** | **Last edited on** | **L0 Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Anjali Dhiman  | 04-12-24      | V1  | 06-12-24           | Khushi Malhotra |

## Table of Contents
1. [Introduction](#introduction)
2. [What is DAST?](#what-is-dast)
3. [Why DAST?](#why-dast)
4. [Different Tools for DAST](#different-tools-for-dast)
5. [Comparison of DAST Tools](#comparison-of-dast-tools)
6. [Advantages of DAST](#advantages-of-dast)
7. [Proof of Concept (POC)](#proof-of-concept-poc)
8. [Best Practices](#best-practices)
9. [Recommendation/Conclusion](#recommendationconclusion)
10. [Contact Information](#contact-information)
11. [References](#references)

## Introduction
In the era of continuous integration and continuous deployment, ensuring the security of applications is paramount. Dynamic Application Security Testing (DAST) plays a crucial role in identifying vulnerabilities in running applications by simulating attacks. This documentation provides a comprehensive guide on implementing DAST in Python CI pipelines.

## What is DAST ?
Dynamic Application Security Testing (DAST) is a black-box testing method where an application is tested from the outside by examining exposed interfaces and inputs to find vulnerabilities. It involves simulating attacks on a running application to identify security flaws that could be exploited by real attackers.

## Why DAST ?

| **Reason**                     | **Description**                                                                 |
|--------------------------------|---------------------------------------------------------------------------------|
| **Identify Real-World Vulnerabilities** | Helps in identifying vulnerabilities that could be exploited in real-world scenarios. |
| **Integration with CI/CD**     | Ensures automated and continuous security testing in CI/CD pipelines, detecting vulnerabilities early. |
| **Comprehensive Testing**      | Uncovers vulnerabilities static analysis might miss, such as issues with authentication, authorization, and data leakage. |


## Different Tools for DAST

| **Tool**         | **Description**                                                                 |
|-------------------|---------------------------------------------------------------------------------|
| **OWASP ZAP**     | An open-source tool for finding vulnerabilities in web applications.           |
| **Burp Suite**    | A comprehensive platform for web application security testing.                 |
| **Arachni**       | An open-source scanner that can identify a wide range of security issues.      |
| **Nikto**         | A web server scanner that performs comprehensive tests against web servers.    |


## Comparison of DAST Tools
| Tool         | Open Source | Ease of Use | Integration with CI/CD | Supported Protocols | Community Support |
|--------------|-------------|-------------|------------------------|---------------------|-------------------|
| OWASP ZAP    | Yes         | High        | High                   | HTTP, HTTPS         | High              |
| Burp Suite   | No          | High        | Medium                 | HTTP, HTTPS         | High              |
| Arachni      | Yes         | Medium      | Medium                 | HTTP, HTTPS         | Medium            |
| Nikto        | Yes         | Medium      | Medium                 | HTTP, HTTPS         | Medium            |

## Advantages of DAST

| **Advantage**          | **Description**                                                                 |
|-------------------------|---------------------------------------------------------------------------------|
| **Early Detection**     | Detect vulnerabilities early in the development process.                       |
| **Automated Testing**   | Automate security testing within CI/CD pipelines.                              |
| **Broad Coverage**      | Test for a wide range of security issues.                                      |
| **Real-World Simulation** | Simulate real-world attack scenarios.                                         |


## Proof of Concept (POC)
For detailed insights into how to perform DAST for Python application, you can view our Proof of Concept (POC) document. Click [here](https://github.com/MyGurukulam-p11/Documentation/blob/main/Application-CI-Design/Python%20CI%20Checks/DAST/POC/README.md)




## Best Practices

| **Practice**            | **Description**                                                                 |
|--------------------------|---------------------------------------------------------------------------------|
| **Regular Scans**        | Perform regular DAST scans to ensure continuous security monitoring.            |
| **Integrate Early**      | Integrate DAST into your CI/CD pipeline early in the development process.       |
| **Review and Act**       | Regularly review DAST reports and take action on identified vulnerabilities.    |
| **Combine with SAST**    | Use DAST in conjunction with SAST (Static Application Security Testing) for comprehensive security coverage. |


## Conclusion
Integrating DAST into your Python CI pipeline is a critical step towards ensuring the security of your applications. By regularly performing DAST, you can identify and address vulnerabilities early, reducing the risk of security breaches. Tools like OWASP ZAP provide a powerful and flexible solution for DAST, making it easier to automate and integrate into your CI/CD workflows.

## Contacts

| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |  Anjaliopstree  |  https://github.com/Anjaliopstree  |

## References

| Reference                    | Link                                                                            |
|------------------------------|---------------------------------------------------------------------------------|
| OWASP ZAP                    | [OWASP ZAP](https://www.zaproxy.org/)                                           |
| Burp Suite                   | [Burp Suite](https://portswigger.net/burp)                                      |
| Arachni                      | [Arachni](https://www.arachni-scanner.com/)                                     |
| Nikto                        | [Nikto](https://cirt.net/Nikto2)                                                |
| DAST Documentation           | [DAST Documentation](https://owasp.org/www-community/Activities/Dynamic_Application_Security_Testing) |
