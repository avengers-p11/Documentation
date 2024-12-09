# **Documentation and POC of Code Compilation in Java CI Checks**

| **Author** | **Created on** | **Version** | **Last updated by** | **Last edited on** | **L0 Reviewer** | **L1 Reviewer** | **L2 Reviewer** |
|------------|--------------|------------|-------------|------------|-----------|-----------|-----------|
| Mohit Saini | 29-11-24 |  | Mohit Saini | 29-11-24 | Khushi Malhotra | | |

![image](https://github.com/user-attachments/assets/8206a944-d9a6-47bc-bf4d-3a8cdacd64ea)



# Table of contents

1. [Introduction](#introduction)

2. [What is Compiler?](#what-is-compiler?)

3. [Why compiler?](#why-compiler?)

4. [Java compilation process](#java-compilation-process)

5. [Different Tools](#different-tools)

6. [Maven Java Compiler Tool](#maven-java-compiler-tool)  

7. [Maven](#what)

8. [Why Maven?](#why-maven?)

9. [Installation Steps of Maven](#installation-steps-of-maven)

10. [Conclusion](#conclusion)

11. [Contact Information](#contact-information)

12. [References](#references)

# Introduction

Code Compilation is like Translation. it's the process of converting human-readable code into machine-readable code. A software program called a compiler performs this translation

# What is Compiler?

A compiler is a special software program that acts like a translator. It takes your code, written in a human-readable language like Python or Java, and translates it into machine language. This process is called compilation.


# Why Compiler?

Code compilation is necessary because computers can only understand machine code. Code compilation in Java is the bridge between human-readable code and machine-executable instructions, enabling Java programs to run seamlessly on various platforms.

| **Reason**       | **Description**                                                                 |
|-------------------|---------------------------------------------------------------------------------|
| **Translation**   | Converts human-readable code into machine-readable instructions for execution.  |
| **Execution**     | Compiled languages run faster because they are translated into machine code before execution. |
| **Debugging**     | Errors are caught during compilation, making debugging easier and more effective. |


# Java compilation process

Java Compiler (javac) generates Bytecode

| **Step**               | **Description**                                                                                      |
|-------------------------|------------------------------------------------------------------------------------------------------|
| **Generating Bytecode** | `javac` compiles source code to platform-independent bytecode in `.class` files via parsing, analysis, and optimization. |
| **Verifying Bytecode**  | JVM verifies bytecode for type safety, security, and correctness before execution.                   |
| **Execution**           | JVM uses the Class Loader to load classes and the Execution Engine to interpret or JIT compile bytecode. |


![image](https://github.com/user-attachments/assets/c920303d-eaae-43b7-bd50-52bdf31d8951)

# Different Tools

| **Tool**            | **Description**                                                                 | **Advantages**                                                                 | **Why**                                                                                                                                           |
|---------------------|---------------------------------------------------------------------------------|-------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| **javac**           | The primary Java compiler that converts Java source code (`.java`) into bytecode (`.class`). | - Standard compiler for Java. <br> - Directly translates Java code into bytecode. | It’s the core tool for turning Java source code into executable bytecode that can run on the JVM.                                                           |
| **Ant**             | A build automation tool used for compiling Java code, running tests, and packaging projects. | - Highly customizable. <br> - Extensible through plugins.  | Automates the build process for Java applications, simplifying repetitive tasks like compilation, testing, and packaging.                                   |
| **Maven**           | A build automation tool that also handles dependencies, project management, and compiling Java code. | - Manages dependencies. <br> - Centralizes build configuration.               | Used for automating the build and dependency management process, ensuring consistent and repeatable builds across environments.                           |
| **Gradle**          | A flexible build tool that automates Java code compilation, testing, and packaging. | - Supports multiple languages. <br> - Offers faster builds with incremental compilation. | An advanced build automation tool known for its speed and flexibility, used in complex Java projects to manage dependencies and automate tasks efficiently. |

# Maven Java Compiler Tool

![image](https://github.com/user-attachments/assets/618806e9-7239-4f38-9b48-055a1544c574)

## Maven
Maven is a powerful build automation and project management tool primarily used for Java projects. It simplifies the build process by automating tasks like compiling source code, managing dependencies, running tests, and generating documentation.

## Why Maven?
Maven has become a popular choice for Java projects due to several key advantages over other build tools like Ant and Gradle.


| **Aspect**                | **Maven**                                      |
|---------------------------|------------------------------------------------|
| **Dependency Management**  | Central repo, auto-resolves dependencies.      |
| **Project Structure**      | Standardized structure, easy setup.            |
| **Build Lifecycle**        | Defined lifecycle (e.g., `compile`, `test`).   |
| **Configuration**          | Minimal setup, "convention over configuration".|
| **Community Support**      | Large community, frequent updates.             |
| **Ease of Use**            | Simple for standard projects, complex for large. |


# Installation Steps of Maven

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

##  **Step 7. Compile the code**
```
mvn compile 
```
![image](https://github.com/user-attachments/assets/afa1daac-19f8-4eb5-b286-2715d90b3484)

# Conclusion
Maven automates and simplifies Java code compilation, managing dependencies and build processes efficiently. Integrating Maven with CI/CD tools ensures consistent, error-free builds and streamlined development workflows.

# Contact Information

| **Name**    | **Email address**         |
|-------------|---------------------------|
| Mohit Saini | mohit.saini.snaatak@mygrurukulam.co |

# References

| **Link** | **Description** |
|----------------------------------------------------|--------------------|
| https://linuxize.com/post/how-to-install-apache-maven-on-ubuntu-20-04/ | Maven installation |
| https://www.geeksforgeeks.org/building-java-project-with-maven/ | Code Compilation |
