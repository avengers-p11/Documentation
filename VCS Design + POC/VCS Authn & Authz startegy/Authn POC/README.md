
# VCS Authentication POC

| **Author** | **Created on** | **Version** | **Last edited on** | **L0 Reviewer** |**L1 Reviewer** |**L2 Reviewer** |
|------------|----------------|-------------------|---------------------|----------|----------|----------|
| Anjali Dhiman  | 21-11-24      | V1  | 22-11-24            | Khushi Malhotra| | |

## Table of Contents
- [Introduction](#introduction)
- [Authentication in Git](#authentication-in-git)                   
- [General purpose Pre-Requisites](#general-purpose-pre-requisites)         
- [Configuration steps](#configuration-steps)
- [Step by Step procedure for authentication](#step-by-step-procedure-for-authentication).      
- [Best Practices for Git Authentication](#best-practices-for-git-authentication)
- [Conclusion](#conclusion) 
- [Contacts](#contacts) 
- [References](#references)  

## Introduction

Authentication is the process of verifying who someone is. It's like checking an ID card to make sure the person is who they claim to be. In digital terms, it usually involves entering a username and password, but can also include more secure methods like using fingerprint scans, face recognition, or special keys (called SSH keys) stored on your computer.

Once authenticated, the system knows it's really you trying to access it. Authentication is crucial for protecting your personal information and ensuring that only authorized users can access certain data or systems.



##  Authentication in Git
In Git, authentication means verifying the identity of a user trying to access or make changes to a repository. This process ensures that the person is who they claim to be before granting them access to the repository. Authentication methods in Git include:

| No. | Methord   | Description                                                                                                     |
|-----|-----------------------|-----------------------------------------------------------------------------------------------------------------|
| 1.  | 	Username and Password    | Users enter their credentials to authenticate.                 |
| 2.  | 	SSH Keys |Users set up secure cryptographic keys for authentication. |
| 3.  |   Personal Access Tokens (PATs) |  These are tokens generated for more secure access.|
| 4.  |  	OAuth Tokens  |  Used for single sign-on and integrated authentication.|

This verification step is crucial for protecting the repository from unauthorized access and maintaining the security and integrity of the code.



##  General purpose Pre-Requisites
   
| No. | Requirements        |
|-----|--------------------------|
| 1.  | Operating system    ( Windows/Mac/Linux )|
| 2.  | Hardware Memory(512 MB of RAM ) |
| 3.  | 	Disk Space (At least 100 MB for installation ) |
| 4.  | 	Git installation |
| 5.  |   Git Configuration |
 
##  Configuration steps
## Step by Step procedure for authentication
- **Step-1 Methord to set up username and token**

## **1. Open your GitHub account settings by clicking on your profile picture in the top right corner and selecting “Settings” from the dropdown 
menu.**

![image](https://github.com/user-attachments/assets/45eaa9b7-e743-4911-b7ac-efc36e46c422)



## **2. In the left sidebar, click on “Developer settings” and then select “Personal access tokens”.**


![image](https://github.com/user-attachments/assets/2ea57d47-dba7-4623-8439-40ff00ec904f)


## **3. Click on the “Generate new token” button.**

  
![image](https://github.com/user-attachments/assets/7db82e73-08fe-40f6-8d30-04986a0f0c11)

## **4. Enter your GitHub password**

![image](https://github.com/user-attachments/assets/61128266-afb4-41ab-9158-f81f5e68aff0)


## **5. Give your token a descriptive name in the “Note” field to easily identify it later.**


![image](https://github.com/user-attachments/assets/259f9fd5-a36b-496d-950c-65ef3ade85be)


## **6. Select the desired scopes for your token. For Git operations, you need to select the “repo” scope.**

![image](https://github.com/user-attachments/assets/60c181f4-f1be-49f1-9948-7f1bd950a0b6)


## **7. Click on the “Generate token” button at the bottom of the page.**

![image](https://github.com/user-attachments/assets/668a33f7-9448-4f1f-aa0e-953d03f6b60f)



#  **GitHub will generate a new personal access token for you. Make sure to copy this token and keep it in a safe place. Note that this token will only be displayed once, so make sure to copy it before leaving the page.**

- **Step-2 Configure Git with Your Username and Personal Access Token**

     Open a Terminal (command prompt).

  
- **Step-3  Set up your Git username and email**
     ```
     git config --global user.name "Your Name"
     ```
     ```
     git config --global user.email "your_email@example.com"
     ```

- **Step-4   Check if the username and email has been updated or not**
    
    ```
    git config --list
    ```

- **Step5. Clone a Repository Using Username and Personal acess token**
    
    Use the HTTPS URL of the repository to clone it.
    ```
    git clone https://github.com/username/repository.git
    ```

- **Step6. Finally  push through git push command**
     
    ```
    git push origin main
    ```

**When asked for username use the username of your profile** 

**When asked for password, enter the personal access token.**


##  Best Practices for Git Authentication
 1)	Use Strong, Unique Passwords: Avoid using easily guessable passwords and do not reuse passwords across multiple sites or services.


2)	Enable Two-Factor Authentication (2FA): Whenever possible, enable 2FA for your Git hosting service to add an extra layer of security.

	
3)	Keep Git Updated: Regularly update your Git installation to benefit from the latest security patches and features.

##  Conclusion

Git, a popular version control system (VCS), supports various authentication methods for secure repository access. Common methods include SSH keys, HTTPS with username and password, and personal access tokens. These ensure secure and authenticated interactions, maintaining code integrity and enabling efficient collaboration across development teams.

## Contacts

| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |  Anjaliopstree  |  https://github.com/Anjaliopstree  |


##  References

| Links | Description      |
|-----  |--------------------------|
| https://www.squash.io/how-to-authenticate-git-push-with-github-using-a-token/  |  For step by step guide for git personal acess token    | 






