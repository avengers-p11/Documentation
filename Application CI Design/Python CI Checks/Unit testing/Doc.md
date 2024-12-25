# Documentation of Unit Testing.

| **Author** | **Created on** | **Version** | **Last edited on** | **L0 Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Anjali Dhiman  | 04-12-24      | V1  | 05-12-24           | Khushi Malhotra |

## Table of Contents

- [Introduction](#Introduction)
- [Life Cycle of Testing](#Life-Cycle-of-Testing)
- [General Workflow](#General-Workflow)
- [Different Tools for  Unit Testing in Python](#Different-Tools-for-Unit-Testing-in-Python)
- [Advantages of CI with Unit Testing](#Advantages-of-CI-with-Unit-Testing)
- [ Conclusion](#Conclusion)
- [Contact](#Contact)
- [References](#References)

---

## Introduction
Continuous Integration (CI) is a practice where code changes are automatically built, tested, and integrated into the main branch frequently. This helps catch integration bugs and code quality issues early, reducing development risks.  In Python projects, CI checks are essential to ensure code passes unit tests and meets quality standards.  
This document focuses on setting up CI for Python projects, with a focus on unit testing, comparing tools, and offering best practices for effective testing in the CI pipeline.


## Life Cycle of Testing

![unit test life cycle](https://github.com/user-attachments/assets/9abd7f94-33d9-423e-bf1f-49a423078cdf)

---

## General Workflow
 ![Testing stage](https://github.com/user-attachments/assets/f057b075-fd9c-45e0-8048-91869f726f9d)

---

# Different Tools for Unit Testing in Python

![python tools](https://github.com/user-attachments/assets/d7a114db-67c2-45ad-829f-c49025221730)

## Comparison of Testing Tool

| Feature                     | Lettuce                             | pytest                             | doctest                          | Robot                   |
|-----------------------------|-------------------------------------|------------------------------------|----------------------------------|-----------------------------------|
| **Type of Testing**          | Behavior-Driven Development (BDD)   | Unit testing and general testing  | Testing embedded in docstrings   | Keyword-driven acceptance testing|
| **Syntax**                   | Gherkin (Given-When-Then)           | Python-based, flexible assertions | Python-based in docstrings       | Keyword-based (using natural language) |
| **Focus**                    | Readable specifications (stories)  | Powerful, scalable testing        | Documenting and testing examples | Acceptance testing for systems   |
| **Ease of Use**              | Easy for non-developers to understand | Developer-friendly, more control  | Simple for small scripts, docs   | Easy to use with predefined keywords |
| **Integration**              | Integrates with Python and web frameworks | Integrates with other tools and frameworks | Minimal, works within Python docs | Large ecosystem of libraries and tools |
| **Execution**                | Command-line, can use parallelism   | Command-line, parallel execution, fixtures | Runs with Python interpreter    | Command-line, supports parallel execution |
| **Test Reporting**           | Basic reports and logs              | Rich reports, plugins available   | Limited to Python's standard |Rich HTML reports, logs available |
| **Popularity**               | Moderate                            | Very popular, widely used         | Niche, typically used for simple testing | Moderate, popular for acceptance testing |
| **Community Support**        | Smaller community                   | Large community and ecosystem     | Small, more focused on documentation | Large community and ecosystem    |

---

# Advantages of  Unit Testing

| Advantage                      | Description                                                                 |
|---------------------------------|-----------------------------------------------------------------------------|
| **Early Detection of Bugs**     | Catch issues right after code integration before they propagate into production. |
| **Consistency**                 | Automated tests ensure consistent execution of test cases across environments. |
| **Speed**                       | CI pipelines automate repetitive tasks like testing, improving overall development speed. |
| **Documentation and Reporting** | Tools like Jenkins and GitLab provide easy-to-read reports, making it easier for developers to debug and fix failing tests. |

---
## Contacts

| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |  Anjaliopstree  |  https://github.com/Anjaliopstree  |

## Conclusion

For Python unit testing, **pytest** is ideal for flexibility and scalability, offering a rich set of features for both simple and complex testing scenarios. Its support for fixtures, parameterized tests, and comprehensive assertion methods make it a popular choice among developers. With an active community and extensive plugin ecosystem, **pytest** enables efficient test development and maintenance, making it well-suited for projects of any scale.

---

