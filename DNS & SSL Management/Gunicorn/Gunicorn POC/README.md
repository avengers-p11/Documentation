# POC of Gunicorn 
<img width="371" alt="image" src="https://github.com/user-attachments/assets/7bd9cd20-d3c3-4b01-acf1-637c9c1f3aa5" />


| **Author** | **Created on** | **Version** | **Last edited on** | **L0 Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Anjali Dhiman  | 04-12-24      | V1  | 24-12-24           | Khushi Malhotra |


## Table of Contents

- [Introduction](#introduction)
- [Gunicorn Setup](#scylladb-setup)
- [Contact](#contact)
- [References](#references)
  
## Introduction
This guide provides a step-by-step process to install and set up Gunicorn (Green Unicorn), a Python WSGI HTTP server, for deploying a basic Python web application (e.g., built with Flask) on a Linux system.



## Gunicorn  Setup

# Gunicorn 
Gunicorn (Green Unicorn) is a Python WSGI HTTP server designed for running web applications, particularly those built with frameworks like Django and Flask. It is known for its simplicity, high performance, and support for concurrent handling of multiple requests using worker processes.
## Prerequisites

- A Linux system with internet access.
- Python 3 and pip installed on your machine.
- Basic knowledge of Python and Flask.
- A Python application 
## Gunicorn Installation Dependencies

| Dependency        | Description                                 |
|-------------------|---------------------------------------------|
| Python            | Required to run Gunicorn (Python 3.6+).     |
| pip               | Python package installer.                   |
| python3-dev       | Development headers for Python (Linux).     |

## Steps

### 1. Install Python and pip

First, ensure that Python and pip (Python’s package installer) are installed on your system.



- If Python is not installed, you can install it using the package manager (on Ubuntu/Debian):

    ```bash
    sudo apt update
    sudo apt install python3 python3-pip
    ```
<img width="564" alt="image" src="https://github.com/user-attachments/assets/379caa72-3623-4230-9b74-4cf9c7c3b9f3" />

- Check pip version:

    ```bash
    pip3 --version
    ```
<img width="562" alt="image" src="https://github.com/user-attachments/assets/da8ba389-2daa-4574-850e-f4deb3a43fd2" />


### 2. Install Gunicorn

Once Python and pip are ready, you can install Gunicorn using pip:

```bash
pip3 install gunicorn
```
<img width="566" alt="image" src="https://github.com/user-attachments/assets/8ef72c23-f011-4a10-95d4-d7803955d50b" />

### 3. Create a Python Web Application (Example with Flask)

If you don’t already have a web application, here's an example using Flask.

- Install Flask:

    ```bash
    pip3 install flask
    ```
<img width="568" alt="image" src="https://github.com/user-attachments/assets/16906cd6-aa2e-495d-b163-191db1e5c2aa" />

- Create a file named `app.py` with the following content:

    ```python
    from flask import Flask

    app = Flask(__name__)

    @app.route('/')
    def hello_world():
        return 'Hello, World!'

    if __name__ == '__main__':
        app.run()
    ```

### 4. Test the Flask App Locally

Before running Gunicorn, you can test your Flask app locally with the built-in Flask development server:

```bash
python3 app.py
```

This will start the Flask development server at [http://127.0.0.1:5000/](http://127.0.0.1:5000/). Open that URL in your browser to ensure the application works.

### 5. Run the Flask App with Gunicorn

To run your Flask app using Gunicorn, use the following command in the terminal from the same directory as `app.py`:

```bash
gunicorn --workers 3 app:app
```

- `--workers 3`: Specifies the number of worker processes Gunicorn should use (adjust based on your machine’s CPU count).
- `app:app`: The format is `module:application`. Here, `app` is the filename (`app.py`), and the second `app` is the Flask application object.

You should see output similar to this:

```bash
[2024-11-14 12:00:00] [INFO] Starting gunicorn 20.1.0
[2024-11-14 12:00:00] [INFO] Listening at: http://127.0.0.1:8000 (1234)
[2024-11-14 12:00:00] [INFO] Using worker: sync
[2024-11-14 12:00:00] [INFO] Booting worker with pid: 1235
```
<img width="566" alt="image" src="https://github.com/user-attachments/assets/e81923f2-ed11-4b88-a1ea-13eb2f4af130" />

Your application should now be running at [http://127.0.0.1:8000/](http://127.0.0.1:8000/).

### 6. Test Gunicorn Server

Visit [http://127.0.0.1:8000/](http://127.0.0.1:8000/) in your browser or use `curl` to check:

```bash
curl http://127.0.0.1:8000/
```
<img width="565" alt="image" src="https://github.com/user-attachments/assets/c9ff8ecd-de49-446c-bfcf-437ca693ca10" />

You should get the response: `Hello, World!`.

## Conclusion 

Gunicorn is a high-performance WSGI HTTP server for Python web applications, known for its simplicity and speed. It effectively handles multiple requests concurrently by forking worker processes, making it a popular choice for production environments. Its compatibility with various Python web frameworks and ease of use make it a reliable choice for deploying web applications.

## Contact

| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
| Anjali Dhiman | anjali.dhiman.snaatak@mygurukulam.co |  Anjaliopstree  |  https://github.com/Anjaliopstree  |

---

## References

- [Gunicorn Documentation](https://gunicorn.org/)
- [Flask Documentation](https://flask.palletsprojects.com/)






