# 🚀 Snapchat Clone CI/CD Deployment using Jenkins, Docker & Tomcat

This project demonstrates how to automate the deployment of a Java Maven Web Application (WAR) using **Jenkins CI/CD**, **Docker**, **Apache Tomcat**, and **Docker Hub** on an **AWS EC2 Ubuntu Server**.

---

# 📌 Project Overview

This project automates the complete software deployment lifecycle:

- Source Code Management using GitHub
- Continuous Integration using Jenkins
- Build Automation using Maven
- Containerization using Docker
- Image Storage using Docker Hub
- Deployment using Apache Tomcat inside Docker
- Hosting on AWS EC2

---

# 🛠 Technologies Used

- Java 17
- Maven
- Apache Tomcat 9
- Docker
- Docker Hub
- Jenkins
- Git & GitHub
- AWS EC2 (Ubuntu 24.04/26.04)

---

# 📂 Project Structure

```
.
├── Dockerfile
├── Jenkinsfile
├── pom.xml
├── README.md
├── src
│   └── main
│       └── webapp
│           ├── index.html
│           ├── style.css
│           └── WEB-INF
│               └── web.xml
└── target
    └── snapchat.war
```

---

# ⚙️ Prerequisites

Before running this project, install:

- Java 17
- Maven
- Docker
- Jenkins
- Git

---

# 🚀 CI/CD Workflow

```
Developer
      │
      ▼
GitHub Repository
      │
      ▼
Jenkins Pipeline
      │
      ▼
Maven Build
      │
      ▼
Generate WAR File
      │
      ▼
Docker Build
      │
      ▼
Docker Image
      │
      ▼
Docker Hub Push
      │
      ▼
Docker Run
      │
      ▼
Tomcat Container
      │
      ▼
Application Live
```

---

# 🐳 Docker Workflow

### Build Docker Image

```bash
docker build -t snapchat-cicd-docker .
```

### Run Container

```bash
docker run -d -p 8084:8080 --name snapchat-container meghabb11/snapchat-cicd-docker:latest
```

---

# 🔄 Jenkins Pipeline Stages

- ✅ Checkout Source Code
- ✅ Maven Build
- ✅ Docker Image Build
- ✅ Docker Login
- ✅ Docker Image Tag
- ✅ Docker Push
- ✅ Deploy Docker Container
- ✅ Cleanup Images
- ✅ Docker Logout

---

# 📦 Dockerfile

- Uses Tomcat 9 with JDK 17
- Removes default ROOT application
- Copies generated WAR file
- Deploys as ROOT application

---

# 📸 Application Access

```
http://<EC2-Public-IP>:8084
```

Example:

```
http://13.xx.xxx.xxx:8084
```

---

# 📊 Deployment Flow

```
GitHub
   │
   ▼
 Jenkins
   │
   ▼
 Maven Package
   │
   ▼
Docker Build
   │
   ▼
Docker Hub
   │
   ▼
Docker Container
   │
   ▼
Tomcat
   │
   ▼
Web Application
```

---

# 📖 How to Run

### Clone Repository

```bash
git clone https://github.com/Megha11092018/snapchat_cicd_docker.git
```

### Build Project

```bash
mvn clean package
```

### Build Docker Image

```bash
docker build -t snapchat-cicd-docker .
```

### Run Container

```bash
docker run -d -p 8084:8080 --name snapchat-container snapchat-cicd-docker
```

---

# 🎯 Features

- CI/CD Pipeline using Jenkins
- Dockerized Java WAR Application
- Automated Docker Image Build
- Docker Hub Integration
- One-click Deployment
- AWS EC2 Hosting
- Apache Tomcat Deployment

---

# 👩‍💻 Author

**Megha B Biradar**

GitHub: https://github.com/Megha11092018

---

⭐ If you found this project useful, don't forget to star the repository!
