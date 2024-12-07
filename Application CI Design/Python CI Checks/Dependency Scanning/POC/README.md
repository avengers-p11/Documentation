# Dependency Scanning POC


| **Author** | **Created on** | **Version** | **Last edited on** | **L0 Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Anjali Dhiman  | 04-12-24      | V1  | 06-12-24           | Khushi Malhotra |


## Table of Contents
1. [Introduction](#1-introduction) 
2. [POC](#2-poc)
3. [Contact](#3-contact)
4. [References](#4-references)

## 1. Introduction
**What is Dependency Scanning in Python CI?**

Dependency scanning involves evaluating the libraries and packages your Python project depends on to identify outdated versions, known vulnerabilities, or misconfigurations. In CI, this scanning process is automated, ensuring your code remains secure and functional after every change.

Dependency scanning checks for:
- **Outdated packages**: Ensures dependencies are up-to-date.
- **Security vulnerabilities**: Identifies known security issues.
- **License compliance**: Verifies that dependencies meet legal requirements.

## 2. POC 


## Step 1: Clone or Access the API Project

If the API repository is hosted on a platform like GitHub, GitLab, or Bitbucket, you can clone it using the following command:

```bash
git clone https://github.com/OT-MICROSERVICES/attendance-api.git
cd repository-name
```

## Step 2: Install Python and pip (if not installed)

Ensure that Python 3 and pip (Python package manager) are installed on your system:

Check Python and pip versions:

```bash
python3 --version
pip3 --version
```

If Python or pip are not installed, you can install them by running the following commands:

```bash
sudo apt update
sudo apt install python3 python3-pip
```

## Step 3: Set Up a Virtual Environment (Recommended)

It's a good practice to isolate your dependencies using a virtual environment.


```bash
sudo apt install python3-venv
```

Create a virtual environment in the project folder:

```bash
python3 -m venv venv
```

Activate the virtual environment:

```bash
source venv/bin/activate
```

Once the environment is activated, your terminal prompt should change to indicate that you are inside the virtual environment.

## Step 4: Install Project Dependencies

If the project uses `requirements.txt`, you can install all the dependencies listed in that file:

Install dependencies from `requirements.txt`:

```bash
pip install -r requirements.txt
```

## Step 5 : if there is no requirement.txt file you can create a requirement.txt file by following these steps
**Generate `requirements.txt` Using `pipreqs`**

If you need to automatically generate a `requirements.txt` file based on the imports in your project, you can use the `pipreqs` tool.

**Step 1: Install `pipreqs`**

To install `pipreqs`, run the following command:

```bash
pip install pipreqs
```




 **Step 2: Generate the `requirements.txt` File**

To generate the `requirements.txt` file, run the following command:

```bash
pipreqs . --force
```

This command will scan the project directory for any external dependencies that are imported in your code and automatically generate a `requirements.txt` file in the current directory.

---


## Step 6: Install Dependency Scanning Tools

To ensure the security of your project, it is recommended to install dependency scanning tools such as `safety`. You can install it using:

```bash
pip install safety
```

After installing `safety`, you can run a security scan to identify any vulnerabilities in your project dependencies:

```bash
safety check
```


After running Safety check i got a vulenerability that my pip version is not updated so we can upgrade the pip and run safety scan again and we got these results .



It states that there is no vulenrabilities reported .This ensure that your Python project dependencies are up-to-date, secure, and compatible.


---
## Step 7 :  Or we can automate this by creating a script also


**1. Create the `dependency_scan.sh` Script**

Create a new shell script file called `dependency_scan.sh` by running the following command:

```bash
nano dependency_scan.sh
```

 **2. Add the Following Content to the Script**
Add the following lines to the script to automate the check for dependencies, outdated packages, and vulnerabilities:

```bash
#!/bin/bash



echo "Checking for security vulnerabilities using safety..."
safety check


```

 **3. Make the Script Executable**

Make the script executable by running the following command:

```bash
chmod +x dependency_scan.sh
```

**4. Run the Script**

To run the script and perform the checks, use the following command:

```bash
./dependency_scan.sh
```

This will generate a `requirements.txt` file, check installed dependencies, identify outdated packages, and scan for security vulnerabilities and broken dependencies.

**Step 5: Resolve Issues**

If the script identifies any outdated dependencies, you can update them using the following command:

```bash
pip install --upgrade <package_name>
```

If any security vulnerabilities are found, update the affected packages or follow the recommendations provided by the tools.

---




## 9. Contacts


## Contacts

| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |  Anjaliopstree  |  https://github.com/Anjaliopstree  |

## 10. References

1. **GitHub Dependabot Documentation**: [GitHub Docs](https://docs.github.com/en/github/administering-a-repository/keeping-your-dependencies-updated-automatically)
2. **Safety Tool GitHub Repository**: [Safety on GitHub](https://github.com/pyupio/safety)
3. **SonarQube Python Plugin Documentation**: [SonarQube Docs](https://docs.sonarqube.org/latest/analysis/languages/python/)
4. **Bandit Documentation**: [Bandit Docs](https://bandit.readthedocs.io/en/latest/)
