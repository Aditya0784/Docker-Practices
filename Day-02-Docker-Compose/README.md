#  Day 02 - Docker Compose

##  Objective

The objective of this practical was to learn how to manage a multi-container Docker application using Docker Compose.

---

##  Topics Covered

- Docker Compose
- Multi-Container Application
- Docker Compose Services
- MySQL Official Image
- Port Mapping
- Named Volumes
- Custom Bridge Network
- Docker DNS
- Service-to-Service Communication

---

## Project Structure

```text
Day-02-Docker-Compose/
│
├── docker-compose.yml
└── README.md
```

---

## ervices Used

### Backend

- Image: `node-app`
- Container Name: `backend`
- Port: `3000`

### MySQL

- Image: `mysql:8`
- Container Name: `mysql`
- Port: `3306`

---

##  Docker Compose File

```yaml
services:
  backend:
    image: node-app
    container_name: backend
    ports:
      - "3000:3000"

  mysql:
    image: mysql:8
    container_name: mysql
    environment:
      MYSQL_ROOT_PASSWORD: root123
      MYSQL_DATABASE: employee_db
    ports:
      - "3306:3306"
    volumes:
      - mysql-data:/var/lib/mysql

volumes:
  mysql-data:
```

---

##  Commands Used

Start Containers

```bash
docker compose up -d
```

List Running Containers

```bash
docker compose ps
```

List Networks

```bash
docker network ls
```

Inspect Network

```bash
docker network inspect day-02-docker-compose_default
```

List Volumes

```bash
docker volume ls
```

Inspect Volume

```bash
docker volume inspect day-02-docker-compose_mysql-data
```

Enter Backend Container

```bash
docker exec -it backend sh
```

Verify Docker DNS

```bash
ping mysql
```

---

##  What I Learned

- Docker Compose manages multiple containers using a single YAML file.
- A custom bridge network is automatically created by Docker Compose.
- Containers connected to the same network communicate using service names instead of IP addresses.
- Docker provides built-in DNS for service discovery.
- Named volumes are stored on the host machine and preserve data even if the container is removed.
- Docker Compose automatically prefixes network and volume names with the project name.

---

## Practical Verification

Successfully verified:

- Backend container started successfully.
- MySQL container started successfully.
- Docker Compose automatically created a custom bridge network.
- Docker Compose automatically created a named volume.
- Backend container successfully communicated with MYSQL using Docker DNS.


## Verification Command:

```bash
ping mysql
```

Output:

```text
PING mysql (172.18.0.3)
64 bytes from 172.18.0.3
```

## Result

Successfully deployed a multi-container Docker application consisting of a Backend service and a MySQL database using Docker Compose with automatic networking, Docker DNS, and persistent storage using named volumes.
