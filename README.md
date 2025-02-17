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
```

### Verify Docker Installation
```bash
docker --version
```

### Install Docker Compose
```bash
sudo apt install -y docker-compose
```

### Verify Docker Compose Installation
```bash
docker-compose --version
```

---

## Step 2: Create a `.env` File
To manage environment variables, create a `.env` file in your project directory.

```bash
nano .env
```

Example content:
```ini
API_KEY=your_api_key_here
DATABASE_URL=postgres://user:password@localhost/dbname
DEBUG=True
SECRET_KEY=your_secret_key_here
```
Save and exit: **Ctrl + O**, then **Enter**, then **Ctrl + X**.

---

## Step 3: Build and Run Containers
### Build Docker Containers
```bash
docker-compose build
```

### Start Containers
```bash
docker-compose up -d
```

This runs the containers in detached mode (`-d`).

### Check Running Containers
```bash
docker ps
```

---

## Step 4: Stop and Remove Containers
### Stop All Running Containers
```bash
docker stop $(docker ps -aq)
```

### Remove All Containers
```bash
docker rm $(docker ps -aq)
```

### Stop and Remove Containers with Docker Compose
```bash
docker-compose down
```

To also remove volumes:
```bash
docker-compose down -v
```

---

## Step 5: Clean Up Docker Resources
If you want to free up space by removing unused images, containers, and volumes, run:
```bash
docker system prune -a
```

---

## Step 6: Restart Docker Service (if needed)
```bash
sudo systemctl restart docker
```

---

## Step 7: Check Logs for Debugging
To check logs of a specific container:
```bash
docker logs <container_id>
```

To follow logs in real-time:
```bash
docker logs -f <container_id>
```

For Docker Compose logs:
```bash
docker-compose logs
```

---

## Deployment Completed 🎉
Now your application should be running successfully using Docker and Docker Compose!

