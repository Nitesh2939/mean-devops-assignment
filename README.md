# 🚀 MEAN Stack DevOps Deployment – CI/CD Implementation

## 👨‍💻 Candidate Details
- **Name:** Nitesh Singh Bhati  
- **Project:** MEAN Stack DevOps Assignment  
- **Tech Stack:** MongoDB, Express, Angular, Node.js  
- **Cloud Platform:** AWS EC2 (Ubuntu 24.04 LTS)  
- **CI/CD:** GitHub Actions + Docker Hub + Watchtower  

---

# 📌 Project Overview

This project demonstrates complete containerization and deployment of a full-stack MEAN (MongoDB, Express, Angular, Node.js) application using modern DevOps practices.

The application is fully automated using CI/CD pipelines and deployed on an AWS Ubuntu cloud server.

---

# 🏗️ Architecture Overview

User → AWS EC2 (Ubuntu) → Nginx (Frontend) → Backend API → MongoDB  
GitHub → GitHub Actions → Docker Hub → Watchtower → Auto Deployment  

---

# 🐳 Docker Implementation

## Backend
- Base Image: `node:18-alpine`
- Optimized production image
- Exposed Port: 8080

## Frontend
- Multi-stage Docker build
- Angular production build
- Served using Nginx
- Exposed Port: 80

---

# 📦 Docker Hub Repositories

- Backend: `nitesh2939/mean-backend`
- Frontend: `nitesh2939/mean-frontend`

Images are automatically built and pushed via GitHub Actions.

---

# ☁️ Cloud Deployment (AWS EC2)

### Server Configuration:
- Ubuntu 24.04 LTS
- Docker Engine
- Docker Compose
- Watchtower for automatic updates

### Public Access: http://13.60.35.131

# 🔄 CI/CD Pipeline

## Continuous Integration (CI)

Implemented using **GitHub Actions**.

### Trigger:
- On every push to `main` branch

### Pipeline Steps:
1. Checkout repository
2. Login to Docker Hub
3. Build backend Docker image
4. Build frontend Docker image
5. Push images to Docker Hub

Workflow File: .github/workflows/docker.yml

## Continuous Deployment (CD)

Implemented using **Watchtower** on the EC2 server.

### Process:
1. GitHub pushes new image to Docker Hub
2. Watchtower checks for updates every 30 seconds
3. If new image detected:
   - Pull latest image
   - Restart container automatically

No manual SSH deployment required.

# 📁 Project Structure

mean-devops-assignment/
│
├── backend/
│ ├── Dockerfile
│ └── Node.js Express API
│
├── frontend/
│ ├── Dockerfile
│ └── Angular Application
│
├── docker-compose.yml
└── .github/workflows/docker.yml

# 🚀 Deployment Instructions

## 1️⃣ Clone Repository
```bash
git clone https://github.com/Nitesh2939/mean-devops-assignment.git
cd mean-devops-assignment


