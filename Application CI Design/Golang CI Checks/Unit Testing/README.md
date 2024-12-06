# Golang CI Check | Unit Testing | Document

| Created     |    Version   | Author | Comment | Reviewer | Date |
|:------------------:|:-------------:|:-------------:|:-------------:|:------------------:|:--------:|
| 6-12-2024   | V1   | Raman Tripathi | Internal Review |   | |
|   |    | Raman Tripathi | L0 |  | 
|  |  | Raman Tripathi | L1  |  |
| |  |  Raman Tripathi | L2  |  |

## Table of Contents

- [Introduction](#Introduction)
- [CI for Unit Testing](#CI-for-Unit-Testing)
- [Unit Tests Generally Cover](#Unit-Tests-Generally-Cover)
- [Why CI with Unit Testing is Important](#Why-CI-with-Unit-Testing-is-Important)
- [Life Cycle of Testing](#Life-Cycle-of-Testing)
- [General Workflow](#General-Workflow)
- [Different Tools for CI and Unit Testing in Golang](#Different-Tools-for-CI-and-Unit-Testing-in-Golang)
- [Comparison of CI Tools for Golang](#Comparison-of-CI-Tools-for-Golang)
- [Advantages of CI with Unit Testing](#Advantages-of-CI-with-Unit-Testing)
- [Best Practices for Golang Unit Testing in CI](#Best-Practices-for-Golang-Unit-Testing-in-CI)
- [Recommendations / Conclusion](#Recommendations-/-Conclusion)
- [Contact](#Contact)
- [References](#References)

---

## Introduction

Continuous Integration (CI) is a practice where code changes are automatically built, tested, and integrated into the main branch frequently. This helps catch integration bugs and code quality issues early, reducing development risks.  

In Golang projects, CI checks are essential to ensure code passes unit tests and meets quality standards.  

This document focuses on setting up CI for Golang projects, with a focus on unit testing, comparing tools, and offering best practices for effective testing in the CI pipeline.

---

# CI for Unit Testing

CI for unit testing in Golang is the process of automatically running unit tests every time new code is integrated into the project repository. These tests are designed to verify that individual components of the Golang application work as expected. By automating this process, CI ensures that changes do not break existing functionality and that new features are well-tested.

---

## Unit Tests Generally Cover

| Aspect               | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **Methods and Functions** | Verifies that individual methods or functions perform as expected.         |
| **Input Validation**     | Ensures that inputs are correctly validated and processed.                |
| **Boundary Conditions**  | Tests for edge cases and boundaries to ensure robustness.                 |
| **Error Handling**       | Verifies that the system gracefully handles unexpected conditions.        |

CI tools provide feedback on whether tests pass or fail, along with logs, allowing developers to quickly address issues in the code.

---

# Why CI with Unit Testing is Important

| Benefit                    | Description                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| **Faster Feedback**         | Developers receive immediate feedback on their code's functionality, helping them fix issues early. |
| **Improved Code Quality**   | By running tests continuously, developers are encouraged to write more testable and cleaner code. |
| **Reduced Integration Issues** | Frequent testing helps catch integration problems early, reducing the number of issues in later stages of development. |
| **Reliability**             | Automated tests increase confidence in code stability, especially when refactoring or adding new features. |
| **Efficient Use of Time**   | Automated unit testing in CI pipelines saves time, as developers don’t need to manually run tests after each change. |

---

## Life Cycle of Testing

![unit test life cycle](https://github.com/user-attachments/assets/9abd7f94-33d9-423e-bf1f-49a423078cdf)

---

## General Workflow
 ![Testing stage](https://github.com/user-attachments/assets/f057b075-fd9c-45e0-8048-91869f726f9d)

---

# Different Tools for CI and Unit Testing in Golang

| Tool               | Description                                                                 | Unit Testing Integration                                 | Usage                                                                 |
|--------------------|-----------------------------------------------------------------------------|----------------------------------------------------------|-----------------------------------------------------------------------|
| **Jenkins**        | An open-source automation server that enables developers to build, test, and deploy software. | Integrates with Go testing tools (e.g., `go test`) to run unit tests as part of the build process. | Uses plugins to display test results and integrate with Go test.        |
| **GitLab CI/CD**   | Provides an integrated CI/CD solution with pipelines defined in `.gitlab-ci.yml`. | Built-in support for Go tests with the `go test` command.            | Unit tests are integrated by configuring pipelines to run Go test tasks. |
| **Travis CI**      | A cloud-based CI service that integrates with GitHub repositories for automating build and test processes. | Supports Golang unit testing through `go test` framework.      | Unit testing steps are defined in the `.travis.yml` configuration file. |
| **CircleCI**       | A cloud-based CI tool that automates testing and deployment pipelines.      | Supports Go and other test frameworks like `testify` or `go test`.                | Configurations are defined in the `config.yml` file to run Golang unit tests. |
| **Azure DevOps**   | Provides CI/CD pipeline support for Golang projects with integrated testing options. | Supports Golang unit tests with `go test` tasks.     | Unit tests are included in the pipeline by configuring YAML files to run Go test tasks. |

---

## Comparison of CI Tools for Golang

| Feature                     | Jenkins          | GitLab CI        | Travis CI        | CircleCI         | Azure DevOps     |
|-----------------------------|------------------|------------------|------------------|------------------|------------------|
| **Open-Source**              | Yes              | Yes              | Yes              | Yes              | No               |
| **Cloud/On-Prem Support**    | Both             | Cloud            | Cloud            | Cloud            | Both             |
| **Integration with GitHub**  | Yes              | Yes              | Yes              | Yes              | Yes              |
| **Support for Go Testing**   | Yes              | Yes              | Yes              | Yes              | Yes              |
| **Ease of Setup**            | Moderate         | Easy             | Easy             | Easy             | Moderate         |
| **Customizable Pipelines**   | High             | High             | Moderate         | High             | High             |
| **Free Tier Available**      | Yes              | Yes              | Yes              | Yes              | Yes              |

---

# Advantages of CI with Unit Testing

| Advantage                      | Description                                                                 |
|---------------------------------|-----------------------------------------------------------------------------|
| **Early Detection of Bugs**     | Catch issues right after code integration before they propagate into production. |
| **Consistency**                 | Automated tests ensure consistent execution of test cases across environments. |
| **Speed**                       | CI pipelines automate repetitive tasks like testing, improving overall development speed. |
| **Documentation and Reporting** | Tools like Jenkins and GitLab provide easy-to-read reports, making it easier for developers to debug and fix failing tests. |

---

# Best Practices for Golang Unit Testing in CI

| Best Practice                   | Description                                                                 |
|----------------------------------|-----------------------------------------------------------------------------|
| **Write Clear and Independent Tests** | Each unit test should focus on a single functionality and be independent of others. |
| **Mock External Dependencies**  | Use mocking libraries like `testify` or `gomock` to isolate unit tests from external systems. |
| **Keep Tests Fast**             | Unit tests should run quickly to avoid blocking the CI pipeline.            |
| **Run Tests Locally Before Committing** | Always run tests locally before pushing changes to the CI server.      |
| **Test Coverage**               | Aim for high code coverage but focus on testing meaningful parts of your code rather than covering every line. |
| **Parallel Testing**            | Use parallel testing when possible to reduce test execution time, especially in large projects. |
| **Fail Fast**                   | Configure CI to fail the build immediately when tests fail, enabling quick feedback. |

---

## Recommendations / Conclusion

- **Choose the Right CI Tool**: Select a CI tool that integrates well with your team's workflow, project needs, and scalability.
- **Automate and Integrate Unit Tests**: Ensure unit tests are an integral part of your CI pipeline to maintain code quality and reliability.
- **Focus on Test Quality**: High-quality tests are more important than test quantity. A smaller number of meaningful, well-structured tests are better than having hundreds of trivial tests.

By incorporating CI into your Golang development lifecycle, you ensure that unit testing is continuously applied, leading to more robust and maintainable code.

---

## Contact

For more information, feedback, or assistance, feel free to contact:
| Name         | Email address                       |
|--------------|-------------------------------------|
| Raman Tripahi | raman.tripathi.snaatak@mygurukulam.co  |

---

## References

# CI and Unit Testing Documentation Links

| Tool              | Documentation Link                                                     |
|-------------------|------------------------------------------------------------------------|
| **Jenkins**       | [Jenkins Documentation](https://www.jenkins.io/doc/)                    |
| **GitLab CI/CD**  | [GitLab CI/CD Documentation](https://docs.gitlab.com/ee/ci/)           |
| **Travis CI**     | [Travis CI Documentation](https://docs.travis-ci.com/)                 |
