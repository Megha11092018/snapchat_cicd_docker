# 🚀 Myntra Fashion Store App Clone CI/CD Deployment using Jenkins, Docker & Tomcat

This project demonstrates a complete **CI/CD pipeline** for deploying a Java Maven Web Application (WAR) using **Jenkins**, **Docker**, **Apache Tomcat**, **Docker Hub**, and **AWS EC2 (Ubuntu)**.

The pipeline automatically builds the application, creates a Docker image, pushes it to Docker Hub, and deploys the application inside a Tomcat container.

---

# 📌 Project Overview

This project automates the software deployment lifecycle:

- Source Code Management using GitHub
- Continuous Integration using Jenkins
- Build Automation using Maven
- WAR Packaging
- Docker Image Creation
- Docker Hub Image Push
- Automated Container Deployment
- Apache Tomcat Hosting
- AWS EC2 Deployment

---

# 🛠 Technologies Used

| Technology | Version |
|------------|---------|
| Java | 17 |
| Maven | Latest |
| Apache Tomcat | 9 |
| Docker | Latest |
| Docker Hub | Cloud Registry |
| Jenkins | Latest LTS |
| Git & GitHub | Version Control |
| AWS EC2 | Ubuntu 24.04 / 26.04 |

---

# 📂 Project Structure

```
snapchat_cicd_docker/
│
├── Dockerfile
├── Jenkinsfile
├── pom.xml
├── README.md
├── src
│   └── main
│       └── webapp
│           ├── index.html
|           |-- style.css
│           ├── images/
│           └── WEB-INF
│               └── web.xml
└── target
    └── snapchat.war
```

---

# ⚙️ Project Setup

## Step 1: Launch AWS EC2

- Ubuntu 24.04 / 26.04
- t2.medium (Recommended)
- Open Ports

```
22
8080
8084
8081
8082
80
```

---

## Step 2: Install Java

```bash
sudo apt update

sudo apt install openjdk-17-jdk -y

java -version
```

---

## Step 3: Install Maven

```bash
sudo apt install maven -y

mvn -version
```

---

## Step 4: Install Docker

```bash
sudo apt install docker.io -y

sudo systemctl enable docker

sudo systemctl start docker

docker --version
```

---

## Step 5: Install Jenkins

```bash
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list

sudo apt update

sudo apt install jenkins -y

sudo systemctl enable jenkins

sudo systemctl start jenkins
```

---

## Step 6: Configure Jenkins

Install Plugins

- Git
- Maven Integration
- Docker Pipeline
- Docker
- Pipeline
- Pipeline Stage View

Configure

- JDK 17
- Maven
- Docker

Give Docker permission

```bash
sudo usermod -aG docker jenkins

sudo systemctl restart jenkins

sudo systemctl restart docker
```

---

## Step 7: Clone Repository

```bash
git clone https://github.com/Megha11092018/snapchat_cicd_docker.git

cd snapchat_cicd_docker
```
---

# 🐳 Docker Commands

## Build Image

```bash
docker build -t snapchat-cicd-docker .
```

---

## Run Container

```bash
docker run -d \
-p 8084:8080 \
--name snapchat-container \
meghabb11/snapchat-cicd-docker:latest
```

---

## Check Running Containers

```bash
docker ps
```

---

## View Logs

```bash
docker logs snapchat-container
```

---

## Stop Container

```bash
docker stop snapchat-container
```

---

## Remove Container

```bash
docker rm snapchat-container
```

---

# 🔄 Jenkins Pipeline Stages

✅ Checkout Source Code

✅ Maven Build

✅ Package WAR

✅ Docker Build

✅ Docker Login

✅ Docker Image Tag

✅ Docker Push

✅ Deploy Container

✅ Cleanup Old Images

✅ Docker Logout

---

# 📦 Dockerfile

The Dockerfile performs the following tasks:

- Uses Tomcat 9 with JDK 17
- Removes default ROOT application
- Copies generated WAR
- Deploys WAR as ROOT application
- Exposes Port 8080
- Starts Tomcat automatically

---

# 🌐 Application Access

Open in browser

```
http://<EC2-Public-IP>:8084
```

Example

```
http://13.xx.xxx.xxx:8084
```

---

# 📊 Deployment Flow Diagram

```
GitHub
   │
   ▼
Jenkins
   │
   ▼
Checkout
   │
   ▼
Maven Package
   │
   ▼
WAR File
   │
   ▼
Docker Build
   │
   ▼
Docker Hub
   │
   ▼
Docker Run
   │
   ▼
Tomcat
   │
   ▼
Snapchat Clone Live
```

---

# 📖 Manual Build

```bash
mvn clean package
```

Generated file

```
target/snapchat.war
```

---

# 🖥 Deploy Manually

```bash
docker build -t snapchat-cicd-docker .

docker run -d \
-p 8084:8080 \
--name snapchat-container \
snapchat-cicd-docker
```

---

# ✨ Features

- Jenkins CI/CD Pipeline
- Java Maven Web Application
- WAR Deployment
- Dockerized Application
- Apache Tomcat Hosting
- Docker Hub Integration
- Automated Deployment
- AWS EC2 Hosting
- Easy One-click CI/CD

---


# 👩‍💻 Author

**Megha B Biradar**

**GitHub**

https://github.com/Megha11092018

---

## ⭐ Support

If you found this project helpful, consider giving it a ⭐ on GitHub. It helps others discover the project and motivates future improvements.
