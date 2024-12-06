# Dependency Scanning POC

| **Created**     | **Version**   | **Author** | **Comment**       | **Reviewer**      |
|:----------------:|:-------------:|:-----------:|:------------------:|:-----------------:|
| 2-12-2024       | V1            | Raman Tripathi      | Initial Commit   |                   |
|                  | V2            | Raman Tripathi         | L1 Review        |                   |
|                  | V3            | Raman Tripathi        | L2 Review        |                   |
## Table of Contents
1. [Introduction](#1-introduction) 
2. [POC](#2-poc)
3. [Contact](#3-contact)
4. [References](#4-references)

## 1. Introduction
**What is Dependency Scanning in Golang CI?**

In modern software development, dependency scanning is an essential practice to ensure the security, stability, and reliability of a project. In the context of Go (Golang) projects, this involves identifying vulnerabilities in both your codebase and the third-party libraries (dependencies) that your project uses.

## 2. POC 


## Step 1: Clone or Access the API Project

If the API repository is hosted on a platform like GitHub, GitLab, or Bitbucket, you can clone it using the following command:

```bash
git clone https://github.com/OT-MICROSERVICES/employee-api.git
cd repository-name
```

## Step 2:   Go Project Setup



**Dependencies**

To get started, you need to install the following dependencies:

- [gorilla/mux](https://github.com/gorilla/mux) - A powerful URL router and dispatcher for Go.
- [logrus](https://github.com/sirupsen/logrus) - Structured logger for Go.

**Installation**

Run the following commands to install the necessary dependencies:

```bash
go get github.com/gorilla/mux
go get github.com/sirupsen/logrus

```



This will add the dependencies to the go.mod file, which tracks the Go dependencies for your project.

## Step 3: Inspect Dependencies Using go list
 
To check all the dependencies your Go project is using, including transitive dependencies, you can run the `go list` command:

```bash
go list -m all
```

This will display all the modules and dependencies for your project, helping you understand what is being used.

## Step 4. Clean Up Unused Dependencies with go mod tidy

The `go mod tidy` command is useful for cleaning up any unused dependencies and ensuring that the `go.mod` and `go.sum` files are in sync. It also helps to find potentially outdated or unnecessary dependencies.

```bash
go mod tidy
```

This command will remove any dependencies that are no longer needed and update your project’s dependency files.

## Step 5  Install GoSec

To install GoSec, follow these steps:

1. **Run the following command** to install GoSec:

   ```bash
   go install github.com/securego/gosec/v2/cmd/gosec@latest
   ```

   This will install the latest version of GoSec and place the binary in your `$GOPATH/bin` directory.

## Step 6: Verify GoSec Installation

To ensure GoSec is installed correctly, run the following command:

```bash
gosec --version
```

This should return the version of GoSec installed, confirming that the installation was successful.

## Step 7: Run GoSec to Scan the Employee API

Now that GoSec is installed, you can use it to scan your Go code for security vulnerabilities.

### Run GoSec on the Entire Project

Navigate to your project root directory (where `main.go` and `go.mod` are located), and run the following command:

```bash
gosec ./...
```

This will scan all Go files in the current directory and its subdirectories, including dependencies listed in your `go.mod` file.

 **GoSec Output**
```bash
2024/12/02 10:00:01 Gosec (v2.17.0) - High severity issues:
Severity: High
- Potential hard-coded password found (e.g. 'password') in main.go at line 12.
- Exploitable command injection found in handler.go at line 20.

Severity: Medium
- Weak cryptographic algorithm found in utils.go at line 15.
- HTTP handler uses insecure response header in api.go at line 30.
```
<img width="634" alt="image" src="https://github.com/user-attachments/assets/0624f694-6241-4fbe-a813-fdcde7c4775c">

## Contact 

For more information, feedback, or assistance, feel free to contact:
| Name         | Email address                       |
|--------------|-------------------------------------|
| Raman Tripahi | raman.tripathi.snaatak@mygurukulam.co  |

## References

1. [GoSec Documentation](https://github.com/securego/gosec)
2. [Snyk Official Site](https://snyk.io/)
3. [Dependabot Documentation](https://docs.github.com/en/github/administering-a-repository/keeping-your-dependencies-updated-automatically)
4. [GolangCI-Lint Documentation](https://golangci-lint.run/)
5. [Trivy GitHub Repository](https://github.com/aquasecurity/trivy)
