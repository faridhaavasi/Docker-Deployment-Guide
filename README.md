# Docker-Deployment-Guide
deploy project simple django


# Docker Deployment Guide

## Prerequisites
Before deploying your application using Docker and Docker Compose, ensure you have the following installed on your Ubuntu system:

- Docker
- Docker Compose
- `.env` file for environment variables (if required)

---

## Step 1: Install Docker and Docker Compose

### Install Docker
```bash
sudo apt update
sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
