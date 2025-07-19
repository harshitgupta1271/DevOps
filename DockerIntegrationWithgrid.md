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

## 2. Pull Docker Images as you want i have pulled for linux  firefox and chrome but we can change based on os and browsers you want

```bash
# Pull Selenium Hub image
docker pull selenium/hub

# Pull Firefox Node image (for Apple Silicon / ARM)
docker pull --platform=linux/amd64 selenium/node-firefox

# Pull Chrome Node image (for Apple Silicon / ARM)
docker pull --platform=linux/amd64 selenium/node-chrome


## 3. Run Selenium Grid with Docker-- here i am creating docker container for these images i have pulled above.
Step 1: Create Docker Network
docker network create grid

Step 2: Start Selenium Hub
docker run -d -p 4442-4444:4442-4444 --net grid --name selenium-hub selenium/hub


Step 3: Start Chrome Node
docker run -d --net grid \
  -e SE_EVENT_BUS_HOST=selenium-hub \
  -e SE_EVENT_BUS_PUBLISH_PORT=4442 \
  -e SE_EVENT_BUS_SUBSCRIBE_PORT=4443 \
  selenium/node-chrome

Step 4: Start Firefox Node
docker run -d --net grid \
  -e SE_EVENT_BUS_HOST=selenium-hub \
  -e SE_EVENT_BUS_PUBLISH_PORT=4442 \
  -e SE_EVENT_BUS_SUBSCRIBE_PORT=4443 \
  selenium/node-firefox

4. (Optional) Remove Docker Network
docker network rm grid
This removes the grid network after all containers have been stopped.

## here we go now we can run tests remotley in selenium grid just go in xml file and run 







