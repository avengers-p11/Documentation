# Generic CI Operation: Credential Scanning

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 29-11-24      | Neelesh  Kumar             | 8-12-24           |  | | |     

### Table of Contents
- [Introduction](#introduction)
- [What is Credential Scanning?](#what-is-credential-scanning)
- [Why Credential Scanning?](#why-credential-scanning)
- [Tools for Credential Scanning](#tools-for-credential-scanning)
- [Comparison of Credential Scanning Tools](#comparison-of-credential-scanning-tools)
- [Advantages of Credential Scanning](#advantages-of-credential-scanning)
- [Proof of Concept (POC)](#proof-of-concept-poc)
- [Best Practices](#best-practices)
- [Recommendation](#recommendation)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [Refrences](#refrences) 

### Introduction
Credential scanning is a process used in Continuous Integration (CI) to automatically check code for sensitive information like passwords, API keys, or tokens. It helps ensure that no critical data is accidentally shared in the codebase or in public repositories, which could lead to security issues.

As part of the CI pipeline, where code is built and tested automatically, credential scanning ensures that sensitive information doesn’t slip through unnoticed. This process is especially important in modern, fast-paced development environments where mistakes can happen.

### What is Credential Scanning?
Credential scanning is simply the act of scanning through your code, configuration files, or logs to check for sensitive information, like:

- **Passwords**
- **API keys**
- **Tokens (used to access services securely)**

If any of these are found in the code, they could be a security risk because attackers could steal and misuse them. Credential scanners identify patterns that match sensitive data, helping you catch and fix these issues early.

### Why Credential Scanning?

- **Prevents Leaks**: Sensitive information like API keys and passwords can be misused by attackers if exposed in code repositories. Scanning helps prevent such data leaks.
- **Automated Protection**: CI systems run multiple code checks quickly. Credential scanning ensures that no sensitive information is accidentally included in the build.
- **Compliance**: Some industries (healthcare, finance) require companies to keep sensitive data secure. Scanning helps organizations meet these standards.
- **Security Best Practice**: It’s a good practice to keep all credentials safe and out of your code. Regular scanning makes sure this happens.

 ### Tools for Credential Scanning

| Tool          | Description                                                                | 
|---------------|--------------------------------------------------------------------------|
| **GitGuardian** | Monitors repositories in real-time to detect hardcoded secrets and sends alerts when something is found. |
| **TruffleHog**  | Looks for sensitive data by scanning for high-entropy strings, which might represent passwords or keys.
| **Gitleaks**    | Scans Git repositories for sensitive information in the code history.   | 
| **AWS Macie**   | Specifically for AWS environments, it scans your storage (like S3 buckets) for sensitive data. | 
| **SpectralOps** | Focuses on identifying secrets in code and configuration files and integrates well with CI pipelines. | 



### Comparison of Credential Scanning Tools

| Tool         | Features                                                                 | Strengths                                                            | Limitations                                                     |
|--------------|--------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------------------------------------------------|
| **GitGuardian** | 1. Real-time monitoring and alerts <br> 2. Integration with GitHub, GitLab <br> 3. Detects hardcoded secrets and sensitive data | 1. Catches issues immediately <br> 2. Easy to integrate into CI/CD <br> 3. Provides detailed alerts and reports | 1. Expensive for larger teams <br> 2. Limited free tier for small teams <br> 3. Can be overwhelming with too many alerts |
| **TruffleHog**  | 1. Scans for high-entropy strings (API keys, secrets) <br> 2. Regex scanning <br> 3. Supports a wide variety of data sources | 1. Works with many data types <br> 2. Flexible scanning methods <br> 3. Good for scanning past commit history | 1. Can produce false positives <br> 2. Complex setup for fine-tuning <br> 3. Manual effort required to interpret results |
| **Gitleaks**    | 1. Simple command-line interface (CLI) <br> 2. CI/CD pipeline integration <br> 3. Scans Git history and pre-commit hooks | 1. Lightweight and fast <br> 2. Easy to use and set up <br> 3. Open-source and free to use | 1. Lacks advanced dashboards <br> 2. Minimal reporting features <br> 3. Less comprehensive for large, complex projects |
| **AWS Macie**   | 1. Uses machine learning to classify sensitive data <br> 2. Works seamlessly with AWS services (S3, etc.) <br> 3. Detects personally identifiable information (PII) | 1. Tailored for AWS environments <br> 2. Automatic classification of sensitive data <br> 3. Can handle large volumes of data | 1. Limited to AWS services <br> 2. Cost can escalate with usage <br> 3. Not suitable for non-AWS projects |
| **SpectralOps** | 1. Customizable with APIs for more control <br> 2. Scans code and configuration files <br> 3. Supports multiple integrations (Jenkins, GitLab, etc.) | 1. Works well with large projects <br> 2. Good for complex workflows <br> 3. Supports multiple file formats and environments | 1. Hard to set up for small teams <br> 2. Complex configuration <br> 3. Can require expert knowledge for customization |


### Advantages of Credential Scanning

| Advantage            | Description                                                                                          |
|----------------------|------------------------------------------------------------------------------------------------------|
| **Better Security**   | By catching credentials early, you prevent security breaches later on.                               |
| **Fast and Automatic**| The scanning is done automatically, meaning developers don’t need to check manually every time.      |
| **Meet Standards**    | Many industries require businesses to secure data properly, and credential scanning helps with this.  |
| **Avoid Data Leaks**  | By removing sensitive data before code is published, you avoid exposing it to hackers.               |

### Proof of Concept (POC)
![Screenshot from 2024-12-08 12-23-42](https://github.com/user-attachments/assets/09cd825b-cf69-49cf-93e1-b3100d104463)
![Screenshot from 2024-12-08 12-23-52](https://github.com/user-attachments/assets/2a53e3d2-e3b4-4b47-ae8d-9b7824a4da0e)



### Best Practices

| Best Practice           | Description                                                                                      |
|-------------------------|--------------------------------------------------------------------------------------------------|
| **Scan Early**           | Add scanning during development (before code is committed) to catch issues early.                |
| **Scan Regularly**       | Regularly scan the entire repository, as old commits may still contain sensitive data.           |
| **Access Controls**   | Implement strict access controls to limit who can view and modify sensitive information.             |
| **Handle False Positives**| Review flagged data carefully, as scanners can sometimes incorrectly flag harmless information.  |
| **Use Secrets Managers** | Store secrets (keys, passwords) in secure vaults like AWS Secrets Manager or HashiCorp Vault.     |

### Recommendation
Chooses GitLeaks because:

- It’s simple to set up and integrates easily with GitHub Actions.
- It scans the entire Git history, not just recent commits, which helps find secrets buried deep in the code.
- It's lightweight and runs efficiently in CI pipelines, ensuring that sensitive data is caught before reaching production.

#### How GitLeaks works:

- **1. Scan the repository**: Gitleaks looks through the entire Git history, including the current files and past commits.
- **2. Find secrets**: It detects strings or patterns that look like sensitive information (such as "password = 'secret123'" or api_key = 'abcdef').
- **3.Report**: It gives a report listing where the leaks are and what kind of secret it found (e.g., password, API key).




### Conclusion
Credential scanning is an essential practice for maintaining the security and integrity of codebases. By implementing regular scans, Access Controls, Using Secrets Managers, organizations can significantly reduce the risk of exposing sensitive information. GitLeaks offer robust solutions for integrating credential scanning into CI pipelines, ensuring continuous protection against credential leaks.

## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Neelesh kumar | nilesh.rajput.snaatak@mygurukulam.co || GitHub | URL |
|----------|---------|
|  devneelesh921  |  https://github.com/devneelesh921  |




### References 
|links | Description |
|-------| ----------|
|https://github.com/gitleaks/gitleaks| GitLeaks |
|https://www.jit.io/resources/appsec-tools/the-developers-guide-to-using-gitleaks-to-detect-hardcoded-secrets| Cred Scanning |


