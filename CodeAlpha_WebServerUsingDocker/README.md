# Docker Web Server

A simple web server deployed using Docker and Nginx, serving a custom HTML website through a bind mount.

## Project Overview

This project demonstrates how to deploy and manage an Nginx web server inside a Docker container.

The default Nginx welcome page was replaced with a custom HTML website hosted on the Ubuntu filesystem.

## Technologies Used

- Ubuntu 26.04.1 LTS
- Docker Engine 29.9.3
- Nginx 1.31.8
- HTML5

## Architecture

Ubuntu Host
- docker-webserver/
  - index.html

Docker Container
- Nginx
- /usr/share/nginx/html/

Port Mapping:
- Host: 8080
- Container: 80

## Deployment Instructions

### 1. Pull the Nginx image

```bash
docker pull nginx
```

### 2. Create the website directory

```bash
mkdir -p ~/docker-webserver
```

### 3. Create your HTML file

Create `index.html` inside the directory.

### 4. Run the container

```bash
docker run -d \
  --name my-nginx \
  -p 8080:80 \
  -v ~/docker-webserver:/usr/share/nginx/html:ro \
  nginx
```

### 5. Access the website

Open:

http://localhost:8080

## Useful Docker Commands

| Command | Purpose |
|---|---|
| docker ps | List running containers |
| docker ps -a | List all containers |
| docker images | List downloaded images |
| docker stop my-nginx | Stop container |
| docker start my-nginx | Start container |
| docker restart my-nginx | Restart container |
| docker logs my-nginx | View container logs |
| docker inspect my-nginx | Inspect container |
| docker stats my-nginx | Monitor resources |
| docker rm my-nginx | Remove container |

## Key Concepts Learned

1. Docker images and containers.
2. Docker port mapping.
3. Container lifecycle management.
4. Detached container execution.
5. Bind mounts.
6. Read-only mounts.
7. Container inspection.
8. Resource monitoring.
9. HTTP connectivity testing.
10. Data persistence.

## Project Outcome

Successfully deployed a customized Nginx web server using Docker.

Verified successful HTTP communication through a `200 OK` response.

Demonstrated persistent website files through Docker bind mounts.
