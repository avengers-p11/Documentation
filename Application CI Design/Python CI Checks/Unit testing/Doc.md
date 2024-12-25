# Documentation of Python Unit Testing.

| **Author** | **Created on** | **Version** | **Last edited on** | **L0 Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Anjali Dhiman  | 04-12-24      | V1  | 05-12-24           | Khushi Malhotra |

## ![image](https://github.com/user-attachments/assets/de480ac4-2a62-417f-a248-c63c8d95bb44)



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
This document focuses on unit testing in Python, providing a comparison of popular tools available in the market, highlighting their features, and offering guidance on selecting and using the best tools effectively.

## Life Cycle of Testing

![image](https://github.com/user-attachments/assets/9e03a4e6-4600-48d6-b81a-41f8abdf3aa1)



## General Workflow
![image](https://github.com/user-attachments/assets/466bf1c9-6f74-44eb-8b8d-5e7e580a72f9)



# Comparison Table of Different Tools Used in Unit Testing of Python

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

## Reference Links

| Links | Description      |
|-----  |--------------------------|
| https://www.geeksforgeeks.org/unit-testing-python-unittest |  Python Unit testing |
| https://www.testbytes.net/blog/python-test-automation-framework | Python Unit testing tools |

