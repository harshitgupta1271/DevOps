# Selenium Grid Setup with Docker Containers

## 1. Prerequisites

- Download Selenium Server JAR (v4.15.0):
  - [Download Link](https://www.selenium.dev/downloads/)
- Install Docker for Mac (Apple Silicon):
  - [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- Restart your system after installation.

Refer to some basic Docker commands for help:  
[Docker Commands - GitHub](https://github.com/harshitgupta1271/DevOps-CI-CD/blob/main/DockerCommands.md)

---

## 2. You can pull Docker images for the operating system and browser combinations you need. For example, I have already pulled images for:

Linux + Firefox
Linux + Chrome
If you need a different OS (e.g., Windows, macOS) or a different browser (e.g., Edge, Safari), we can update the configuration and pull the appropriate Docker image accordingly.

```bash
# Pull Selenium Hub image
docker pull selenium/hub

# Pull Firefox Node image (for Apple Silicon / ARM)
docker pull --platform=linux/amd64 selenium/node-firefox

# Pull Chrome Node image (for Apple Silicon / ARM)
docker pull --platform=linux/amd64 selenium/node-chrome

# 🚀 Selenium Grid Setup with Docker Compose

This repository provides a simple way to run Selenium Grid using Docker Compose. It includes a Hub and browser nodes (Chrome and Firefox), allowing you to run automated browser tests remotely.

---

## 📄 docker-compose.yml

```yaml
version: '3'

services:
  selenium-hub:
    image: selenium/hub
    ports:
      - "4442:4442"
      - "4443:4443"
      - "4444:4444"
    networks:
      - grid

  node-chrome:
    image: selenium/node-chrome
    environment:
      - SE_EVENT_BUS_HOST=selenium-hub
      - SE_EVENT_BUS_PUBLISH_PORT=4442
      - SE_EVENT_BUS_SUBSCRIBE_PORT=4443
    networks:
      - grid

  node-firefox:
    image: selenium/node-firefox
    environment:
      - SE_EVENT_BUS_HOST=selenium-hub
      - SE_EVENT_BUS_PUBLISH_PORT=4442
      - SE_EVENT_BUS_SUBSCRIBE_PORT=4443
    networks:
      - grid

networks:
  grid:
    driver: bridge




How to Use

1. Start Selenium Grid
2. we need to open cmd on yml file location 
docker-compose up 

Now we can run tests remotly

3. Check Grid and Node Status
Open your browser and visit:
http://localhost:4444/grid/console


3. Scale Nodes (e.g., 3 Chrome nodes)
 Use --scale for newer Docker versions:

docker-compose up -d --scale node-chrome=3

5. Stop and Clean Up Containers
docker-compose down















