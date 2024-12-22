# Generic CI Operation: Credential Scanning

| **Author** | **Created on** | **Last updated by** | **Last edited on** | **Reviwer L0** |**Reviwer L1** |**Reviwer L2** |
|------------|----------------|----------------------|---------------------|---------------|---------------|---------------|
| Neelesh kumar      | 29-11-24      | Neelesh  Kumar             | 8-12-24           | Shikha tripathi | | |     

### Table of Contents
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



### Comparison of Credential Scanning Tools

| Tool         | Features                                                                 | Strengths                                                            | Limitations                                                     |
|--------------|--------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------------------------------------------------|
| **GitGuardian** | 1. Real-time monitoring and alerts <br> 2. Integration with GitHub, GitLab <br> 3. Detects hardcoded secrets and sensitive data | 1. Catches issues immediately <br> 2. Easy to integrate into CI/CD <br> 3. Provides detailed alerts and reports | 1. Expensive for larger teams <br> 2. Limited free tier for small teams <br> 3. Can be overwhelming with too many alerts |
| **TruffleHog**  | 1. Scans for high-entropy strings (API keys, secrets) <br> 2. Regex scanning <br> 3. Supports a wide variety of data sources | 1. Works with many data types <br> 2. Flexible scanning methods <br> 3. Good for scanning past commit history | 1. Can produce false positives <br> 2. Complex setup for fine-tuning <br> 3. Manual effort required to interpret results |
| **Gitleaks**    | 1. Simple command-line interface (CLI) <br> 2. CI/CD pipeline integration <br> 3. Scans Git history and pre-commit hooks | 1. Lightweight and fast <br> 2. Easy to use and set up <br> 3. Open-source and free to use | 1. Lacks advanced dashboards <br> 2. Minimal reporting features <br> 3. Less comprehensive for large, complex projects |
| **AWS Macie**   | 1. Uses machine learning to classify sensitive data <br> 2. Works seamlessly with AWS services (S3, etc.) <br> 3. Detects personally identifiable information (PII) | 1. Tailored for AWS environments <br> 2. Automatic classification of sensitive data <br> 3. Can handle large volumes of data | 1. Limited to AWS services <br> 2. Cost can escalate with usage <br> 3. Not suitable for non-AWS projects |


### Advantages of Credential Scanning

| Advantage            | Description                                                                                          |
|----------------------|------------------------------------------------------------------------------------------------------|
| **Better Security**   | By catching credentials early, you prevent security breaches later on.                               |
| **Fast and Automatic**| The scanning is done automatically, meaning developers don’t need to check manually every time.      |
| **Meet Standards**    | Many industries require businesses to secure data properly, and credential scanning helps with this.  |
| **Avoid Data Leaks**  | By removing sensitive data before code is published, you avoid exposing it to hackers.               |

### Proof of Concept (POC)
![Screenshot from 2024-12-22 16-51-00](https://github.com/user-attachments/assets/a406f9f6-1379-4ab0-92d9-667788071874)
![Screenshot from 2024-12-22 16-51-52](https://github.com/user-attachments/assets/700f960e-8279-42da-b70f-ccfee6062398)



### Best Practices

| Best Practice           | Description                                                                                      |
|-------------------------|--------------------------------------------------------------------------------------------------|
| **Scan Early**           | Add scanning during development (before code is committed) to catch issues early.                |
| **Scan Regularly**       | Regularly scan the entire repository, as old commits may still contain sensitive data.           |
| **Access Controls**   | Implement strict access controls to limit who can view and modify sensitive information.             |
| **Handle False Positives**| Review flagged data carefully, as scanners can sometimes incorrectly flag harmless information.  |
| **Use Secrets Managers** | Store secrets (keys, passwords) in secure vaults like AWS Secrets Manager or HashiCorp Vault.     |

### Recommendation
## Why Choose GitLeaks?

| Feature                                     | Description                                                                                   |
|---------------------------------------------|-----------------------------------------------------------------------------------------------|
| **Simple Setup**                            | GitLeaks is easy to configure and integrates seamlessly with GitHub Actions for CI workflows. |
| **Comprehensive Scanning**                  | It scans the entire Git history, not just recent commits, ensuring even deeply buried secrets are identified. |
| **Lightweight and Efficient**               | GitLeaks is optimized for CI pipelines, catching sensitive data without adding significant overhead. |


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


