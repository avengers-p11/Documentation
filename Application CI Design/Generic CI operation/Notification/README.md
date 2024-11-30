
# Notification (Slack and Jenkins Integration) Setup

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 29-11-24      | Neelesh  Kumar             | 29-11-24           |  | | |     


Integrate Slack with Jenkins for real-time notifications and efficient DevOps communication.

##  Introduction
This guide will walk you through setting up Slack and Jenkins to collaborate, providing seamless communication and automation in your DevOps workflow.

##  Table of Contents
- [Prerequisites](#prerequisites)
- [Step 1: Create a Slack Account](#step-1-create-a-slack-account)
- [Step 2: Launch an EC2 Instance and Install Jenkins](#step-2-launch-an-ec2-instance-and-install-jenkins)
- [Step 3: Install Jenkins CI App on Slack](#step-3-install-jenkins-ci-app-on-slack)
- [Step 4: Install Slack Notification Plugin in Jenkins](#step-4-install-slack-notification-plugin-in-jenkins)
- [Step 5: Run a Sample Test](#step-5-run-a-sample-test)
- [Conclusion](#conclusion)

## 🛠️ Prerequisites
- An AWS account for launching an EC2 instance.
- A Slack account.
- Basic knowledge of Jenkins and AWS.

## 📝 Step 1: Create a Slack Account

1. Go to [Slack’s official website](https://slack.com) and click **Sign Up**.


2.Select your mail here to create an Account

3. Name your workspace `Jenkins` (or any name you prefer).
 
4. Optionally, invite teammates or skip this step.

5. Your Slack workspace and channel are now ready for use!


## 🖥️ Step 2: Launch an EC2 Instance and Install Jenkins

1. Launch an Ubuntu EC2 instance via AWS Console.
2. Use the following user data script to install Jenkins:
   ```bash
   #!/bin/bash
   sudo apt update -y
   wget -O - https://packages.adoptium.net/artifactory/api/gpg/key/public | sudo tee /usr/share/keyrings/adoptium-archive-keyring.gpg > /dev/null
   echo "deb [signed-by=/usr/share/keyrings/adoptium-archive-keyring.gpg] https://packages.adoptium.net/artifactory/deb $(awk -F= '/^VERSION_CODENAME/{print$2}' /etc/os-release) main" | sudo tee /etc/apt/sources.list.d/adoptium.list
   sudo apt update -y
   sudo apt install temurin-17-jdk -y
   /usr/bin/java --version
   curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo gpg --dearmor -o /usr/share/keyrings/jenkins-archive-keyring.gpg
   echo "deb [signed-by=/usr/share/keyrings/jenkins-archive-keyring.gpg] https://pkg.jenkins.io/debian-stable binary/" | sudo tee /etc/apt/sources.list.d/jenkins.list
   sudo apt update -y
   sudo apt-get install jenkins -y
   sudo systemctl start jenkins
   sudo systemctl status jenkins
   sudo cat /var/lib/jenkins/secrets/initialAdminPassword

### Step 3: Install Jenkins CI App on Slack
1. Open Slack and click on your workspace name at the top left.
2. Select **Settings & Administration** > **Manage Apps**.
   

3.Search for **Jenkins CI** and click **Add to Slack**.
 

4. Choose the Slack channel where you want to receive Jenkins notifications, then click **Add Jenkins CI Integration**.



5. Copy the **team subdomain** and **integration token** for later use in Jenkins.
 

### Step 4: Install Slack Notification Plugin in Jenkins
1. In Jenkins, navigate to **Manage Jenkins** > **Manage Plugins**.
   

2. Search for **Slack Notification Plugin** and install it.
4. After installation, configure the Slack credentials:
   - Go to **Manage Jenkins** > **Credentials** > **Global** > **Add Credentials**.
   - Select **Secret Text**, then enter the Slack integration token copied earlier.
     

5. **Configure the Slack settings in Jenkins:**
   - Go to **Manage Jenkins** > **Configure System**.
   - In the **Slack** section:
     - Set **Workspace** to your Slack team subdomain.
     - Select the credentials (integration token) you created earlier.
     - Set a default Slack channel for notifications.
       

6.**Create the Jenkins job:**
   - Go to Jenkins Dashboard and click on **New Item** or create a Pipeline job.
   - Add the following pipeline script to the job.

## Usage

Add this script to your pipeline job:

```groovy
def COLOR_MAP = [
    'FAILURE' : 'danger',
    'SUCCESS' : 'good'
]

pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo "Hello world"
            }
        }
    }
    post {
        always {
            script {
                def slackColor = COLOR_MAP[currentBuild.currentResult] ?: 'warning' // Default to 'warning' if the result is not explicitly defined

                echo 'Sending Slack Notifications'

                slackSend(
                    channel: '#channel-name', // Change your channel name
                    color: slackColor,
                    message: """
                    *${currentBuild.currentResult}:* Job ${env.JOB_NAME}
                    build ${env.BUILD_NUMBER}
                    More info at: ${env.BUILD_URL}
                    """
                )
            }
        }
    }
}
```



*** You will get a Notification in Slack ***



## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Neelesh kumar | nilesh.rajput.snaatak@mygurukulam.co || GitHub | URL |
|----------|---------|
|  devneelesh921  |  https://github.com/devneelesh921  |


## References
--------------
Slack and Jenkins Integration 

