# Azure DevOps CI/CD Pipeline Project

## Project Overview

This project demonstrates a complete CI/CD pipeline using Azure DevOps, GitHub, Docker, and an Azure Virtual Machine.

The application is a simple static website hosted inside an Nginx Docker container running on an Azure VM. Whenever code is pushed to the GitHub repository, Azure DevOps automatically triggers a pipeline that connects to the Azure VM through SSH, builds a Docker image, and deploys the updated application.

---

## Architecture

GitHub Repository
⬇
Azure DevOps Pipeline
⬇
SSH Connection to Azure VM
⬇
Docker Image Build
⬇
Docker Container Deployment
⬇
Application Available on Browser

---

## Technologies Used

* Azure DevOps
* GitHub
* Azure Virtual Machine (Ubuntu)
* Docker
* Nginx
* YAML Pipelines
* SSH

---

## Project Structure

```text
azure-devops-docker-project/
│
├── index.html
├── Dockerfile
├── azure-pipelines.yml
└── README.md
```

---

## CI/CD Workflow

1. Developer makes changes to the application code.
2. Changes are committed and pushed to GitHub.
3. Azure DevOps automatically detects the change.
4. Pipeline is triggered.
5. Azure DevOps connects to the Azure VM using SSH.
6. Docker image is built on the VM.
7. Existing container is stopped and removed.
8. New container is created using the latest image.
9. Updated application becomes available through the VM public IP.

---

## Docker Commands Used

Build Image

```bash
docker build -t azure-web .
```

Stop Existing Container

```bash
docker stop azure-container
```

Remove Existing Container

```bash
docker rm azure-container
```

Run New Container

```bash
docker run -d --name azure-container -p 80:80 azure-web
```

---

## Azure DevOps Pipeline

The pipeline is configured using `azure-pipelines.yml` and automatically runs whenever code is pushed to the main branch.

Pipeline Tasks:

* Connect to Azure VM using SSH
* Pull latest code from GitHub
* Build Docker image
* Remove old container
* Deploy updated container

---

## Application URL

```text
http://4.213.226.85/
```

---

## Learning Outcomes

Through this project, I gained hands-on experience with:

* Azure DevOps Pipelines
* CI/CD Implementation
* Docker Containerization
* Azure Virtual Machines
* GitHub Integration
* SSH-based Deployment Automation
* YAML Pipeline Configuration

---

## Author

Anand Kumar D

DevOps Engineer
