# 📸 Snapchat Clone – DevOps CI/CD Project

A simple Snapchat-style landing page built with **HTML + CSS**, packaged with **Maven**, containerized with **Docker**, and deployed automatically to **AWS EC2** using **Jenkins**.

---

## 🚀 Project Overview

This project demonstrates a **complete DevOps CI/CD pipeline** for deploying a static web application.  
It uses:
- **GitHub** → Source Code Management  
- **Jenkins** → Continuous Integration & Continuous Deployment  
- **Maven** → Build and package `.war` file  
- **Docker** → Containerize the app  
- **Tomcat** → Application server  
- **AWS EC2** → Deployment environment  
- **To Access the project** -> *http://PUBLIC_IP:8084*
---

## 🧩 Tech Stack
| Tool | Purpose |
|------|----------|
| **HTML, CSS** | Frontend (Snapchat-style landing page) |
| **Maven** | Build management and `.war` packaging |
| **Tomcat** | Web application server |
| **Docker** | Containerization |
| **Jenkins** | CI/CD automation |
| **AWS EC2** | Cloud hosting |
| **GitHub** | Source control |

---

## ⚙️ Setup Instructions

### 🧱 1. Prerequisites
- Java 11+
- Maven 3.9+
- Docker installed
- Jenkins installed
- AWS EC2 instance running (with Docker installed)
- GitHub account

---
<img width="1888" height="932" alt="image" src="https://github.com/user-attachments/assets/3890e863-9d03-473f-a3fd-403768bcde34" />

<img width="1893" height="920" alt="image" src="https://github.com/user-attachments/assets/604bbbea-6243-4f85-ae3a-6b80eb861328" />

<img width="1882" height="663" alt="image" src="https://github.com/user-attachments/assets/564d9cba-a702-48ac-b231-5427a3f249d4" />

---
### ⚒️ 2. Build the Project
```bash
mvn clean package
```
### 3. Provide jenkins user permission
```bash
visudo
```
### 4. Create Jenkins Credentials for DockerHub
- *Username* and *AccessToken*(DockerHub)
---
*Project Done BY @sak_shetty*
