# MEAN Stack CRUD Application - DevOps Deployment

## 📌 Project Overview

This project demonstrates the containerization and deployment of a full-stack MEAN (MongoDB, Express, Angular, Node.js) CRUD application using Docker, Docker Compose, Nginx reverse proxy, AWS EC2, and GitHub Actions CI/CD pipeline.

---

## 🏗 Architecture

- Frontend: Angular 15
- Backend: Node.js + Express
- Database: MongoDB (Docker container)
- Reverse Proxy: Nginx
- Containerization: Docker & Docker Compose
- Cloud: AWS EC2 (Ubuntu)
- CI/CD: GitHub Actions
- Image Registry: Docker Hub

---

## 🚀 Setup & Deployment Steps

### 1️⃣ Clone Repository

```bash
git clone <your-repo-url>
cd mean-devops-assignment
```
### 2️⃣ Docker Setup

Ensure Docker & Docker Compose are installed.
```bash
docker --version
docker-compose --version
```
### 3️⃣ Run Application

```bash
docker-compose pull
docker-compose up -d
```
http://<EC2_PUBLIC_IP>

---
## 🔁 CI/CD Pipeline

Whenever code is pushed to the main branch:

GitHub Actions builds backend & frontend Docker images

Images are pushed to Docker Hub

GitHub connects to EC2 via SSH

Latest images are pulled

Containers restart automatically

Workflow file: .github/workflows/deploy.yml
---
## 🌐 Nginx Reverse Proxy

Configured to:

Route / → Angular frontend (8081)

Route /api → Backend API (8080)

This allows application access via: http://<EC2_PUBLIC_IP>
