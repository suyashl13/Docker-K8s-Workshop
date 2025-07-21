# Docker Overview

Docker is a containerization platform which allows us to package, ship and run applications in containers. Containers are lightweight and portable: they provide a consistent and reliable way to deploy applications across different environments.

## Advantages of Docker

- **Lightweight**: Containers are much lighter than Virtual Machines as they don't require a separate Operating System for each container.
- **Portable**: Docker containers are highly portable. They can be run on any system that has docker installed, regardless of the underlying hardware or OS.
- **Isolated**: Docker containers are isolated from each other. This means that if one container is compromised, the other containers are not affected.
- **Easy to Manage**: Docker containers are easy to manage. We can create, start, stop and delete containers with a single command.
- **Fast Deployment**: Docker containers can be deployed quickly and easily. This makes them ideal for applications which require rapid deployment.
- **Resource Efficient**: Docker containers are resource efficient. They only use the resources required to run the application. This makes them ideal for applications which require low resources.

# Running My First Image (Hello World)

```bash
$ docker run hello-world
```

