# Jenkins Declarative Pipeline with Email and Slack Notifications

This pipeline demonstrates a **Jenkins Declarative Pipeline** that sends email and Slack notifications based on the success or failure of the build.

---

## Pipeline Overview

### Features:
1. **Notification Stage**:
   - A simple placeholder stage to mimic some actions.

2. **Post-Build Notifications**:
   - **Email Notification**:
     - Sends an email to the specified recipients in both success and failure scenarios.
   - **Slack Notification**:
     - Sends a Slack message to the defined channel in success and failure scenarios.

---

## Environment Variables

- **`email_recipients`**:
  - Defines the email address for notification.
  - Default: `nilesh.rajput.snaatak@mygurukulam.co`

- **`slack_channel`**:
  - Defines the Slack channel for sending notifications.
  - Default: `#project-notification`

- **`slack_webhook_creds_id`**:
  - Jenkins credential ID for Slack Webhook Token.
  - Default: `neelesh-slack-webhook`

### Author -> Neelesh Rajput (nilesh.rajput.snaatak@mygurukulam.co)
