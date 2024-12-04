#    **Bugs Analysis Documentation and POC**

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer L0**  | **Reviewer L1**   | **Reviewer L2**   |
|-----------------------|----------------|-------------|---------------------------|---------------------|------------------|-------------------|----------------|
| Mohit Saini      |   26-11-24       | v1 | Mohit Saini          |     26-11-24            |    |      |     |

![image](https://github.com/user-attachments/assets/fa4b21db-e5e1-475e-8b14-296d4e3dda6c)


**Table of Contents**

1. [**Introduction**](#introduction)
2. [**What**](#what-is-bugs-analysis)
3. [**Why**](#why)
4. [**Different Tools**](#different-tools)
5. [**Tool POC**](#static-code-analysis-tools-sonarqube-poc)
6. [**Conclusion**](#conclusion)
7. [**Contact Information**](#contact-information)
8. [**References**](#references)



# Introduction
The Bug is the informal name of defects, which means that software or application is not working as per the requirement.
In software testing, a software bug can also be issue, error, fault, or failure. The bug occurred when developers made any mistake or error while developing the product.


# What is Bugs Analysis 

Bug analysis is like finding and fixing the mistakes for example your software is a cake. Sometimes, there can be mistakes in the recipe or the baking process, which can make the cake taste bad or look funny. These mistakes are like bugs in software. After fixing those mistakes in the cake recipe. We look for the problem, figure out why it happened, and then fix it so the next cake is perfect.

# Why

| **Reason**                 | **Description**                                  |
|----------------------------|--------------------------------------------------------|
| **Improve Code Quality**   | Finds mistakes in code early to make it better.        |
| **Enhance Performance**    | Makes the code run faster and smoother.                |
| **Ensure Security**        | Protects the code from attacks and problems.           |
| **Reduce Development Costs** | Saves money by fixing problems early.                 |
| **Boost User Satisfaction**| Makes the software work well for users.                |
| **Support Scalability**    | Helps the software grow and handle more users.         |


# Different Tools
Here are some tools for analyzing bugs for Java program. 

| **Tool Name**          | **Description**                                                                                    | **Why**                                                                | **Pros**                                                                 | **Cons**                                                                |
|------------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|------------------------------------------------------------------------|------------------------------------------------------------------------|
| **Java Debugger (JDB)** | A command-line debugger used to find and fix bugs in Java programs.                               | Helps in stepping through the code to identify logical errors.         | Lightweight and fast. Good for troubleshooting runtime issues.         | Command-line based; lacks graphical interface. Can be complex for beginners. |
| **PAR**                | A generate-and-validate tool that uses manually defined fix templates to repair bugs.               | Automates bug fixes based on predefined templates.                      | Reduces manual intervention. Can speed up bug fixing.                  | Limited to predefined fixes. May not cover all types of bugs.          |
| **QACrashFix**         | A tool that fixes Java crash bugs by mining fixes from Q&A websites.                               | Uses community-provided fixes to resolve crash bugs automatically.     | Leverages community knowledge. Can be effective for common bugs.       | Depends on available solutions in the community. May not be suitable for complex bugs. |
| **ARJA**               | A repair tool for Java based on multi-objective genetic programming.                               | Uses genetic algorithms to automatically generate bug fixes.           | Can generate novel fixes. Good for complex bug scenarios.              | Can be computationally expensive. Might produce false positives or incorrect fixes. |
| **NpeFix**             | An automatic repair tool specifically for fixing NullPointerException in Java.                  | Fixes one of the most common Java exceptions NullPointerException. | Focused on a specific, common issue. Saves time for developers.        | Limited to fixing only NullPointerException. May not be suitable for other bugs. |
| **Trac**               | An open-source bug-fixing tool written in Python that can find and fix errors in Java code, apps, libraries, and websites. | Provides an integrated system for issue tracking and fixing.           | Comprehensive bug tracking system. Integrates well with version control systems. | Requires setup and configuration. Not focused solely on Java.         |
| **Usersnap**           | A tool that allows users to submit bug reports and track the progress of fixes.                    | Collects user feedback and tracks bug fix status.                      | User-friendly interface. Helps gather real-time user feedback.        | May require additional configuration for integration. Limited debugging features. |
| **VisualVM**           | This is used for that identifies hot spots in code that are slowing down performance.                        | Helps optimize the performance of Java applications.                    | Good for identifying performance bottlenecks. Visual interface.        | Focuses on performance issues, not bugs. Can be resource-intensive.   |
| **JConsole**           | This is used for inspecting JMX metrics from Spring applications.                                        | Monitors and manages Java applications in real-time.                    | Useful for monitoring application health. Real-time diagnostics.      | More suitable for production environments. Limited bug-fixing capabilities. |
| **SLF4J Logging Facade** | This is used for setting meaningful log levels to assist with debugging.                               | Helps developers manage log messages effectively for easier bug tracking. | Simplifies log management. Supports various logging frameworks.        | Doesn’t directly fix bugs; only aids in bug detection. Requires proper logging setup. |
| **FindBugs**           | This is used for to find bugs in Java programs, especially runtime bugs.                               | Detects a wide range of issues including performance and security bugs. | Wide range of bug detection. Integrates well with IDEs and build tools. | May produce false positives. Does not cover all bug types.           |


# Static Code Analysis Tools SonarQube POC

## Pre-requisites 

## System Specifications

| **Specification**      | **Details**         |
|-------------------------|---------------------|
| **Operating System**    | Ubuntu 22.04      |
| **CPU**                | 2 vCPU             |
| **Volume**             | 20 GB              |
| **RAM**                | 4 GB               |


# Security ports

## System Specifications

| **Specification**      | **Details**         |
|-------------------------|---------------------|
| **Operating System**    | Ubuntu 22.04 / 20.04 LTS |
| **CPU**                | 2 vCPU             |
| **Volume**             | 20 GB              |
| **RAM**                | 4 GB               |
| **Security Ports**     | (Shown below)      |

### Security Ports

| **Port** | **Protocol** | **Source Side**    | **Destination Side** | **Use Case**                     |
|----------|--------------|--------------------|-----------------------|-----------------------------------|
| 22       | TCP          | Any                | Server               | SSH Access for remote login      |
| 80       | TCP          | Any                | Server               | HTTP traffic for web applications|
| 443      | TCP          | Any                | Server               | Secure HTTPS web traffic         |
| 5432     | TCP          | Application Server | Database Server      | PostgreSQL database access       |
| 9000     | TCP          | Any                | Server               |  SonarQube |


## 1. First create the instance t2.medium or t3.large.

## 2. Open the port

![image](https://github.com/user-attachments/assets/0d00a94e-47cd-4c37-b2fa-5ba2b58cfdf6)

# Step-by-step installation on Ubuntu
## **Step 1. Update and Upgrade System Packages**

```
sudo apt update
```
![image](https://github.com/user-attachments/assets/9b9ae16e-6312-4826-aae7-27788803d1bf)


```
sudo apt upgrade -y
```
![image](https://github.com/user-attachments/assets/a648c53b-4753-47fd-b3a6-9800bb73a66f)

## **Step 2. Java installation**

```
sudo apt install -y openjdk-17-jdk
```
![image](https://github.com/user-attachments/assets/204ef06f-6d5a-40d4-beff-3c765702f5c1)

##  **Step 3. verify the installed Java version**
```
java -version
```

## **Step 4. install and configure PostgreSQL**

#### 1. Adding the PostgreSQL repository.
```
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" /etc/apt/sources.list.d/pgdg.list'
```
![image](https://github.com/user-attachments/assets/33ef266f-10e4-4e04-8f69-0bd4f0a71c82)

#### 2. To proceed with installing and configuring PostgreSQL, add the PostgreSQL signing key.

```
wget -q https://www.postgresql.org/media/keys/ACCC4CF8.asc -O - | sudo apt-key add -
```
![image](https://github.com/user-attachments/assets/655cbe26-173d-425c-abed-32fffe288e18)

#### 3. To complete the PostgreSQL setup, proceed by installing PostgreSQL.
```
sudo apt install postgresql postgresql-contrib -y
```
![image](https://github.com/user-attachments/assets/3875f1ec-6e16-48c1-9329-30e824514193)

#### 4. Ensure the database server starts automatically upon reboot for seamless operation

```
sudo systemctl enable postgresql
```
![image](https://github.com/user-attachments/assets/c1ec225d-93e3-498f-9c2c-242d1ba0302d)

#### 5. Initiate the database server to begin operations.
```
sudo systemctl start postgresql
```

#### 6. Verify the current status of the database server.
```
sudo systemctl status postgresql
```

#### 7. Switch to the Postgres user account for further configuration.
```
sudo -i -u postgres
```
![image](https://github.com/user-attachments/assets/40bef5ea-2759-4bf4-97d4-9610a9d8c8ca)

#### 8. Create a new database user to manage the sqube database
```
createuser sona
```


#### 9. Log in to the PostgreSQL database to proceed with database operations.
```
psql
```

![image](https://github.com/user-attachments/assets/9b2fb362-3a73-4009-b827-3fef92f2886b)


 
#### 10. Set a strong password for the “sona” user. Use a password


ALTER USER sona WITH ENCRYPTED password 'Sona#123';

#### 11. Create a sqube database and assign the ownership to the “sona” user.
CREATE DATABASE sqube OWNER sona;

Grant all privileges on the “sqube” database to the “sona” user
GRANT ALL PRIVILEGES ON DATABASE sqube to sona;
![image](https://github.com/user-attachments/assets/43a19949-613c-48ea-958f-aa41c4e644af)

#### 12. To verify the creation of the database, use the following command
```
\l
```
To verify the creation of the database user, use the following command:
```
\du
```
![image](https://github.com/user-attachments/assets/0bea53d0-ed81-48ec-a55e-d99ca1ed0f26)

#### 13. To exit the PostgreSQL command-line interface, use the following command:
```
\q
```
#### 13.  To return to your non-root sudo user account, use the following command:
```
exit
```
![image](https://github.com/user-attachments/assets/7abfa498-bd09-49af-8879-12b3437aed30)



## **Step 5. Downloading and Installing SonarQube**

Install the zip utility, required for extracting the SonarQube files
```
sudo apt install zip -y
```
![image](https://github.com/user-attachments/assets/b7a5db7b-9b05-487e-9092-0eff78c47532)



## **Step 6. installing the latest version of SonarQube 10.4 Community Edition (free version)**

```
sudo wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-10.4.1.88267.zip
```

![image](https://github.com/user-attachments/assets/e8c2fd40-6589-4f0c-950e-da10bbf989bb)


## **Step 7. Move the unzipped files to the /opt/sonarqube directory**

```
sudo unzip sonarqube-10.4.1.88267.zip
sudo mv sonarqube-10.4.1.88267 sonarqube
sudo mv sonarqube /opt/
```

## **Step 8. Setting Up SonarQube: Adding Group and User**

```
sudo groupadd sona
sudo useradd -d /opt/sonarqube -g sona sona
```
![image](https://github.com/user-attachments/assets/ca173ef6-0730-4100-a8b6-8a1a59e59b02)



## **Step 9. Grant the “sona” user access to the /opt/sonarqube directory**

```
sudo chown -R sona:sona /opt/sonarqube
```

![image](https://github.com/user-attachments/assets/61b774fd-6e27-42e0-bb35-c4ebd6a03aa4)



## **Step 10. Edit the SonarQube configuration file located**

```
sudo nano /opt/sonarqube/conf/sonar.properties
```


## **Step 11. Uncomment the following lines in the SonarQube configuration file**

```
sonar.jdbc.username=sona
sonar.jdbc.password=password
sonar.jdbc.url=jdbc:postgresql://localhost:5432/sqube
```
![image](https://github.com/user-attachments/assets/2d051074-3552-45fd-8e2b-5d13b8d45b27)


## **Step 12. To edit the SonarQube script file**
```
sudo nano /opt/sonarqube/bin/linux-x86-64/sonar.sh
```


## **Step 13. Select the branch you want to merge**

```
RUN_AS_USER=sona
```
![image](https://github.com/user-attachments/assets/d74ff63b-e3c0-495b-8f83-5fe514fc4929)


## **Step 14. Create a new service file using a text editor**
```
sudo nano /etc/systemd/system/sonar.service
```


## **Step 15. Check for merge conflicts after creating the pull request, It’s now ready for review**

```
[Unit]
Description=SonarQube service
After=syslog.target network.target
[Service]
Type=forking
ExecStart=/opt/sonarqube/bin/linux-x86-64/sonar.sh start
ExecStop=/opt/sonarqube/bin/linux-x86-64/sonar.sh stop
User=sona
Group=sona
Restart=always
LimitNOFILE=65536
LimitNPROC=4096
[Install]
WantedBy=multi-user.target
```

![image](https://github.com/user-attachments/assets/af10bcfb-cfdc-4bf1-8015-0304377c063a)


## **Step 16. Enable the SonarQube service to start at boot**

```
sudo systemctl enable sonar
```


## **Step 17. start the SonarQube service**

```
sudo systemctl start sonar
```

```
sudo systemctl status sonar
```
![image](https://github.com/user-attachments/assets/4f138b22-9d7b-460e-a7fb-50a4b8285a97)



## **Step 18. To edit the sysctl configuration file**

```
sudo nano /etc/sysctl.conf
```


## **Step 18. Add the following lines to the sysctl configuration file (/etc/sysctl.conf)**

```
vm.max_map_count=262144
fs.file-max=65536
ulimit -n 65536
ulimit -u 4096
```

![image](https://github.com/user-attachments/assets/7cfcf710-2856-4438-9e13-bcc278d37d63)


## **Step 18. To apply the changes, reboot the system**
sudo reboot



## **Step 18. Access SonarQube in a web browser by entering your server’s IP address followed by port 9000**

```
http://100.26.240.39:9000
```
**Step 19. Log in to SonarQube using the username “admin” and password “admin”**
![image](https://github.com/user-attachments/assets/aceb6217-a3e7-474d-a903-3f9d3bfbba08)

Once logged in, SonarQube will prompt you to change your password. Enter the current password “admin” and then enter your new password twice as prompted.

![image](https://github.com/user-attachments/assets/658677aa-d66c-4b3d-8876-0e11ebf9bc6b)

**Step 20. Go to SonarQube and select the project**

![image](https://github.com/user-attachments/assets/170adf86-92c9-48a0-b5b5-af15d1502929)

**Step 21. Create a Local Project: Set up a new or existing project on your machine**

![image](https://github.com/user-attachments/assets/0b49d923-61a7-4120-ae5f-7558dc8c0d3c)

**Step 22. Configure the Project: Prepare your project for analysis by configuring the necessary files**
![image](https://github.com/user-attachments/assets/76d79553-2d6a-41ab-852a-b4ee40d505be)

**Step 23. Analysis your project which you want**

![image](https://github.com/user-attachments/assets/1da40957-0508-43c9-89e7-3916c6dd4feb)

**Step 24. Generate Token: Create an authentication token in SonarQube**

![image](https://github.com/user-attachments/assets/8a2cc014-c67c-437c-b045-509adb3a0765)

**Step 25. Copy the Token: Copy the generated SonarQube token to use for authentication when running the SonarScanner**

![image](https://github.com/user-attachments/assets/90fde3fa-0b9e-46bc-9f9f-8e474637e604)

**Step 26. Analyze your project** 

![image](https://github.com/user-attachments/assets/8b835153-c969-4c89-b066-5789850c98ea)

**Step 27.Run Analyze on your project**
![image](https://github.com/user-attachments/assets/5ac3feea-4186-4935-a3a7-e41c2dd8eecb)

**Step 28.Paste the scan command**

![image](https://github.com/user-attachments/assets/2f271634-5d44-421f-b3f3-c6dc526932e3)

**Step 29. After sucessfully run command**

![image](https://github.com/user-attachments/assets/900d6aa0-946d-41cf-bb16-4ba997ca5039)

**Step 30. Bugs anaylsis report**
![image](https://github.com/user-attachments/assets/f2a2c5ad-d3d7-4410-83fb-945dc15e8a87)



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
