#    **Documentation and POC of Bugs Analysis**

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer L0**  | **Reviewer L1**   | **Reviewer L2**   |
|-----------------------|----------------|-------------|---------------------------|---------------------|------------------|-------------------|----------------|
| Mohit Saini      |   26-11-24       | v1 | Mohit Saini          |     09-12-24            | Khushi & Shreya   |      |     |

![image](https://github.com/user-attachments/assets/fa4b21db-e5e1-475e-8b14-296d4e3dda6c)


**Table of Contents**

1. [**Introduction**](#introduction)
2. [**What is Bugs Analysis?**](#what-is-bugs-analysis?)
3. [**Why Bugs Analysis?**](#why-bugs-analysis?)
4. [**Different Tools used in Bugs Analysis**](#different-tools-used-in-bugs-analysis)
5. [**SonarQube Bugs Anaylysis**](#sonarqube-bugs-anaylysis)
6. [**Conclusion**](#conclusion)
7. [**Contact Information**](#contact-information)
8. [**References**](#references)



# Introduction
The Bug is the informal name of defects, which means that software or application is not working as per the requirement.
In software testing, a software bug can also be issue, error, fault, or failure. The bug occurred when developers made any mistake or error while developing the product.


# What is Bugs Analysis?

Bug analysis is like finding and fixing the mistakes for example your software is a cake. Sometimes, there can be mistakes in the recipe or the baking process, which can make the cake taste bad or look funny. These mistakes are like bugs in software. After fixing those mistakes in the cake recipe. We look for the problem, figure out why it happened, and then fix it so the next cake is perfect.

# Why Bugs Analysis?

| **Reason**                 | **Description**                                  |
|----------------------------|--------------------------------------------------------|
| **Improve Code Quality**   | Finds mistakes in code early to make it better.        |
| **Enhance Performance**    | Makes the code run faster and smoother.                |
| **Ensure Security**        | Protects the code from attacks and problems.           |
| **Reduce Development Costs** | Saves money by fixing problems early.                 |
| **Boost User Satisfaction**| Makes the software work well for users.                |
| **Support Scalability**    | Helps the software grow and handle more users.         |


# Different Tools used in Bugs Analysis
Here are some tools for analyzing bugs for Java program. 

| **Tool Name**          | **Description**                                                                                           | **Why**                                                                | **Pros**                                                                 | **Cons**                                                                |
|------------------------|-----------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|------------------------------------------------------------------------|------------------------------------------------------------------------|
| **Java Debugger (JDB)** | A command-line debugger used to find and fix bugs in Java programs.                                        | Helps in stepping through the code to identify logical errors.         | Lightweight and fast. Good for troubleshooting runtime issues.         | Command-line based; lacks graphical interface. Can be complex for beginners. |
| **PAR**                | A generate-and-validate tool that uses manually defined fix templates to repair bugs.                      | Automates bug fixes based on predefined templates.                      | Reduces manual intervention. Can speed up bug fixing.                  | Limited to predefined fixes. May not cover all types of bugs.          |
| **FindBugs**           | A static analysis tool that detects bugs in Java programs, especially runtime bugs.                        | Detects a wide range of issues including performance and security bugs. | Wide range of bug detection. Integrates well with IDEs and build tools. | May produce false positives. Does not cover all bug types.           |
| **SonarQube**          | A continuous inspection tool that performs automatic reviews of code to detect bugs, code smells, and security vulnerabilities. | Ensures code quality and identifies potential problems early.           | Provides detailed code analysis, integrates well with CI/CD pipelines. | Requires setup and configuration. Can be resource-intensive for large projects. |



# SonarQube Bugs Anaylysis 

# Steps to Create a Sonarqube Server

**Please refer to the reference link for the installation**
| Link         | Description         |
|--------------|------------------------|
| [Sonarqube Installation](https://github.com/avengers-p11/Documentation/blob/main/Application%20CI%20Design/Java%20CI%20Checks/Static%20Code%20Analysis/README.md#sonarqube-static-code-analysis)          |POC  |
#

# Step 1. Go to Sonarqube server and Login
![image](https://github.com/user-attachments/assets/87f4dc86-539f-4320-a929-25d7e88a3e04)


# Step 2. Go to SonarQube and select the project

![image](https://github.com/user-attachments/assets/170adf86-92c9-48a0-b5b5-af15d1502929)

# Step 3. Create a Local Project: Set up a new or existing project on your machine

![image](https://github.com/user-attachments/assets/0b49d923-61a7-4120-ae5f-7558dc8c0d3c)

# Step 4. Configure the Project: Prepare your project for analysis by configuring the necessary files
![image](https://github.com/user-attachments/assets/76d79553-2d6a-41ab-852a-b4ee40d505be)

# Step 5. Analysis your project which you want

![image](https://github.com/user-attachments/assets/1da40957-0508-43c9-89e7-3916c6dd4feb)

# Step 6. Generate Token: Create an authentication token in SonarQube

![image](https://github.com/user-attachments/assets/8a2cc014-c67c-437c-b045-509adb3a0765)

# Step 7. Copy the Token: Copy the generated SonarQube token to use for authentication when running the SonarScanner

![image](https://github.com/user-attachments/assets/90fde3fa-0b9e-46bc-9f9f-8e474637e604)

# Step 8. Analyze your project

![image](https://github.com/user-attachments/assets/8b835153-c969-4c89-b066-5789850c98ea)

# Step 9. Run Analyze on your project
![image](https://github.com/user-attachments/assets/5ac3feea-4186-4935-a3a7-e41c2dd8eecb)

# Step 10. Paste the scan command

![image](https://github.com/user-attachments/assets/2f271634-5d44-421f-b3f3-c6dc526932e3)

# Step 11. Execution was successful

![image](https://github.com/user-attachments/assets/900d6aa0-946d-41cf-bb16-4ba997ca5039)

# Step 12. Bugs anaylsis Result
![image](https://github.com/user-attachments/assets/f2a2c5ad-d3d7-4410-83fb-945dc15e8a87)

# Step 13. Report
| Link         | Description         |
|--------------|------------------------|
| [Artifact](https://github.com/avengers-p11/Documentation/blob/main/Application%20CI%20Design/Java%20CI%20Checks/Bugs%20Analysis/salary-0.1.0-RELEASE.jar.original)           |File |
#



# Conclusion

Bug analysis tools are like special helpers that find and fix these Lego mistakes. They check your code for errors, slow parts, and security problems. By using these tools, you can build better software that works correctly and is safe to use.

#  Contact Information


| **Name**    | **Email address**         |
|-------------|---------------------------|
| Mohit Saini | mohit.saini.snaatak@mygurukulam.co |


# References

| **Link** | **Description** |
|------------------------------------------------------|------------------|
| https://www.scaler.com/topics/is-used-to-find-and-fix-bugs-in-the-java-program/| Bugs Anlyasis |
| https://www.browserstack.com/guide/debugging-tools-for-java| Bugs Anlysis tool |
