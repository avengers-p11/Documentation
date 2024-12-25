# Jenkins Scripted Pipeline with Email and Slack Notifications

## Overview
This repository contains a Jenkins Scripted Pipeline script designed to send notifications via email and Slack. The pipeline includes a single `Notification` stage, and it performs actions based on the build status, notifying the appropriate recipients in case of success or failure.

---

## Pipeline Features
- **Scripted Pipeline**: Written in the Jenkins Scripted Pipeline style.
- **Notifications**:
  - **Email Notification**: Sends build success or failure notifications to a specified email group.
  - **Slack Notification**: Posts build status messages to a specified Slack channel.

---

## Environment Configuration
The following environment variables are used in the pipeline:

| Variable                 | Description                                              |
|--------------------------|----------------------------------------------------------|
| `email_recipients`       | Email addresses of the recipients for notifications.     |
| `slack_channel`          | Slack channel for notifications (e.g., `#project-notification`). |
| `slack_webhook_creds_id` | Jenkins credential ID for the Slack webhook token.       |

---

## Pipeline Logic
### Stages:
1. **Notification**:
   - A simple stage that logs a message.

### Post-Build Actions:
- On **Success**:
  - Sends an email to `email_recipients` with the build details.
  - Sends a Slack message to the `slack_channel`.
- On **Failure**:
  - Sends an email to `email_recipients` with the failure details.
  - Sends a Slack message to the `slack_channel`.

### Author -> Neelesh Rajput (nilesh.rajput.snaatak@mygurukulam.co)
