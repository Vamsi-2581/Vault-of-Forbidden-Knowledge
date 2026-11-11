[← Back to README](../README.md) | [Contributing Guide](../CONTRIBUTING.md)

# Docker Basics Cheatsheet (Quick Reference)

A simple, practical reference sheet for building images, running containers, and managing services with Docker and Docker Compose.

## 1. Running and Managing Containers

```bash
docker run -d -p 8080:80 --name web nginx        # Run container in background and map port 8080 to 80
docker ps                                        # List all currently running containers
docker ps -a                                     # List all containers (including stopped ones)
docker stop web                                  # Gracefully stop a running container
docker start web                                 # Start a stopped container
docker restart web                               # Restart a running container
docker rm web                                    # Remove a stopped container
docker rm -f web                                 # Force remove a running container
```

## 2. Inspecting and Debugging Containers

```bash
docker logs web                                  # View logs output by a container
docker logs -f web                               # Follow live log updates in real time
docker exec -it web sh                           # Open an interactive shell inside a running container
docker inspect web                               # View detailed configuration and network IP in JSON
docker top web                                   # Display running processes inside a container
```

## 3. Building and Managing Images

```bash
docker build -t myapp:1.0 .                      # Build an image from a Dockerfile in current directory
docker images                                    # List all images stored locally
docker pull redis:alpine                         # Download an image from Docker Hub
docker rmi myapp:1.0                             # Delete a local image
```

## 4. Docker Compose Multi-Container Services

```bash
docker compose up -d                             # Start all services defined in docker-compose.yml in background
docker compose down                              # Stop and remove all containers, networks, and volumes
docker compose logs -f                           # View combined live logs across all compose services
docker compose ps                                # List status of compose-managed service containers
docker compose restart                           # Restart all compose services
```

## 5. Cleaning Up Disk Space

```bash
docker system prune -f                           # Remove all unused containers, dangling images, and networks
docker volume prune -f                           # Remove all anonymous volumes not used by any container
```
