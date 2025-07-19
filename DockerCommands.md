# 🐳 Docker Cheat Sheet (Essential Commands)

## 🔧 Docker Basics

```bash
docker version            # Show Docker client & server version info
docker -v                 # Show Docker client version only
docker info               # Display system-wide Docker details
docker --help             # List all available Docker commands
docker login              # Authenticate with Docker Hub
 

docker images                      # List locally stored Docker images
docker pull <image-name>          # Download image (e.g., Ubuntu) from Docker Hub
docker rmi <image-id or name>     # Remove a specific Docker image


docker ps                          # Show running containers
docker run <image-name>           # Run container (non-interactive)
docker run -it <image-name>       # Run container in interactive terminal mode
docker start <container-id or name>  # Start a stopped container
docker stop <container-id or name>   # Stop a running container
docker rm <container-id or name>     # Delete a stopped container


docker stats                       # Show live resource usage stats of containers
docker system df                   # Show Docker disk usage
docker system prune -f             # Remove:
                                   # - Stopped containers
                                   # - Dangling images
                                   # - Unused networks
                                   # ( Does NOT remove running containers)
