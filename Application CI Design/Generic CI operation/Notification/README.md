
# Notification (Slack and Jenkins Integration) Setup

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 29-11-24      | Neelesh  Kumar             | 12-12-24           |  | | |     


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

![Screenshot from 2024-12-12 18-49-36](https://github.com/user-attachments/assets/4bd43765-d965-422c-9b59-e7ead8b3669f)
![Screenshot from 2024-12-12 18-49-49](https://github.com/user-attachments/assets/23700090-bc13-4095-91eb-326c9c475fb9)


4. Choose the Slack channel where you want to receive Jenkins notifications, then click **Add Jenkins CI Integration**.
![Screenshot from 2024-12-12 18-51-13](https://github.com/user-attachments/assets/34a65138-9eb9-4dde-979d-027a241eb112)

5. Copy the **team subdomain** and **integration token** for later use in Jenkins.
![Screenshot from 2024-12-12 18-51-53](https://github.com/user-attachments/assets/aac5bbae-4279-45c9-8e1d-847ac3a4497a)


### Step 3: Install Slack Notification Plugin in Jenkins
1. In Jenkins, navigate to **Manage Jenkins** > **Manage Plugins**.
2. Search for **Slack Notification Plugin** and install it.
![Screenshot from 2024-12-12 18-54-31](https://github.com/user-attachments/assets/136e6420-f2b0-4c6b-bb64-445e4fa17fdc)



 3. After installation, configure the Slack credentials:
   - Go to **Manage Jenkins** > **Credentials** > **Global** > **Add Credentials**.
   - Select **Secret Text**, then enter the Slack integration token copied earlier.
![Screenshot from 2024-12-12 20-22-36](https://github.com/user-attachments/assets/fed4ec2e-0476-4d16-baa7-77a96e487a8f)
![Screenshot from 2024-12-12 20-22-50](https://github.com/user-attachments/assets/395a52b7-9608-455f-8e0c-cceed447797e)


 4. **Configure the Slack settings in Jenkins:**
   - Go to **Manage Jenkins** > **Configure System**.
   - In the **Slack** section:
     - Set **Workspace** to your Slack team subdomain.
     - Select the credentials (integration token) you created earlier.
     - Set a default Slack channel for notifications.
 ![Screenshot from 2024-12-12 20-23-58](https://github.com/user-attachments/assets/a6c075b0-afec-4875-89ee-b2d99dbda0f6)
 ![Screenshot from 2024-12-12 20-24-12](https://github.com/user-attachments/assets/08b9b790-cb71-4a04-87ca-e85c73b4ea21)
 ![Screenshot from 2024-12-12 19-33-24](https://github.com/user-attachments/assets/946dce6e-af28-4e0f-a92c-2423d6a7721e)

## Step 4: Run a Sample Test   

   1.Trigger a build             
   2.Check the Slack channel you configured to ensure you receive build status notifications.
 
 ![Screenshot from 2024-12-12 19-48-42](https://github.com/user-attachments/assets/e794af0b-caf7-45bf-bc18-73d21e40ba9e)

 ![Screenshot from 2024-12-12 19-48-34](https://github.com/user-attachments/assets/2a28a245-6209-41fb-8fe6-7203d82e5521)


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




