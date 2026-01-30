# Assignment-4

# 🚀 End-to-End CI/CD: GitHub Actions + Docker + Kubernetes

This project demonstrates an **end-to-end CI/CD pipeline** using **GitHub Actions** for Continuous Integration and **Kubernetes (Minikube)** for local deployment.

The pipeline builds, tests, and publishes a Docker image automatically, while deployment to Kubernetes is executed locally due to Minikube running on a developer machine.

---

## 🎯 Objective

- Set up a CI pipeline using GitHub Actions
- Build and test a Python application automatically
- Build and push Docker images to Docker Hub
- Deploy the application to a local Kubernetes cluster (Minikube)
- Use GitHub Secrets for secure credential management

---

## 🛠 Tech Stack

- Python (Flask)
- GitHub Actions
- Docker
- Docker Hub
- Kubernetes
- Minikube
- kubectl

---

## 🐍 Application Overview

The application is a simple Python Flask app that serves a basic HTTP response.

Example response:
Deployed via GitHub Actions CI/CD 🚀

## 🐳 Docker Image

- Docker image is built automatically by GitHub Actions
- Image is pushed to Docker Hub

Image format:
beastguhan/cicd-app:latest

Code Push → GitHub Actions → Tests → Build Image → Push to Docker Hub


### GitHub Secrets Used

| Secret Name | Purpose |
|------------|--------|
| DOCKER_USERNAME | Docker Hub username |
| DOCKER_PASSWORD | Docker Hub access token |

---

## ☸️ CD Strategy (Local Kubernetes)

Since **Minikube runs locally**, it is not accessible from cloud-hosted GitHub Actions runners.

Therefore:
- **CI** is handled in GitHub Actions
- **CD** is handled locally using kubectl

### Deployment Steps (Local)

```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml

minikube service cicd-service

