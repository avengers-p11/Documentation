# POC on Dynamic Application Security Testing (DAST) for GoLang Application

![image](https://github.com/user-attachments/assets/acb58b84-6c76-4d03-ba78-2a64f435b571)

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
|Raman Tripathi| 6-12-24    | Version 1  | Raman Tripathi   | 6-12-24       |

## Table of Content: 
- [Introduction](#Introduction)
- [Pre-requisites](#Pre-requisites)
- [Step-by-Step setup Guide](#Step-by-step-Setup-Guide)
- [Conclusion](#Conclusion)
- [Contact Information](#Contact-Information)
- [References](#References)

## Introduction
This POC demonstrates the use of Dynamic Application Security Testing (DAST) to identify security vulnerabilities in GoLang-based applications. Using OWASP ZAP, we analyze the application’s resilience against potential security threats by simulating attacks.

## Pre-requisites
- [OWASP ZAP](https://www.zaproxy.org/) 
- A running GoLang application to perform DAST.

<img width="635" alt="image" src="https://github.com/user-attachments/assets/1e036e63-066d-4efc-af92-9ef4dbbbe187">


# Step-by-Step Setup Guide

**Step 1**: Update Your Linux System

Before installing OWASP ZAP, it's essential to update your system to ensure that you have the latest packages and security patches. To update your system, open the terminal and type the following command:
```
sudo apt update
```
**Step 2**: Install OWASP ZAP

Once your system is up to date, you can install OWASP ZAP. To do so, type the following command in the terminal:
```
sudo snap install zaproxy --classic
````
**Step 3**: Launch OWASP ZAP

Once the installation is complete, you can launch OWASP ZAP from the application menu or the command line. To launch it from the command line, type the following command:
```
zaproxy
```
<img width="631" alt="image" src="https://github.com/user-attachments/assets/41d6744b-94b5-45b8-80cd-f64c08203c3e">

You can now start using OWASP ZAP to test the security of your web applications.After a few minutes, OWASP ZAP will open up.

<img width="634" alt="image" src="https://github.com/user-attachments/assets/58f2b114-300c-4582-88a3-03282b47b396">

**Step 4**: Click on the **Automated scan** option a interface will come out on which provide the URL of the application and click on **attack**. 

<img width="643" alt="image" src="https://github.com/user-attachments/assets/69708d09-3ca5-4dfc-b6e6-dafa72d467d1">

OWASP ZAP will start  scanning  your application for  vulnerabilities .

<img width="635" alt="image" src="https://github.com/user-attachments/assets/9962765f-4051-4695-a8e9-1ac4ab8bcb7e">

**Step 5** : Analyze Results

 After the scan, navigate to the Alerts tab to see the list of identified vulnerabilities. Click on each **alert** to see details .

<img width="630" alt="image" src="https://github.com/user-attachments/assets/962b4cad-6af7-44b6-ac97-13c0a13f0755">

 **Step 6** : Report Generation: 

You can also Generate the Report of the analysis by click on the **Report** option and generate it in desired format (HTML, PDF,JSON etc.) for future References. 

<img width="458" alt="image" src="https://github.com/user-attachments/assets/4d3b5513-0c0b-481e-9f30-e20738550802">

After selecting the format,click on **Generate Report**. Your Report will be generated in your desired directory. 

<img width="631" alt="image" src="https://github.com/user-attachments/assets/a1036e83-f5b4-4fbf-b3b6-3d6c566d1fc5">


## Conclusion

DAST using OWASP ZAP for GoLang applications effectively uncovers security vulnerabilities by simulating real-world threats. By incorporating DAST into your CI/CD pipelines, you ensure your applications remain secure and resilient against evolving attack vectors.

## Contact Information

For more information, feedback, or assistance, feel free to contact:
| Name         | Email address                       |
|--------------|-------------------------------------|
| Raman Tripahi | raman.tripathi.snaatak@mygurukulam.co  |


## Reference Links

| Links | Description |
|-------|-------------|
|https://techofide.com/blogs/how-to-install-owasp-zap-on-windows-and-linux/ | A step-by-step guide to installing OWASP ZAP on both Windows and Linux platforms. Useful for beginners starting with OWASP ZAP. |
| https://www.zaproxy.org/ | The official website for OWASP ZAP, providing documentation, downloads, and community support. Ideal for exploring all features of ZAP. |
