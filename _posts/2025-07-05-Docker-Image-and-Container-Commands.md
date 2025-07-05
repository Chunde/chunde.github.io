---
layout: post  
title: Docker Command Cheatsheet  
date: 2025-07-04 20:45:17  
description: Essential Docker commands for image and container manipulation.  
tags: Docker DevOps Containerization  
tabs: true  
---

### Common Docker Commands  

| **Operation**               | **Command**                                                                 | **Explanation**                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| **Run a container**         | `docker run -it <image_name>`                                               | Starts a container interactively (`-i` keeps STDIN open, `-t` allocates a pseudo-TTY). |
| **SSH into a container**    | `docker exec -it <container_id> /bin/bash`                                  | Executes an interactive bash shell inside a running container.                  |
| **Bind local folder**       | `docker run -v /host/path:/container/path <image_name>`                     | Mounts a host directory (`/host/path`) into the container (`/container/path`).  |
| **Change port binding**     | `docker run -p <host_port>:<container_port> <image_name>`                   | Maps the host’s port (e.g., `8080`) to the container’s port (e.g., `80`).      |
| **List running containers** | `docker ps`                                                                | Shows all active containers. Add `-a` to include stopped containers.            |
| **Remove a container**      | `docker rm <container_id>`                                                  | Deletes a stopped container. Use `-f` to force removal of a running container.  |
| **List images**             | `docker images`                                                            | Displays all locally stored Docker images.                                      |
| **Remove an image**         | `docker rmi <image_id>`                                                     | Deletes a Docker image. Use `-f` to force removal.                              |
| **Build an image**          | `docker build -t <tag_name> <path_to_Dockerfile>`                          | Builds an image from a `Dockerfile` in the specified directory.                 |
| **Copy files to container** | `docker cp /host/file <container_id>:/container/path`                       | Copies a file from the host to a running container.                             |
| **View logs**               | `docker logs <container_id>`                                                | Displays the logs of a container. Add `-f` to follow live logs.                 |
| **Stop a container**        | `docker stop <container_id>`                                                | Gracefully stops a running container.                                           |
| **Start a stopped container** | `docker start <container_id>`                                             | Restarts a stopped container.                                                   |

### Notes:  
- Replace `<image_name>`, `<container_id>`, and paths with actual values.  
- For port binding, ensure the host port is available (e.g., `-p 8080:80`).  
- Use `docker --help` or `man docker` for detailed syntax.  

Example for port binding and volume mounting:  
```bash
docker run -p 8080:80 -v /home/user/data:/app/data nginx
```  
This runs an Nginx container with host port `8080` mapped to container port `80` and mounts `/home/user/data` to `/app/data`.