# Jenkins Pipeline for FOSSA Dependency Scanning

This Jenkins pipeline automates the process of performing dependency scanning on a project using FOSSA, generating an HTML report, and sending email notifications with the results.

## Overview

This pipeline:
1. **Cleans the workspace** before starting the build.
2. **Clones the Git repository** from the specified URL.
3. **Runs the FOSSA dependency scanning** to detect and analyze dependencies.
4. **Generates an HTML report** of the FOSSA analysis and stores it.
5. **Sends email notifications** with the generated report, or notifies if the scan fails.

## Prerequisites

Before using this pipeline, make sure you have:
- Jenkins installed with the **Pipeline** plugin enabled.
- **FOSSA CLI** installed on the Jenkins node or agent.
- A **Jenkins Secret Text** credential for the FOSSA API key (e.g., `neelesh-fossa-token`).
- Access to the **FOSSA** account for generating reports.

## Pipeline Steps

### 1. **Clean Workspace**
   The workspace is cleaned at the beginning of the pipeline to ensure no leftover files from previous builds.

### 2. **Clone Repository**
   The repository is cloned from the specified URL (`https://github.com/OT-MICROSERVICES/attendance-api.git`) and the `main` branch is checked out.

### 3. **Dependency Scanning (FOSSA)**
   - The `FOSSA_API_KEY` is securely retrieved from Jenkins credentials using `withCredentials`.
   - The `fossa init` command initializes FOSSA in the project.
   - The `fossa analyze` command runs the scan.
   - The `fossa report --format html` command generates an HTML report (`fossa-report.html`).

### 4. **Publish FOSSA Report**
   The generated FOSSA report (`fossa-report.html`) is archived as an artifact for future reference and can be accessed later.

### 5. **Email Notification**
   - **Always**: If the FOSSA report is found, an email is sent to the defined recipients with the FOSSA report attached. If the report is not found, a message is printed indicating that the report is missing.
   - **Failure**: If the build fails, an email notification is sent informing the team of the failure, including the build log URL.

## Environment Variables

The following environment variables are used in the pipeline:
- `branch_name`: The name of the Git branch to check out (default: `main`).
- `repo_url`: The Git repository URL to clone (default: `https://github.com/OT-MICROSERVICES/attendance-api.git`).
- `fossa_token_id`: The Jenkins credential ID for the FOSSA API key (default: `neelesh-fossa-token`).
- `email_recipients`: The email address to send the notifications (default: `nilesh.rajput.snaatak@mygurukulam.co`).
- `fossa_report_name`: The name of the generated FOSSA report (default: `fossa-report.html`).


### Author -> Neelesh Rajput (nilesh.rajput.snaatak@mygurukulam.co)
