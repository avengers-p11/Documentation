# Jenkins AMI Build Decalartive Pipeline

This repository contains a Jenkins pipeline script that automates the process of building an AMI using HashiCorp Packer. The pipeline includes steps for validating the Packer template, building the AMI, and notifying the team via email and Slack.

## Prerequisites

1. **Jenkins Setup**:
   - Jenkins should be installed and configured.
   - Ensure the Jenkins agent has Packer installed and properly configured.

2. **Packer Template**:
   - A valid Packer template (`packer_template.json`) should be available in the repository.

3. **AWS Permissions**:
   - Ensure the AWS credentials used by Jenkins have permissions to create AMIs and manage EC2 resources.

4. **Email Configuration**:
   - Configure the Jenkins email plugin for notifications.

5. **Slack Configuration**:
   - Configure the Slack notification plugin and add the webhook credentials (`slack_webhook_creds_id`).

## Pipeline Configuration

### Environment Variables

| Variable               | Description                              |
|------------------------|------------------------------------------|
| `aws_region`           | AWS region where the AMI is created.    |
| `packer_template`      | Path to the Packer template JSON file.  |
| `email_recipients`     | Email addresses for notifications.      |
| `slack_channel`        | Slack channel for notifications.        |
| `slack_webhook_creds_id` | Credential ID for Slack webhook.       |
| `ami_name`             | Name of the AMI to be created.          |

### Pipeline Stages

1. **Checkout Code**:
   - Pulls the latest code from the source control repository.

2. **Validate Packer Template**:
   - Validates the Packer template to ensure correctness.

3. **Build AMI**:
   - Builds the AMI using Packer with the specified region and template.

### Notifications

- **Email**: Sends email notifications on success and failure to the specified recipients.
- **Slack**: Sends Slack notifications to the specified channel on success and failure.

## Usage

1. Clone this repository to your Jenkins server.
2. Configure the Jenkins job to use the `Jenkinsfile` or directly paste the pipeline script into the job.
3. Trigger the pipeline.

### Author -> Neelesh Rajput (nilesh.rajput.snaatak@mygurukulam.co)
