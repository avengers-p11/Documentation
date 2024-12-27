# Creds Scanning Jenkins Pipeline - Scripted 

This Jenkins pipeline performs the following tasks:

1. **Cleans the workspace** before starting the build.
2. **Clones the repository** from a specified Git URL and branch.
3. **Runs a Gitleaks scan** on the repository to detect any sensitive information (e.g., passwords, API keys).
4. **Publishes the Gitleaks report** as an artifact.
5. **Sends email notifications** with the Gitleaks report attached after a successful scan or if the build fails.

## Pipeline Configuration

- **Branch Name**: `main`
- **Repository URL**: `https://github.com/OT-MICROSERVICES/attendance-api.git`
- **Gitleaks Report File Name**: `gitleaks-report.json`
- **Email Recipients**: `nilesh.rajput.snaatak@mygurukulam.co`

## Pipeline Stages

1. **Clean Workspace**: Cleans up the workspace to ensure a clean start for each build.
2. **Clone Repository**: Clones the repository from the given Git URL and branch (`main`).
3. **Run Gitleaks Scan**: Runs a Gitleaks scan to detect any sensitive data in the repository and generates a report.
4. **Publish Gitleaks Report**: Archives the Gitleaks report file as an artifact.

## Post Actions

- If the Gitleaks report is found, an email notification is sent with the report attached.
- If the pipeline fails, an email is sent notifying the failure with a link to the build logs.

### Author -> Neelesh Rajput (nilesh.rajput.snaatak@mygurukulam.co)
