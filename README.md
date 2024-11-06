# UnityHub - Video Chat Web Application using Django

## Project Overview

**UnityHub** is a web application designed to facilitate real-time video chats, built with Django as the backend framework. It leverages the Agora Real-Time Voice and Video Engagement SDK to deliver high-quality video and voice communication. UnityHub provides users with a smooth and interactive experience, making it an ideal platform for both personal and professional video calls.

### Key Features:
- **Real-Time Video & Voice**: High-quality, low-latency video and voice communication powered by Agora's SDK.
- **User-Friendly Interface**: Intuitive and responsive UI for seamless navigation and usage.
- **Secure & Private**: Ensures user data privacy and secure video sessions.
- **Scalable Architecture**: Built using Django for robust, scalable performance.
- **Cross-Platform**: Accessible on both desktop and mobile devices.
- **Group Video Chat**: Support for multi-user video calls.

### Technologies Used:
- **Backend**: Django (Python)
- **Frontend**: HTML, CSS, JavaScript
- **Real-Time Communication**: Agora Real-Time Voice and Video Engagement SDK
- **Database**: SQLite

This project demonstrates the integration of modern web technologies with real-time communication solutions, offering a flexible and reliable platform for video engagement.


## Working with Virtual Environments on Your Local Machine

1. Ensure `pip` is installed on your device. The latest version can be installed and upgraded by using the command:
    ```bash
    py -m pip install --upgrade pip
    ```

2. Python uses `venv` as the preferred module to create and manage virtual environments. `venv` is included in the Python standard library and does not require any additional installation. You can create a virtual environment in the specific project directory by running the command:
    ```bash
    py -m venv env
    ```
    *(Here, `env` is the name assigned to the virtual environment, and you can use any name you wish.)*

3. Activate the virtual environment:  
   You need to activate the virtual environment. This will put the virtual environment-specific Python and `pip` executables into your shell’s PATH. You can do this by running the command:
    ```bash
    .\env\Scripts\activate
    ```

    If an error occurs, you can resolve it temporarily by running:
    ```bash
    Set-ExecutionPolicy RemoteSigned -Scope Process
    ```

    To remove the error permanently, run:
    ```bash
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
    ```

4. Exit the virtual environment:  
   You can exit the virtual environment by running the command:
    ```bash
    deactivate
    ```

## Installing Django and Creating a Project

1. To install Django, use the command in the terminal:
    ```bash
    pip install django
    ```

   To check the version of Django, run:
    ```bash
    python -m django --version
    ```

2. To create a project in Django, use:
    ```bash
    django-admin startproject demoproject
    ```
    *(Here, `demoproject` is the name of the project, and you can use any name you wish.)*

   To create the project in the current working directory (avoiding subdirectories with the same name), run:
    ```bash
    django-admin startproject demoproject .
    ```

   Use `CTRL + C` to stop the server, and then deactivate the virtual environment.

## Creating an App and Running Your Django Project

1. The `startapp` command option of the `manage.py` script creates a default folder structure for the app of that name. Here’s how to create a `demoapp` in the `demoproject` folder:
    ```bash
    python manage.py startapp demoapp
    ```

2. To run and view your Django app in the browser, execute the following commands in the terminal:
    - To run the server (if there is more than one Django project):
        ```bash
        django-admin runserver
        ```
    - To run the server (if there is only one Django project):
        ```bash
        python manage.py runserver
        ```

    - To compile the migrations:
        ```bash
        python manage.py makemigrations
        ```

    - To migrate the changes in the database:
        ```bash
        python manage.py migrate
        ```

## Create Database Tables

The `startproject` template installs some Django apps by default, such as admin, auth, and sessions. You need to create the necessary database tables for these apps. Run the migrate command to build their respective table structure in the current MySQL database:
```bash
python manage.py migrate
```

## Django Admin
### Superuser:
```bash
Username: admin  
Password: admin123
```

## Agora Video Chat Setup

### 1. Create an Agora Account
- Visit [Agora.io](https://www.agora.io/) and sign up for a free account.
- After logging in, create a new project in the Agora Console.
- Note your **App ID** and **App Certificate** from the project settings. These are essential for authenticating your application with Agora services.

### 2. Download the Agora SDK
- Go to the [Agora SDK Downloads](https://www.agora.io/en/products/rtc/sdk/) page.
- Choose the **Video SDK for Web** and download it.
- Extract the SDK files and add them to your project's static files folder. This will allow you to use the Agora functionalities in your web application.

### 3. Install `agora-token-builder`
- To manage token generation, install the `agora-token-builder` package using:
```bash
pip install agora-token-builder
```

## How to Use This Source Code:
### 1. Clone the Repository
```bash
git clone https://github.com/SumithShetty1/unityhub.git
```

### 2. Install Requirements

To install the necessary dependencies for the project, navigate to the project directory and run the following command:

```bash
cd unityhub
pip install -r requirements.txt
```

### 3. Update Agora Credentials

To use this project, you'll need to update the Agora credentials in `views.py` and `streams.js`.

1. **Create an Account:**
   - Go to [agora.io](https://www.agora.io/) and create an account.
   - Create a new app and copy your **App ID** and **App Certificate**.

2. **Update Files:**
   - In `views.py`, replace the placeholders with your Agora credentials:

   ```python
   def getToken(request):
       appId = "YOUR APP ID"
       appCertificate = "YOUR APP CERTIFICATE"
       ...
    ```

    - In `streams.js`, update the App ID by replacing the placeholder with your actual Agora App ID. Locate the following line:

    ```javascript
    const APP_ID = 'YOUR APP ID';
    ...
    ```

### 4. Start the Server

To start the Django server, navigate to your project directory and run the following command:

```bash
python manage.py runserver
```
