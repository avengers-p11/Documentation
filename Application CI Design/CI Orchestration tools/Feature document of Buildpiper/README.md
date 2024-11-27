# BuildPiper Documentation

## Introduction
BuildPiper is an open-source, self-hosted, and scalable CI/CD platform designed to simplify the DevOps process by streamlining code delivery. It is tailored to support cloud-native environments and large-scale software development, providing an easy way to manage builds and deployments across different environments.

This documentation provides an overview of BuildPiper, its features, advantages and disadvantages, reasons for not using it in our OT Microservices project, and a conclusion on its suitability for our team.

---

## Why BuildPiper
BuildPiper is designed to address the complexities of managing CI/CD pipelines in enterprise-level applications. It provides flexibility for scaling pipelines, automating tasks, and managing infrastructure-as-code. By supporting both cloud and on-premise configurations, BuildPiper offers a robust solution for teams looking for a customizable CI/CD tool that integrates well with a variety of development and deployment environments.

---

## Features of BuildPiper

| **Feature**                  | **Description**                                                                                                     |
|------------------------------|---------------------------------------------------------------------------------------------------------------------|
| **Multi-cloud Integration**   | Seamlessly integrates with cloud services like AWS, GCP, Azure, and private clouds for deployment automation.        |
| **Pipeline as Code**          | Allows users to define CI/CD pipelines through code for better version control and automation.                       |
| **Scalable**                  | Built to scale with the growth of your team and application, from small projects to enterprise-level systems.         |
| **Customizable Dashboards**   | Provides customizable dashboards to visualize pipeline execution, statuses, and metrics in real-time.                |
| **Flexible Plugins**          | Supports a wide range of plugins for integration with tools like Docker, Kubernetes, Terraform, and Helm.             |
| **Containerized Builds**      | Runs CI/CD jobs inside containers, allowing for better isolation and consistency across builds.                       |
| **Environment Management**    | Manages different environments and deployment stages, making it easy to handle staging, testing, and production.      |

---

## Advantages and Disadvantages of Using BuildPiper

### Advantages

| **Advantage**                         | **Description**                                                                                                      |
|---------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| **Customizable Pipelines**            | Offers flexibility to define custom workflows for various use cases and environments.                                 |
| **Multi-cloud and Hybrid Support**    | Supports integration with multiple cloud providers and hybrid environments.                                          |
| **Scalability**                       | Ideal for growing teams, offering scalable resources and managing large pipelines efficiently.                        |
| **Open-source**                       | Completely open-source, which means no license fees and full control over configurations and features.                |
| **Container Support**                 | Native support for Docker and Kubernetes ensures seamless containerized builds and deployments.                       |

### Disadvantages

| **Disadvantage**                      | **Description**                                                                                                      |
|---------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| **Steep Learning Curve**              | Requires time and effort to understand the platform and configure pipelines effectively, especially for new users.     |
| **Self-hosting Requirements**         | Requires infrastructure for self-hosting, which could be a barrier for teams with limited resources.                   |
| **Complex Setup**                     | The initial setup and configuration may be complex for teams unfamiliar with BuildPiper.                              |
| **Limited Documentation**             | Some features may have limited or less detailed documentation compared to other mainstream CI/CD tools.               |

---

## Why We Are Not Using BuildPiper in Our OT Microservice

We decided not to use BuildPiper in our OT Microservices project for the following reasons:

| **Reason**                            | **Description**                                                                                                      |
|---------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| **Existing Tool Preference**          | We are already using GitHub for version control and CI/CD, which provides sufficient features for our needs.         |
| **Familiarity and Expertise**         | Our team has existing expertise with GitHub Actions, and switching to BuildPiper would require significant retraining. |
| **Infrastructure Constraints**        | BuildPiper requires self-hosting, which would add additional infrastructure maintenance costs and effort.              |
| **Cost and Resource Overhead**        | While BuildPiper is open-source, it would require additional resources to host and scale, which is not ideal for our current setup. |
| **Feature Overlap**                   | GitHub Actions already provides the necessary CI/CD capabilities without the complexity of managing an additional tool. |

---

## Conclusion

While BuildPiper offers a powerful set of features for CI/CD automation, including multi-cloud integration, scalable pipelines, and containerized builds, it does not align with the current infrastructure and expertise of our team. Given that we are already using GitHub for version control and CI/CD workflows, adopting BuildPiper would introduce unnecessary complexity, resource overhead, and a steep learning curve. Therefore, GitHub Actions remains the most suitable choice for our OT Microservices project.

---

## Contacts

| **Name**            | **Email Address**                                           |
|---------------------|-------------------------------------------------------------|
| Anjali Dhiman       | anjali.dhiman.snaatak@mygurukulam.co                        |
| **GitHub**          | [Anjaliopstree GitHub](https://github.com/Anjaliopstree)     |

---

## References

| **Reference Source**              | **Description**                                                        | **URL**                                      |
|-----------------------------------|------------------------------------------------------------------------|----------------------------------------------|
| BuildPiper Official Website      | Official site for BuildPiper documentation and details.               | [BuildPiper](https://buildpiper.io)          |
| GitHub Actions Documentation      | GitHub’s official documentation for CI/CD using GitHub Actions.       | [GitHub Actions](https://docs.github.com/en/actions) |

