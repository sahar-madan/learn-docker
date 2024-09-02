# Docker and Docker Compose Basics

## Introduction

Docker is a platform that enables developers to automate the deployment of applications inside lightweight, portable containers. Containers package an application with all its dependencies, ensuring consistency across different environments.

Docker Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application's services, networks, and volumes, and then use a single command to start everything.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/) installed on your machine
- [Docker Compose](https://docs.docker.com/compose/install/) installed on your machine

## Docker Basics

### Key Concepts

- **Container**: A lightweight, standalone package that includes everything needed to run a piece of software (code, runtime, system tools, libraries, settings).
- **Image**: A snapshot of a container. Images are used to create containers.
- **Dockerfile**: A script containing a series of instructions to build a Docker image.
- **Docker Hub**: A cloud-based repository for sharing Docker images.

### Basic Commands

- **`docker --version`**: Check Docker version.
- **`docker pull <image>`**: Download an image from Docker Hub.
- **`docker build -t <image-name> .`**: Build a Docker image from a Dockerfile.
- **`docker run <image>`**: Create and start a container from an image.
- **`docker ps`**: List running containers.
- **`docker stop <container-id>`**: Stop a running container.
- **`docker rm <container-id>`**: Remove a stopped container.
- **`docker rmi <image-id>`**: Remove an image.

## Docker Compose Basics

### Key Concepts

- **Service**: A definition of a container in the Docker Compose file.
- **Network**: The communication layer between containers.
- **Volume**: A persistent storage mechanism for container data.

### Basic Commands

- **`docker-compose --version`**: Check Docker Compose version.
- **`docker-compose up`**: Start up all services defined in `docker-compose.yml`.
- **`docker-compose down`**: Stop and remove containers defined in `docker-compose.yml`.
- **`docker-compose build`**: Build or rebuild services defined in `docker-compose.yml`.
- **`docker-compose logs`**: View logs for services.

### Example `docker-compose.yml`

Here’s a basic example of a `docker-compose.yml` file for a web application with a database:

```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
  db:
    image: postgres
    environment:
      POSTGRES_USER: example
      POSTGRES_PASSWORD: example
