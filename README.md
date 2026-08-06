# 🚀 DevOps Modern End-to-End Deployment Pipeline

<p align="center">

![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-623CE4?style=for-the-badge&logo=terraform&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

</p>

## 📖 Project Overview

This project demonstrates the implementation of a complete **DevOps pipeline** for deploying and managing two different applications using modern DevOps tools and practices.

The solution automates infrastructure provisioning, server configuration, application containerization, and deployment through a CI/CD pipeline.

The project was built using:

- Infrastructure as Code (Terraform)
- Configuration Management (Ansible)
- Containerization (Docker & Docker Compose)
- Continuous Deployment (GitHub Actions)
- Amazon Web Services (AWS EC2)

---

## 🚀 Getting Started

Clone the repository:

```bash
git clone https://github.com/walter-Scotts/devops-final-project.git

cd devops-final-project
```
---

# 🎯 Project Objectives

The objective of this project is to:

- Provision cloud infrastructure using Terraform
- Configure servers automatically using Ansible
- Containerize multiple applications with Docker
- Deploy applications using Docker Compose
- Automate deployments using GitHub Actions
- Demonstrate an end-to-end DevOps workflow

---

# 🛠 Technology Stack

| Category | Technology |
|-----------|------------|
| Cloud Provider | AWS EC2 |
| Infrastructure as Code | Terraform |
| Configuration Management | Ansible |
| Containerization | Docker |
| Multi-Container Management | Docker Compose |
| CI/CD | GitHub Actions |
| Version Control | Git & GitHub |
| Portfolio Application | Python Flask |
| Java Application | Apache Tomcat |
| Operating System | Ubuntu Linux |

---

# 📂 Project Structure

```text
devops-final-project/

├── terraform/
│   ├── main.tf
│   ├── provider.tf
│   ├── variables.tf
│   ├── outputs.tf
│
├── ansible/
│   ├── inventory
│   └── playbook.yml
│
├── portfolio/
│   ├── app.py
│   ├── Dockerfile
│   ├── requirements.txt
│   └── templates/
│
├── samplejavaapp/
│   └── Dockerfile
│
├── docker-compose.yml
│
└── .github/
    └── workflows/
        └── deploy.yml
```

---

# 🏗 System Architecture

The deployment process follows this workflow:

```text
Developer
     │
     │ git push
     ▼
GitHub Repository
     │
     ▼
GitHub Actions
     │
     ▼
Terraform
     │
     ▼
AWS EC2 Instance
     │
     ▼
Ansible
     │
     ▼
Docker Compose
     │
 ┌───┴──────────┐
 ▼              ▼
Portfolio      Java App
Flask          Tomcat
Port 5000      Port 8080
```

---

# ☁️ Infrastructure Provisioning

Infrastructure is provisioned using **Terraform**, enabling Infrastructure as Code (IaC) for repeatable deployments.

Terraform provisions:

- Amazon EC2 Instance
- Virtual Private Cloud (VPC)
- Security Group
- SSH Access

## Security Group Rules

| Port | Purpose |
|------|----------|
| 22 | SSH |
| 5000 | Portfolio Application |
| 8080 | Java Application |

Terraform ensures that the infrastructure can be recreated consistently without manual configuration.

---

# ⚙️ Configuration Management

Server configuration is automated using **Ansible**.

The Ansible playbook performs the following tasks:

- Updates Ubuntu packages
- Installs Git
- Installs Docker
- Starts Docker service
- Clones the GitHub repository

This ensures every server is configured consistently.

---

## 📋 Prerequisites

Before running this project, ensure you have:

- AWS Account
- Terraform
- Docker
- Docker Compose
- Ansible
- Git
- GitHub Account

---

# 🐳 Containerization

Both applications are containerized using Docker.

## Portfolio Application

- Python Flask
- Port 5000

## Java Application

- Apache Tomcat
- Port 8080

Each application contains its own Dockerfile.

Docker Compose is used to deploy both applications together.

Deployment command:

```bash
docker compose up -d --build
```

This command:

- Builds Docker images
- Creates containers
- Restarts services
- Publishes application ports

---

# 🚀 CI/CD Pipeline

Continuous Deployment is implemented using **GitHub Actions**.

Whenever code is pushed to the **main** branch, GitHub Actions automatically deploys the latest version.

Pipeline workflow:

1. Checkout Repository
2. Connect to EC2 through SSH
3. Pull latest code
4. Build Docker images
5. Restart containers using Docker Compose

Deployment command executed on EC2:

```bash
cd /home/ubuntu/devops-final-project

git pull origin main

docker compose up -d --build
```

This removes the need for manual deployments.

---

# ✅ Deployment Verification

Deployment was verified using the following methods.

## Verify Containers

```bash
docker ps
```

---

## View Logs

```bash
docker logs portfolio-app

docker logs java-app
```

---

## Portfolio Website

```
http://<EC2_PUBLIC_IP>:5000
```

---

## Java Application

```
http://<EC2_PUBLIC_IP>:8080/sampleapp/
```

---

## CI/CD Verification

Deployment was confirmed by:

- Successful GitHub Actions workflow
- Running Docker containers
- Updated application content
- Accessible application URLs

---

# 📸 Screenshots

---

## ☁️ AWS Infrastructure

### EC2 Instance

![AWS EC2 Instance](screenshots/ec2-instance.png)

### Terraform Output

![Terraform Output](screenshots/terraform-output.png)

---

## 🐳 Docker Deployment

### Running Docker Containers

![Docker Containers](screenshots/docker-containers.png)

### Portfolio Application

![Portfolio Application](screenshots/portfolio-app.png)

### Java Application

![Java Application](screenshots/java-app.png)

---

## ⚙️ GitHub Actions CI/CD

### Successful Deployment Workflow

![GitHub Actions](screenshots/github-actions.png)

---

## ☸️ Kubernetes Deployment

### Namespace

![Namespace](screenshots/kubernetes/namespaces.png)

### Deployment

![Deployment](screenshots/kubernetes/deployments.png)

### Running Pods

![Pods](screenshots/kubernetes/pods.png)

### Services

![Services](screenshots/kubernetes/services.png)

### NodePort Service URL

![NodePort URL](screenshots/kubernetes/service-url.png)

### Portfolio Running on Kubernetes

![Portfolio Browser](screenshots/kubernetes/portfolio-browser.png)

---

## 📂 GitHub Repository

### Repository Overview

![GitHub Repository](screenshots/screenshots.png)

---

# 🚀 Future Improvements

Future enhancements planned for this project include:

- Deploy the application to Amazon EKS
- Configure Kubernetes Ingress
- Secure the application with HTTPS using cert-manager
- Package deployments with Helm Charts
- Implement GitOps with Argo CD
- Integrate Prometheus & Grafana for monitoring
- Configure Horizontal Pod Autoscaling (HPA)
- Enhance the CI/CD pipeline with automated testing and security scanning

---

# 📚 Skills Demonstrated

This project demonstrates practical experience with:

### ☁️ Cloud & Infrastructure
- Amazon Web Services (AWS EC2)
- Infrastructure as Code (Terraform)
- Cloud Infrastructure Provisioning

### ⚙️ Configuration Management
- Ansible
- Linux System Administration
- Server Automation

### 🐳 Containerization
- Docker
- Docker Compose
- Python Flask Containerization
- Java Application Deployment (Apache Tomcat)

### ☸️ Kubernetes
- Kubernetes
- Minikube
- kubectl
- Namespaces
- Deployments
- ReplicaSets
- Services
- NodePort Networking
- Application Scaling
- Self-Healing Workloads
- YAML Manifests

### 🚀 CI/CD & Version Control
- Git
- GitHub
- GitHub Actions
- Continuous Integration & Continuous Deployment (CI/CD)

### 📖 Documentation
- Technical Documentation
- Deployment Automation
- DevOps Best Practices

---

## 👨‍💻 Author

**Eyinafe Abiodun Emmanuel**

DevOps Engineer | Cloud Engineer | Platform Engineer

- 📧 Email: emmanuelabbeycity09@gmail.com
- 🌐 GitHub: https://github.com/walter-Scotts
- 💼 LinkedIn: https://linkedin.com/in/eyinafe-abiodun-emmanuel-a0781541b

---

# 🙏 Acknowledgements

Special thanks to:

- AWS
- HashiCorp Terraform
- Docker
- Ansible
- GitHub Actions
- Open Source Community

---

# ⭐ Conclusion

This project demonstrates a complete DevOps workflow from infrastructure provisioning to automated deployment.

The implementation follows modern DevOps best practices by combining:

- Infrastructure as Code
- Configuration Management
- Containerization
- Continuous Deployment

The result is a fully automated deployment pipeline capable of consistently deploying multiple applications on AWS with minimal manual intervention.

---

# 🎯 Project Outcomes

Through this project I learned how to:

- Build and manage Kubernetes clusters using Minikube.
- Deploy containerized applications with Deployments.
- Expose applications using Kubernetes Services.
- Scale applications using ReplicaSets.
- Organize workloads using Namespaces.
- Troubleshoot Kubernetes deployments.
- Apply Kubernetes best practices using YAML manifests.

---

# 📄 License

This project is for educational and portfolio purposes.