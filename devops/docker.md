# Docker

Content

- Naming
- Commands
- Dockerfile
- Volumes
- Docker Compose

## Naming

- dockerfile, blueprint for building docker image
- image, immutable snapshot of a project
- container, running process of an image
- dockerhub, store images in cloud

## Commands

```bash
docker ps
```

```bash
# Build the image
docker build -t ariaandika/demoapp:1.0
```

```bash
# Run image by id
docker run b9094046D -p 5000:8080
```

## Dockerfile

```Dockerfile
# Dockerfile
# Every step is called layer, layer may be cached

# get starting point from some image
FROM node:12

# Like cd
WORKDIR /app

# Install package first so it will be cached
#    Local         Container
COPY package*.json ./

RUN npm i

# Then copy the project files, excluding files in .dockerignore
COPY . .

ENV PORT=8080

# Expose 8080 in container to 8080 in host machine
EXPOSE 8080

# No shell startup, like exec command
CMD [ "npm", "start" ]

```

then build the docker

## Volumes

a folder for keeping container state

```bash
docker volume create database-volumes

docker run --mount source=database-volumes,target=/stuff
```

## Docker Compose

```yml
# docker-compose.yml

version: '3'
services:
  web:
    build: .
    ports:
      - "8080:8080"
  db:
    image: "mysql"
    environtment:
      MYSQL_ROOT_PASSWD: "root"
    volumes:
      - db-data:/foo

volumes:
  db-data:
```

launching

```bash
docker-compose up

# Delaunch
docker-compose down
```
