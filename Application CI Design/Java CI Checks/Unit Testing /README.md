
#    **Unit Testing**

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer L0**  | **Reviewer L1**   | **Reviewer L2**   |
|-----------------------|----------------|-------------|---------------------------|---------------------|------------------|-------------------|----------------|
| Mohit Saini      |   26-11-24       | v1 | Mohit Saini          |     26-11-24            |    |      |     |

![image](https://github.com/user-attachments/assets/297dbba6-a64b-4c3f-a76f-3efc3c194a79)


**Table of Contents**

1. [**Introduction**](#introduction)
2. [**What**](#what-is-unit-testing)
3. [**Why**](#why)
4. [**Different Tools**](#different-tools)
5. [**Conclusion**](#conclusion)
6. [**Contact Information**](#contact-information)
7. [**References**](#references)



# Introduction
Unit testing is like checking each piece to make sure it fits correctly and works as it should. By testing each piece individually, we can catch any mistakes early on and build a stronger, more stable castle. fixing errors in small parts of our code, so the whole program works correctly.

# What is Unit Testing

Unit testing is a way to test small pieces of code to make sure they work correctly. It's like testing each brick in a wall to make sure it's strong and fits properly.

# Why

| **Reasons**               | **Description**                                                                                      |
|---------------------------|------------------------------------------------------------------------------------------------------|
| **Early Bug Detection**    | It helps find and fix errors early in the development process, before they become bigger problems.    |
| **Improved Code Quality**  | It encourages writing clean, well-structured, and maintainable code.                                 |
| **Increased Confidence**   | By testing small parts of your code, you can be more confident that your software will work as expected. |
| **Facilitates Refactoring**| It allows you to make changes to your code without fear of breaking things, as unit tests can quickly identify any unintended consequences. |
| **Documentation**          | Unit tests serve as living documentation, showing how code is intended to be used.                   |


# Different Tools
The list of several relevant testing frameworks for Java is mentioned below

![image](https://github.com/user-attachments/assets/ed78bd7c-e10e-4a84-98bf-2f616b3552b7)



| Tool | What It Does | Key Features | Pros | Cons |
|---|---|---|---|---|
| JUnit | Used for testing small parts of Java programs. | Simple test annotations like @Test, @Before. Works well with IDEs like IntelliJ and Eclipse. | Easy to learn and use. Lots of community help available. | Can't run tests in parallel. Not great for very complex test setups. |
| TestNG | A testing tool for all types of tests (unit, integration, etc.). | Extra features like @BeforeSuite, @DataProvider. Runs tests in parallel. Test configuration using XML. | Great for managing big test suites. Runs tests faster with parallel execution. | Harder to learn than JUnit. XML setup can be tricky. |
| Mockito | Creates fake objects to test code. | Makes fake objects to replace real ones. Checks if fake objects are used correctly. Works with JUnit and TestNG. | Helps test without needing actual dependencies. Easy to use with clear syntax. | Doesn't support static methods without extra tools. Overuse can create bad test setups. |
| Selenium | Automates browsers to test websites. | Works with Chrome, Firefox, Safari, and more. Can be used with JUnit and TestNG. | Tests work across browsers. Supports many languages like Java, Python. | Tests can be slow. Needs extra tools for advanced features. |
| Spring Test | Tests apps built with Spring Framework. | Helps with integration testing. Supports Spring-specific features like @ContextConfiguration. | Perfect for testing Spring apps. Makes testing dependencies easier. | Only useful for Spring projects. Requires Spring knowledge. |
| Spock | Tests Java and Groovy programs. | Uses Groovy for easy-to-read tests. Built-in mocking and data-driven tests. | Simple and clear test writing. Great for testing with lots of data. | Needs knowledge of Groovy language. May not suit non-BDD projects. |
| Arquillian | Tests Java EE apps in real environments. | Runs tests inside containers like WildFly, JBoss. Handles test deployment. | Tests apps in real conditions. Works well with Java EE. | Setup can be complex. Slower because it uses real environments. |

# Conclusion

The goal of unit testing is to make sure that any new functionality does not break the existing functionality. It also helps identify any issues or bugs earlier in the development process and helps ensure that code meets quality standards set by the organisation.

#  Contact Information


| **Name**    | **Email address**         |
|-------------|---------------------------|
| Mohit Saini | mohit.saini.snaatak@mygurukulam.co |


# References

| **Link** | **Description** |
|------------------------------------------------------|------------------|
|https://www.geeksforgeeks.org/7-best-testing-frameworks-for-java-developers/| Unit Testing |
| https://www.freecodecamp.org/news/java-unit-testing/| Unit Testing tool |

