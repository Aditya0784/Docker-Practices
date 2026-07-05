# Docker Node.js Demo

A simple Node.js application containerized using Docker. This project demonstrates the basic Docker workflow, including creating a Dockerfile, building an image, and running a container.

## Project Structure

```text
node-app/
├── app.js
├── package.json
└── Dockerfile
```

## Technologies Used

* Docker
* Node.js
* Alpine Linux

## Dockerfile Instructions Used

* `FROM`
* `WORKDIR`
* `COPY`
* `RUN`
* `EXPOSE`
* `CMD`

## Build the Docker Image

```bash
docker build -t node-app .
```

## Verify the Image

```bash
docker images
```

## Run the Docker Container

```bash
docker run -d --name my-node-app -p 3000:3000 node-app
```

## Check Running Containers

```bash
docker ps
```

## View Container Logs

```bash
docker logs my-node-app
```

## Stop the Container

```bash
docker stop my-node-app
```

## Start the Container Again

```bash
docker start my-node-app
```

## Remove the Container

```bash
docker rm -f my-node-app
```

## Remove the Docker Image

```bash
docker rmi node-app
```

## Application

The application starts a simple HTTP server on **port 3000** and returns:

```text
Hello from Docker 🚀
```

## Concepts Learned

* Docker Image
* Docker Container
* Dockerfile
* Base Image (`FROM`)
* Working Directory (`WORKDIR`)
* Copying Files (`COPY`)
* Installing Dependencies (`RUN`)
* Exposing Ports (`EXPOSE`)
* Running the Application (`CMD`)
* Image Build
* Container Creation
* Port Mapping

## Learning Outcome

After completing this project, I learned how to:

* Create a Dockerfile for a Node.js application.
* Build a Docker image.
* Run a Docker container.
* Expose and map application ports.
* Verify running containers and images.
* View container logs.
* Deploy a Dockerized application on an Ubuntu server running on Oracle Cloud.

---

**Author:** Aditya Rao
