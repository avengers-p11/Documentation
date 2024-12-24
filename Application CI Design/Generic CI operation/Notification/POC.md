
# Notification (Slack and Jenkins Integration) Setup POC

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 29-11-24      | Neelesh  Kumar             | 12-12-24           | Shreya jaiswal | | |     


Integrate Slack with Jenkins for real-time notifications and efficient DevOps communication.

##  Introduction
This guide will walk you through setting up Slack and Jenkins to collaborate, providing seamless communication and automation in your DevOps workflow.

##  Table of Contents
- [Prerequisites](#prerequisites)
- [Step 1: Create a Slack Account](#step-1-create-a-slack-account)
- [Step 2: Install Jenkins CI App on Slack](#step-3-install-jenkins-ci-app-on-slack)
- [Step 3: Install Slack Notification Plugin in Jenkins](#step-4-install-slack-notification-plugin-in-jenkins)
- [Step 4: Run a Sample Test](#step-5-run-a-sample-test)
- [Contacts](#contacts)
- [References](#References)

  
##  Prerequisites
- An AWS account for launching an EC2 instance.
- A Slack account.
- Basic knowledge of Jenkins and AWS.

##  Step 1: Create a Slack Account

1. Go to [Slack’s official website](https://slack.com) and click **Sign Up**.

2. Select your mail here to create an Account

3. Name your workspace `Jenkins` (or any name you prefer).
 
4. Optionally, invite teammates or skip this step.

5. Your Slack workspace and channel are now ready for use!



### Step 2: Install Jenkins CI App on Slack
1. Open Slack and click on your workspace name at the top left.

2. Select **Settings & Administration** > **Manage Apps**.
   
3.Search for **Jenkins CI** and click **Add to Slack**.

![Screenshot from 2024-12-23 16-02-11](https://github.com/user-attachments/assets/71c74c6c-65d3-4600-a266-0405a39653d8)
![Screenshot from 2024-12-23 16-02-42](https://github.com/user-attachments/assets/8a4a2145-67c1-4159-a6f0-a65aa505b88f)


4. Choose the Slack channel where you want to receive Jenkins notifications, then click **Add Jenkins CI Integration**.
![Screenshot from 2024-12-23 16-03-11](https://github.com/user-attachments/assets/e578382c-9866-4479-926a-0d2db44e708a)

5. Copy the **team subdomain** and **integration token** for later use in Jenkins.
![Screenshot from 2024-12-23 16-04-34](https://github.com/user-attachments/assets/eb31429d-c21d-45ff-8f6c-ee42f9720a3c)


### Step 3: Install Slack Notification Plugin in Jenkins
1. In Jenkins, navigate to **Manage Jenkins** > **Manage Plugins**.
2. Search for **Slack Notification Plugin** and install it.
![Screenshot from 2024-12-23 16-05-07](https://github.com/user-attachments/assets/75c83248-7742-4eae-907e-24d143324599)



 3. After installation, configure the Slack credentials:
   - Go to **Manage Jenkins** > **Credentials** > **Global** > **Add Credentials**.
   - Select **Secret Text**, then enter the Slack integration token copied earlier.
![Screenshot from 2024-12-23 16-06-04](https://github.com/user-attachments/assets/5feba79e-871f-452d-97be-8e9b91dc2281)
![Screenshot from 2024-12-23 16-06-39](https://github.com/user-attachments/assets/7c490c65-aaef-4fcd-b395-c6a13bede446)


 4. **Configure the Slack settings in Jenkins:**
   - Go to **Manage Jenkins** > **Configure System**.
   - In the **Slack** section:
     - Set **Workspace** to your Slack team subdomain.
     - Select the credentials (integration token) you created earlier.
     - Set a default Slack channel for notifications.
 ![Screenshot from 2024-12-23 16-20-55](https://github.com/user-attachments/assets/964d1bd5-f9f6-44c1-aff0-1d6ad8d77715)
 ![Screenshot from 2024-12-23 16-21-56](https://github.com/user-attachments/assets/a1d037bd-538a-4eff-968f-5e394f43547a)
 ![Screenshot from 2024-12-23 16-23-10](https://github.com/user-attachments/assets/f41ca00e-1384-442d-ab38-77c4a77caa3f)

## Step 4: Run a Sample Test   

   1.Trigger a build             
   2.Check the Slack channel you configured to ensure you receive build status notifications.
 
 ![Screenshot from 2024-12-23 16-23-41](https://github.com/user-attachments/assets/dbafb717-70e2-4f8f-a578-0e5e65373403)
 ![Screenshot from 2024-12-23 16-24-09](https://github.com/user-attachments/assets/400a9c17-8b92-436e-917a-578c51957f21)

 ## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Neelesh kumar | nilesh.rajput.snaatak@mygurukulam.co || GitHub | URL |
|----------|---------|
|  devneelesh921  |  https://github.com/devneelesh921  |


## References


| **Reference**                      | **Description**                                                                 | **Link**                                                                                   |
|------------------------------------|---------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| **Jenkins Slack Plugin**           | Official documentation for the Jenkins Slack Notification Plugin.               | [Jenkins Slack Plugin](https://plugins.jenkins.io/slack/)                                  |
| **Slack App Configuration Guide**  | Step-by-step guide to creating and configuring a Slack App for integration.     | [Slack App Configuration Guide](https://api.slack.com/authentication/basics)              |
| **Slack Plugin Configuration**     | Detailed instructions to configure Slack within Jenkins.                        | [Slack Plugin Configuration](https://plugins.jenkins.io/slack/#configuration)             |
| **Post-Build Notification Setup**  | Instructions for setting up Slack notifications in Jenkins job configurations.  | [Post-Build Notification Setup](https://plugins.jenkins.io/slack/#project-notifications)  |





