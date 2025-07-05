---
layout: post  
title: WordPress Docker Setup  
date: 2025-07-04 13:05:10  
description: Guide for deploying WordPress with Docker on Ubuntu including port binding and volume mounting  
tags: Docker WordPress Ubuntu Web-Development  
tabs: true  
---

## Prerequisites
1. Ubuntu system (20.04/22.04 recommended)
2. Docker installed (if not, follow Step 1)
3. Basic terminal familiarity

## Step-by-Step Guide

### 1. Install Docker
```bash
sudo apt update
sudo apt install docker.io docker-compose
sudo systemctl enable --now docker
sudo usermod -aG docker ${USER}  # Add current user to docker group
newgrp docker  # Refresh group permissions
```

### 2. Create Docker Compose File
Create `docker-compose.yml` with:

```yaml
version: '3.8'

services:
  db:
    image: mysql:5.7
    volumes:
      - db_data:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: your_root_password
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wordpress
      MYSQL_PASSWORD: wordpress
    restart: unless-stopped

  wordpress:
    depends_on:
      - db
    image: wordpress:latest
    ports:
      - "8080:80"  # Binds host port 8080 to container port 80
    volumes:
      - ./wp-content:/var/www/html/wp-content  # Local folder binding
    environment:
      WORDPRESS_DB_HOST: db:3306
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: wordpress
      WORDPRESS_DB_NAME: wordpress
    restart: unless-stopped

volumes:
  db_data:
```

### 3. Key Configuration Details

**Port Binding**:
- `ports: - "8080:80"` maps:
  - Host machine port: 8080 (accessible via `http://localhost:8080`)
  - Container port: 80 (WordPress default port)

**Volume Binding**:
- `volumes: - ./wp-content:/var/www/html/wp-content` creates:
  - Local folder: `./wp-content` (relative to compose file)
  - Container path: WordPress content directory
  - Changes persist after container restarts

### 4. Launch the Stack
```bash
docker-compose up -d
```

### 5. Verification
1. Check running containers:
   ```bash
   docker ps
   ```
2. Access WordPress at `http://localhost:8080`
3. Check local filesystem for created `wp-content` folder

### 6. Management Commands
- Stop containers: `docker-compose down`
- View logs: `docker-compose logs -f`
- Update images: `docker-compose pull && docker-compose up -d`

## Troubleshooting
1. Port conflicts: Change left-side port in `ports` mapping (e.g., `8081:80`)
2. Permission issues: 
   ```bash
   sudo chown -R $USER:$USER ./wp-content
   ```
3. Database errors: Verify credentials match in both service definitions