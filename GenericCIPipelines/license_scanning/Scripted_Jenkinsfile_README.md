# Jenkins Pipeline for FOSSA Dependency Scanning

This Jenkins pipeline automates the process of running a dependency scan on a project using FOSSA, generating an HTML report, and sending email notifications with the scan results.

## Overview

This pipeline:
1. **Cleans the workspace** to remove any previous files.
2. **Clones the repository** from the specified Git URL and branch.
3. **Runs FOSSA dependency scanning** to analyze the project dependencies.
4. **Generates an HTML report** of the FOSSA analysis.
5. **Archives the generated FOSSA report**.
6. **Sends email notifications** with the FOSSA report attached or notifies if the scan fails.

## Prerequisites

Before using this pipeline, ensure that:
- Jenkins is set up with the **Pipeline** plugin enabled.
- **FOSSA CLI** is installed on the Jenkins agent.
- A **Jenkins Secret Text** credential for the FOSSA API key (e.g., `neelesh-fossa-token`) is configured.
- Access to the **FOSSA** account to generate dependency reports.

## Pipeline Steps

### 1. **Clean Workspace**
   The workspace is cleaned to ensure no leftover files from previous builds.

### 2. **Clone Repository**
   The repository is cloned from the specified URL (`https://github.com/OT-MICROSERVICES/attendance-api.git`) and the `main` branch is checked out.

### 3. **Dependency Scanning (FOSSA)**
   - Retrieves the FOSSA API key using `withCredentials`.
   - Runs `fossa init` to initialize the project for scanning.
   - Runs `fossa analyze` to perform the scan.
   - Generates an HTML report (`fossa-report.html`) with `fossa report --format html attribution`.

### 4. **Publish FOSSA Report**
   The generated FOSSA report (`fossa-report.html`) is archived as an artifact so that it can be accessed later.

### 5. **Email Notification**
   - **Always**: If the FOSSA report exists, an email is sent to the specified recipients with the report attached. If the report is not found, a message is printed indicating that no report was generated.
   - **Failure**: If the build fails, an email is sent notifying the team about the failure, including the build log URL for troubleshooting.

## Environment Variables

The following environment variables are used in the pipeline:
- `branch_name`: The name of the Git branch to be checked out (default: `main`).
- `repo_url`: The Git repository URL to clone (default: `https://github.com/OT-MICROSERVICES/attendance-api.git`).
- `fossa_token_id`: The Jenkins secret ID for the FOSSA API key (default: `neelesh-fossa-token`).
- `email_recipients`: The email address to send the notifications to (default: `nilesh.rajput.snaatak@mygurukulam.co`).
- `fossa_report_name`: The name of the generated FOSSA report (default: `fossa-report.html`).

### Author -> Neelesh Rajput (nilesh.rajput.snaatak@mygurukulam.co)
