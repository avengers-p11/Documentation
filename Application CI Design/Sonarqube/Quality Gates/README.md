# SonarQube Quality Gates

  | Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Raman Tripathi | 25-11-24 | version 1 | Raman Tripathi | 25-11-24 |

## Table of Contents

- [What is SonarQube](#what-is-sonarqube)
- [What are Quality Gates in SonarQube](#what-are-quality-gates-in-sonarqube)
- [Benefits of SonarQube Quality Gates](#benefits-of-sonarqube-quality-gates)
- [Types of quality gates in SonarQube](#types-of-quality-gates-in-sonarqube)
- [SonarQube Quality Gate Implementation](#SonarQube-Quality-Gate-Implementation)
- [Conclusion](#Conclusion)
- [Contact Information](#contact-information)
- [Reference Links](#reference-links)

## What is SonarQube

SonarQube is an open-source platform developed by SonarSource for continuous inspection of code quality. It performs automatic reviews using static code analysis to detect bugs, code smells, and security vulnerabilities across multiple programming languages. By providing comprehensive reports and visualizations.

## What are Quality Gates in SonarQube

SonarQube quality gates are predefined sets of conditions used to assess the quality of software code during its development lifecycle. These conditions typically include metrics such as code coverage, code duplications, coding standards compliance, and security vulnerabilities. Quality gates evaluate these metrics against predetermined thresholds. If the code meets these standards, the gate passes; if not, it fails. 

## Benefits of SonarQube Quality Gates

| Benefit                 | Description                                                                                   |
|-------------------------|-----------------------------------------------------------------------------------------------|
| Early Issue Detection   | Catch code quality issues early in development, offering prompt feedback.                      |
| Consistency             | Ensure consistent code quality across projects and teams.                                      |
| Automation              | Automate code evaluation against metrics like coverage and vulnerabilities, saving time.       |
| Best Practices          | Encourage adherence to coding standards, improving overall code quality.                       |
| Integration             | Seamlessly integrate with CI/CD pipelines for continuous monitoring and improvement.           |
| Decision Support        | Provide insights for project managers to assess code readiness, reducing deployment risks.     |


## Types of quality gates in SonarQube

- ### Default Quality Gate

    SonarQube's default quality gate, known as "Sonar way," is a set of predefined conditions designed to ensure code quality and maintainability. It typically includes criteria such as no new critical issues, a minimum percentage of code coverage by unit tests on new code, and limits on code duplication. Additionally, it enforces high ratings for maintainability, reliability, and security on new code.



| Metric                   | Condition                          | Default Value                                |
|--------------------------|------------------------------------|----------------------------------------------|
| **Code Coverage**        | Code Coverage on New Code          | Greater than 80%                             |
| **Duplicated Lines**     | Duplicated Lines on New Code       | Limited amount                               |
| **Reliability Rating**   | Reliability Rating on New Code     | no new blocker or critical issues        |
| **Security Rating**      | Security Rating or Hotspot on New Code | no new blocker or critical vulnerabilities |
| **Maintainability Rating** | Maintainability Rating on New Code | technical debt ratio <= 5%               |

 - ### Custom Quality Gate

    In SonarQube, you can create custom quality gates to tailor code quality checks according to your project's specific requirements. custom quality gates let you adjust metrics like code coverage, duplication and maintainability according to your project's needs.

## SonarQube Quality Gate Implementation

### 1. Login to SonarQube
- Open your SonarQube instance (e.g., `http://localhost:9000`).
- Login using your credentials.

<img width="605" alt="image" src="https://github.com/user-attachments/assets/bf94527d-89d8-40ad-8c30-0282b4fa9c5f" />


### 2. Go to Quality Gates
- Click on **Quality Gates** in the top menu.

<img width="608" alt="image" src="https://github.com/user-attachments/assets/41885da3-708a-47d7-ae0a-6b61c8358770" />


### 3. Create or Edit a Quality Gate
- If you want to modify an existing Quality Gate (like **SonarWay**), click on it. Otherwise, click **Create** to create a new one.

<img width="332" alt="image" src="https://github.com/user-attachments/assets/0cb90da2-9d13-46c6-897f-ea92aa5a7519" />

- Give the gate a meaningful name if creating a new one.

<img width="356" alt="image" src="https://github.com/user-attachments/assets/1c38a1e7-7f9e-404e-8441-3af5fc034ef3" />

### 4. Add Conditions for Failing Quality Gate

#### Code Coverage:
- **Condition**: If **Code Coverage** is less than **80%**, the project should fail.
  
  **Add Condition**:
  - **Metric**: `Coverage`
  - **Operator**: `is less than`
  - **Value**: `80%`
  - **Status**: `Error` (This will fail the project if coverage is below 80%).

<img width="594" alt="image" src="https://github.com/user-attachments/assets/b0530c5f-05ee-41b9-9458-f2f410c6415e" />

### 5. Apply Quality Gate to Your Project
- Once you have added the conditions, save the quality gate.
- Go to Project Administration > Quality Gate.
- From the dropdown, select the quality gate you just created or updated.
- Save the settings.

### 6. Test the Quality Gate
- Run the SonarQube analysis for your project to check if the quality gate fails based on these conditions:
```
  mvn clean install sonar:sonar
```
- After the analysis, go to the SonarQube dashboard for your project.
- Check the Quality Gate status:
  - If any condition (e.g., Code Coverage < 80%, Reliability Rating = B, etc.) is not met, the project will show as Failed.

<img width="599" alt="image" src="https://github.com/user-attachments/assets/a575e851-ddbf-4575-a61c-74761e65675f" />

### Conclusion

SonarQube's quality gates help maintain high code standards by checking metrics like code coverage, security, and maintainability. The default "Sonar way" gate provides a solid foundation, while custom gates allow for flexibility. Quality gates detect issues early, ensure consistency, and integrate smoothly into CI/CD pipelines, making them essential for modern software development.

---

## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Raman Tripathi | raman.tripathi.snaatak@mygurukulam.co |

| GitHub | URL |
|----------|---------|
|  Raman-tripathi07  |  https://github.com/Raman-tripathi07 |

## References

1. [SonarQube Official Documentation - Quality Gates](https://docs.sonarqube.org/latest/user-guide/quality-gates/)  
2. [Best Practices for Managing Code Quality](https://www.sonarsource.com/)  
3. [Continuous Integration and Quality Gates](https://martinfowler.com/)  
4. [SonarQube Community Forum](https://community.sonarsource.com/)  

