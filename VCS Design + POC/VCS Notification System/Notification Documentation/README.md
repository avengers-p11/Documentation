# VCS Notification Documentation

| **Author** | **Created on** | **Version** | **Last edited on** | **Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Raman Tripathi  | 17-11-24      |   | 17-11-24           |  |

## Table Of Contengt
- [Introduction](#introduction)
- [Pre-requisites](#pre-requisites)
- [Step-by-Step Setup Guide](#step-by-step-setup-guide)
- [Best practices](#best-practices)
- [Conclusion](#conclusion)
- [Contacts](#contacts)
- [References](#references)
  
## Introduction

The VCS Notification System is designed to send real-time notifications about various events in a version control system (e.g., Git). This system can notify users about pushes, pull requests, commits, and branch changes in a repository. It aims to enhance collaboration and keep teams informed about important code changes.

## Pre-requisites

Before you begin setting up the VCS Notification System, ensure you have the following software/tools installed on your system:

| Requirement                 | Description                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| Git                         | A distributed version control system for tracking changes in code.          |
| Node.js (v14 or later)      | JavaScript runtime for building server-side applications.                   |
| npm (v6 or later)           | Package manager for managing Node.js dependencies.                          |
| Webhook Endpoint (optional) | A server or service to receive and handle webhook notifications (e.g., Slack, email server, etc.). |

## Step-by-Step Setup Guide

Follow the steps below to set up the VCS Notification System:

### 1. Clone the Repository

Clone this repository to your local machine.

```bash
git clone https://github.com/your-repository/vcs-notification-system.git
cd vcs-notification-system
```
### 2. Install Dependencies 

Install the required Node.js packages using npm.

```bash
npm install
```
### 3. Configure Notification Settings
Open the config.json file and configure the necessary settings such as:

VCS webhook URL (GitHub, GitLab, Bitbucket, etc.)
Notification channels (e.g., Slack, email)
Webhook URL(s) for your preferred notification channels  

Example:
```json
{
  "vcs": {
    "url": "https://api.github.com/webhooks",
    "events": ["push", "pull_request", "commit"]
  },
  "notifications": {
    "slack": {
      "webhookUrl": "https://hooks.slack.com/services/TOKEN"
    },
    "email": {
      "smtpServer": "smtp.example.com",
      "emailFrom": "notifications@example.com",
      "emailTo": "dev-team@example.com"
    }
  }
}
```

### 4. Set Up Webhooks in VCS

#### For GitHub:

i). **Go to the repository's settings**:
   - Navigate to your GitHub repository.
   - In the upper-right corner, click the **Settings** tab.

ii). **Add a new webhook**:
   - In the left sidebar, under **"Webhooks"**, click **Add webhook**.
   
iii). **Enter the webhook URL**:
   - In the **Payload URL** field, enter the webhook URL from your `config.json` file.
   
iv). **Select the content type**:
   - Under **Content type**, select `application/json` to send JSON payloads.

v). **Choose the events to trigger notifications**:
   - Under **"Which events would you like to trigger this webhook?"**, select the events you want to receive notifications for:
     - **Push** (for push events)
     - **Pull requests** (for pull request events)
     - **Commit** (for commit events)
     - Or select **Let me select individual events**, and choose your desired events.
   
vi). **Save the webhook**:
   - Once you've configured the webhook, click **Add webhook** to save your settings.

#### For GitLab:

i). **Go to the project settings**:
   - Navigate to your GitLab project.
   - In the left sidebar, click on **Settings**, then select **Webhooks** under the **Integrations** section.

ii). **Add a new webhook**:
   - In the **URL** field, enter the webhook URL from your `config.json` file.

iii). **Select the desired events**:
   - In the **Trigger** section, select the events you want to receive notifications for:
     - **Push events** (for push notifications)
     - **Merge request events** (for merge requests)
     - **Tag push events** (for tags)
     - Or any other events you want to monitor.
   
iv). **Save the webhook**:
   - After configuring the events, click the **Add webhook** button to save your settings.

### 5. Run the Notification Server
Once your webhook configuration is complete, you can start the server to listen for events and send notifications.

```bash
npm start
```

The server will now run, listen for VCS events, and notify users based on your configuration.

## Best Practices

| Best Practice                           | Description                                                                 |
|-----------------------------------------|-----------------------------------------------------------------------------|
| **Use Separate Configuration Files**    | Keep environment-specific settings (e.g., API keys) in separate files or environment variables to enhance security. |
| **Implement Logging**                   | Implement logging to capture events and issues, helping you troubleshoot any notification-related problems. |
| **Use Retry Mechanisms**                | Ensure that the system can retry sending notifications in case of temporary failures (e.g., network issues). |
| **Ensure Secure Webhook Endpoints**     | Use HTTPS for webhook URLs to ensure that communication is secure. |
| **Rate Limiting & Throttling**          | Implement rate limiting for external services (like Slack) to avoid sending too many requests in a short period. |

## Conclusion

The VCS Notification System is a powerful tool to keep your team updated about important code changes in real-time. By setting up webhooks and configuring notification channels, you can streamline your development process and improve collaboration. 

Ensure you follow the best practices outlined above to maintain a secure, reliable, and efficient notification system. This will not only improve the user experience but also help you avoid common pitfalls and ensure smooth communication within your team.

## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Raman Tripathi | raman.tripathi.snaatak@mygurukulam.co |

| GitHub | URL |
|----------|---------|
|  Raman-tripathi07  |  https://github.com/Raman-tripathi07  |

## References

| Reference                           | Link                                                        |
|-------------------------------------|-------------------------------------------------------------|
| **GitHub Webhooks Documentation**   | [GitHub Webhooks Docs](https://docs.github.com/en/developers/webhooks-and-events/webhooks) |
| **GitLab Webhooks Documentation**   | [GitLab Webhooks Docs](https://docs.gitlab.com/ee/administration/webhooks.html) |
| **Node.js Official Website**        | [Node.js](https://nodejs.org/en/)                            |
| **Slack Webhooks Documentation**    | [Slack Webhooks](https://api.slack.com/messaging/webhooks)   |


