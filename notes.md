# Commands

## Build image

```console
docker image build -f Dockerfile_ubuntu -t sshd-u:0.0.1 .
docker image build -f Dockerfile_debian -t sshd-d:0.0.1 .
docker image build -f Dockerfile_alpine -t sshd-a:0.0.1 .
```

## Run container

```console
docker container run --rm -p 4022:22 --name aa sshd-a:0.0.1
```

## Test connection

```console
ssh cn330@localhost -p 4022
```

## Stop container

```console
docker container stop aa
```

## Rebuild image with another version

```console
docker container run --rm -p 4022:22 --name aa sshd-a:0.0.2
```

## Login Docker Hub

```console
docker login -u docker_hub_username
```

## Tag image for pushing to Doker Hub

```console
docker image tag sshd-a:0.0.1 docker_hub_username/sshd-a:0.0.1
docker image tag sshd-a:0.0.2 docker_hub_username/sshd-a:0.0.2
```

## Push image to Docker Hub

```console
docker push docker_hub_username/sshd-a:0.0.1
docker push docker_hub_username/sshd-a:0.0.2
```

## Docker compose: Build image

```console
docker compose build
docker compose -p openhouse build
```

## Docker compose: Start and stop services

```console
docker compose up
docker compose up -d
docker compose down
```