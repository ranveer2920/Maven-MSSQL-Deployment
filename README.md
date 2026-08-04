## 🚀 Maven + MSSQL Connectivity Project (Docker, Kubernetes, Helm, Jenkins & GitLab CI/CD)

## 📌 Project Overview

This project demonstrates an end-to-end DevOps pipeline for a Java Maven + MSSQL application.
It covers the complete lifecycle: code → build → containerization → deployment → automation → CI/CD, using Jenkins and GitLab pipelines.

The application logic resides in HelloServlet.java, which connects to MSSQL Database and serves dynamic responses.

## 🛠️ Tech Stack

- Backend: Java (Servlets) + Maven  
- Database: Microsoft SQL Server (MSSQL)  
- Containerization: Docker  
- Orchestration: Kubernetes (Deployment + Service)  
- Packaging: Helm  
- CI/CD: Jenkins, GitLab CI/CD  

## 📂 Project Structure
```
├── Deployment.yaml # Kubernetes Deployment manifest
├── Service.yaml # Kubernetes Service manifest
├── Dockerfile # Docker build file
├── DockerHub.png # Docker images are pushed here
├── Jenkinsfile # Jenkins CI/CD pipeline
├── .gitignore
├── pom.xml # Maven build configuration
├── JenkinsPipeline.png # Pipeline execution (Jenkins/GitLab)
├── Output.png # Application output screenshot
├── java-servlet-app/ # Helm chart for app deployment
│ ├── Chart.yaml
│ ├── values.yaml
│ ├── templates/
│ │ ├── deployment.yaml
│ │ ├── service.yaml
│ │ ├── ingress.yaml
│ │ ├── mssql.yaml
│ │ └── tests/test-connection.yaml
└── src/main/java/org/example/
├── HelloServlet.java # Core servlet code
└── Main.java
```
---

## ⚙️ Setup & Installation

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/AkashGadekar0/MavenMSSQLDeploy.git
cd HelloWorldProject
```
2️⃣ Build Maven Artifact
```
mvn clean package
```
3️⃣ Build & Push Docker Image
```
docker build -t your-dockerhub-user/maven-mssql-app:latest .
docker push your-dockerhub-user/maven-mssql-app:latest
```
☸️ Kubernetes Deployment
Apply Kubernetes Manifests
```
kubectl apply -f Deployment.yaml
kubectl apply -f Service.yaml
```
🎯 Helm Deployment
Instead of applying YAML manually, use the Helm chart:
```
cd java-servlet-app
helm install maven-mssql-app .
```
Upgrade / update:
```
helm upgrade maven-mssql-app .
```
Uninstall:
```
helm uninstall maven-mssql-app
```

## 🔄 CI/CD Pipelines

# ✅ Jenkins Pipeline
Defined in Jenkinsfile with stages:
Checkout – Pull latest code
Build Artifact – mvn clean package
Docker Build & Push – Build and push Docker image
Deploy – Helm install/upgrade on Kubernetes

# ✅ GitLab CI/CD Pipeline
Configured in .gitlab-ci.yml (you can add if not yet).
Pipeline stages:
Build Artifact – Compile Maven JAR/WAR
Build Image – Create Docker image
Push Image – Push to Docker registry
Helm Install/Update – Deploy to Kubernetes cluster

## ✅ End-to-End Flow
Code written in HelloServlet.java connects to MSSQL DB
Build artifact created with Maven
Packaged into Docker image
Deployed to Kubernetes using Helm
Automated via Jenkins and GitLab CI/CD pipelines
Output verified through web UI

## 👨‍💻 Author
Ranveer Patil
📧 patilranveer0320@gmail.com
