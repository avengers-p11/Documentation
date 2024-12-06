# POC on Dynamic Application Security Testing (DAST) for Python Application
## Description of this POC 


![image](https://github.com/user-attachments/assets/171719a3-9f78-40bd-aaf8-4b9cd9242a85)

| **Author** | **Created on** | **Version** | **Last edited on** | **L0 Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Anjali Dhiman  | 04-12-24      | V1  | 06-12-24           | Khushi Malhotra |


## Table of Content: 
- [Introduction](#Introduction)
- [Pre-requisites](#Pre-requisites)
- [Step-by-Step setup Guide](#Step-by-step-Setup-Guide)
- [Conclusion](#Conclusion)
- [Contact Information](#Contact-Information)
- [References](#References)

## Introduction
Dynamic Application Security Testing (DAST) is a process of testing a running application for vulnerabilities by simulating external attacks. OWASP ZAP (Zed Attack Proxy) is a popular open-source DAST tool that helps in identifying security vulnerabilities in web applications. This document provides a step-by-step guide to creating a POC for DAST using OWASP ZAP.

## Pre-requisites
- [OWASP ZAP](https://www.zaproxy.org/) 
- A Running Application(JAVA) to Perform DAST.

![image](https://github.com/user-attachments/assets/98359f43-cbdc-4617-bbc5-2b6ed9f73405)


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
![image](https://github.com/user-attachments/assets/95ffc176-ae19-4576-bfa3-13aa07190cfb)



You can now start using OWASP ZAP to test the security of your web applications.After a few minutes, OWASP ZAP will open up.

![image](https://github.com/user-attachments/assets/73b5d624-9147-45c2-bf3f-9b9f437f3129)



**Step 4**: Click on the **Automated scan** option a interface will come out on which provide the URL of the application and click on **attack**. 

![image](https://github.com/user-attachments/assets/4a96a933-3907-47c1-8ecb-0589308ebaea)



OWASP ZAP will start  scanning  your application for  vulnerabilities .

![image](https://github.com/user-attachments/assets/61510b82-ae54-4fba-be6b-0580355b3b44)


**Step 5** : Analyze Results

 After the scan, navigate to the Alerts tab to see the list of identified vulnerabilities. Click on each **alert** to see details .

 ![image](https://github.com/user-attachments/assets/a11c4743-8635-416e-b142-2da9ef0ebdb8)


![image](https://github.com/user-attachments/assets/11ec0321-2756-456f-94f4-92f8540dd41b)


 **Step 6** : Report Generation: 

You can also Generate the Report of the analysis by click on the **Report** option and generate it in desired format (HTML, PDF,JSON etc.) for future References. 

![image](https://github.com/user-attachments/assets/e5199663-5308-4390-bb87-a58d107018b5)



After selecting the format,click on **Generate Report**. Your Report will be generated in your desired directory. 

![Screenshot from 2024-12-03 16-36-30](https://github.com/user-attachments/assets/f6e63bad-b94f-4e89-b7fe-6f03c1a6ab4a)

## Conclusion

Using OWASP ZAP for DAST is a powerful way to identify and mitigate security vulnerabilities in your web applications. By following the steps above, you can create a comprehensive POC demonstrating its capabilities and integration into your security workflow.

## Contacts

| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |  Anjaliopstree  |  https://github.com/Anjaliopstree  |

## Reference Links

| Links | Description |
|-------|-------------|
|https://techofide.com/blogs/how-to-install-owasp-zap-on-windows-and-linux/ | A step-by-step guide to installing OWASP ZAP on both Windows and Linux platforms. Useful for beginners starting with OWASP ZAP. |
| https://www.zaproxy.org/ | The official website for OWASP ZAP, providing documentation, downloads, and community support. Ideal for exploring all features of ZAP. |
