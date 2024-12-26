
# Python CI Check | Unit Testing | POC



| **Author** | **Created on** | **Version** | **Last edited on** | **L0 Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Anjali Dhiman  | 04-12-24      | V1  | 05-12-24           | Khushi Malhotra |



## Table of Contents

- [Introduction](#Introduction)
- [Pre-requisite](#Pre-requisite)
- [Performing Unit Testing](#Performing-Unit-Testing)
- [Conclusion](#Conclusion)
- [Contact](#Contact)
- [Refrence](#Refrence)




## Introduction
 In this Document we are creating the POC of unit testing for the Pyhton based API, to get the errors by performing the unit testing.


## Pre-requisite


## Run Time Dependency

| **Name** | **Version** | **Description** |
|------|---------|-------------|
| **python** | 3.11 | Application is built on this version only |




## Performing Unit Testing
 After cloning the repo to the system we run the below command 

 ```bash
pytest
 ```
This command will start executing unit tests.

![IMG-20241206-WA0016](https://github.com/user-attachments/assets/67050653-5d90-4ad7-80c0-2488eabdbcd8)



 In the above images we can see that this unit test give us the modules error , same as we are facing when we are building our api


 #### Errors we are Facing

| **Error Type**           | Description | **Possible Solutions**  |
|--------------------------|---------------------------|----------------------|
|Modules| Raised when the Python interpreter can't find the module to import|Ensure the module is installed,Ensure the module is in the correct path or location|
|Flask|Raised when Python can't find the flask|Please make sure that all libraries of python is installed properly|
|psycopg2|error occurs when the PostgreSQL server is unreachable, either due to connection issues or incorrect connection parameters.|Ensure that the PostgreSQL server is running and accessible.|

## Report Link
| Link         | Description         |
|--------------|------------------------|
| [Unit Testing](https://github.com/avengers-p11/Documentation/blob/main/Application%20CI%20Design/Python%20CI%20Checks/Unit%20testing/pytest-report.xml)| Report |



## Conclusion
 we can say that Unit testing in Python ensures code correctness, identifies bugs early, improves code reliability, and promotes efficient debugging and maintenance.



 ## Contact

| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |  Anjaliopstree  |  https://github.com/Anjaliopstree  |
 


 ## Refrence
  | Link|Description|
  |:---:|:---:|
  |[Link](https://github.com/MyGurukulam-p11/Documentation/tree/main/OT-Microservices/Application/Attendance-API)|Attendance API|
  |[Link](https://github.com/MyGurukulam-p11/Documentation/blob/main/Application-CI-Design/Python-CI-Checks/Unit-Testing/README.md)|Python Unit testing Doc|
