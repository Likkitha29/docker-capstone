# Docker Capstone Project — Containerized Website with Nginx

## Project Overview
This project demonstrates how to containerize a static website using Docker and Nginx. Two versions of the website are built as separate Docker images and run in separate containers on different host ports.

## Technologies Used
- Docker
- Nginx Alpine
- HTML and CSS
- Git and GitHub

## Project Structure
```text
docker-capstone/
├── Dockerfile
├── index.html
└── README.md
```

## Dockerfile
```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80
```

## Build Docker Images
Build Version 1:
```bash
docker build -t docker-capstone:v1 .
```

Build Version 2:
```bash
docker build -t docker-capstone:v2 .
```

## Run the Containers
Run Version 1 on port 8081:
```bash
docker run -d --name capstone-v1 -p 8081:80 docker-capstone:v1
```

Run Version 2 on port 8082:
```bash
docker run -d --name capstone-v2 -p 8082:80 docker-capstone:v2
```

## Access the Website
- Version 1: http://localhost:8081
- Version 2: http://localhost:8082

## Verify Containers and Images
```bash
docker ps
docker images
```

## Architecture
```text
Browser (localhost:8081) → Docker host port 8081 → Version 1 container → Nginx port 80
Browser (localhost:8082) → Docker host port 8082 → Version 2 container → Nginx port 80
```

## GitHub Repository
https://github.com/Likkitha29/docker-capstone

## Conclusion
This project demonstrates building Docker images, running multiple containerized website versions, mapping host ports to container ports, and managing source code with Git and GitHub.