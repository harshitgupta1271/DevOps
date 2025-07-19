# 🚀 Selenium Grid Setup with Docker Compose-- This is just to replace manaul efforts 

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















