# Dockerizing a MERN Stack Application

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)

The setup includes building and running Docker containers for both the frontend and backend, along with MongoDB, and managing them using Docker Compose.

## Getting Started

### Create a Network for Docker Containers

Create a Docker network to allow containers to communicate with each other:

```sh
docker network create docker-network
```

### Build and Run the Client

1. **Build the Client Docker Image**

   ```sh
   cd ./frontend
   docker build -t frontend .
   ```

2. **Run the Client Container**

   ```sh
   docker run --name=frontend --network=docker-network -d -p 5173:5173 frontend
   ```

3. **Verify the Client is Running**

   Open your browser and go to `http://localhost:5173` to see the frontend application in action.

### Run the MongoDB Container

```sh
docker run --network=docker-network --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/mydb mongo:latest
```

### Build and Run the Server

1. **Build the Server Docker Image**

   ```sh
   cd ./backend
   docker build -t backend .
   ```

2. **Run the Server Container**

   ```sh
   docker run --name=backend --network=docker-network -d -p 8000:8000 backend
   ```

## Using Docker Compose

To simplify container management, you can use Docker Compose to build and run all services:

```sh
docker-compose up -d
```

This command will build and start the frontend, backend, and MongoDB containers as defined in your `docker-compose.yml` file.

# I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](bitfield.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.