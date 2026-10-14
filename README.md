# Jenkins Node.js Web Application

## 💡 Introduction

This project is a simple web application built with **Node.js** and **Express.js**. It starts a web server on port **3000** and displays a text message when a user opens the home page.

The message mentions a webhook and the 18 May DevOps batch. The project is intended for practicing Node.js application deployment and Jenkins-based CI/CD workflows.

## 🎯 Objectives

- Create a web server using Node.js.
- Use Express.js to handle HTTP requests.
- Display a response on the home page.
- Configure application dependencies using `package.json`.
- Practice Jenkins integration and webhook-triggered automation.

## 🏗️ Architecture
The following diagram illustrates how the application works.
<img width="1672" height="941" alt="architecture-diagram" src="https://github.com/user-attachments/assets/7bb63a48-56c4-4063-a90c-a2e6b38f0612" />
User/Browser → HTTP Request → AWS EC2 (Linux) → Nginx → PHP-FPM (submit.php) → MariaDB (FCT database, users table) → Success Page with submitted data


### Architecture Components

| Component | Role |
|-----------|------|
| **Frontend – Web Browser** | Sends requests and displays the response |
| **Backend – Node.js** | Runs the JavaScript application |
| **Web Framework – Express.js** | Handles HTTP requests and responses |
| **Configuration – package.json** | Defines project info, dependencies and the start command |
| **CI/CD – Jenkins and Webhook** | Can trigger an automated pipeline when configured |

> **Note:** Jenkins and webhook automation are optional deployment components. They are not configured by the application code files alone.

## 📥 Input

The application receives an HTTP GET request from the user's browser.

| Input | Description |
|-------|-------------|
| URL | `http://localhost:3000/` |
| HTTP Method | `GET` |
| Port | `3000` |
| Route | `/` |
| Request Body | Not required |

### Input Process

1. The user opens a web browser.
2. The user accesses `http://localhost:3000/`.
3. The browser sends an HTTP GET request.
4. Express.js receives the request at the `/` route.
5. The application processes the request and prepares a text response.

## 📤 Output

When the user opens the home page, the application displays a text message that mentions the webhook and the 18 May DevOps batch.
<img width="1920" height="1080" alt="Screenshot (6)" src="https://github.com/user-attachments/assets/f3258532-2ca2-417b-939a-31888b493a0b" />


### Output Process

1. Express.js matches the incoming request to the `/` route.
2. The `res.send()` method sends the configured text response.
3. The browser displays the message.
4. The terminal displays the server startup message:

```
App listening at http://localhost:3000
```

## 🚀 Background – PM2

**PM2 (Process Manager 2)** is a process manager commonly used to run Node.js applications in the background.

### Key Features

- Runs Node.js applications as background processes.
- Automatically restarts applications when they crash.
- Provides application logs.
- Supports process monitoring.
- Can configure applications to start automatically after a server reboot.

## 🛠️ Deployment Guide

### 1. Launch an EC2 instance on AWS

Use a Linux AMI (e.g. Amazon Linux) and allow inbound traffic on port **3000** (and SSH on port 22) in the security group.

### 2. Push the code to GitHub

Commit `app.js` and `package.json` to a GitHub repository.

### 3. Install the required packages

```bash
sudo yum install node git -y
```

### 4. Clone the repository from GitHub

```bash
sudo git clone <url>
```

### 5. Install dependencies

```bash
sudo yum install npm
sudo npm install
```

### 6. Start the website

```bash
node app.js
```

### 7. Start in the background (optional, with PM2)

```bash
sudo npm install -g pm2
sudo pm2 start app.js
```

> **Note:** PM2 is not included in the provided `package.json`. Use these commands only if you choose to run the application with PM2.

## ✅ Conclusion

This project demonstrates the basic working of a web application using Node.js and Express.js. It gives practical experience with HTTP requests, routing, server responses, dependency management and application startup.

It can also serve as a starting point for learning Jenkins CI/CD pipelines, webhook integration and automated application deployment.

## 🧰 Technologies Used

- **Runtime:** Node.js
- **Framework:** Express.js
- **Language:** JavaScript
- **Package Management:** npm
- **Application Port:** 3000
- **Optional Process Manager:** PM2
- **Optional CI/CD Tool:** Jenkins

## 👤 Author

**Shantilal Samrut**
