# 2. Common docker commands.

---

## 2.1 Pulling an Image

The `docker pull` command is used to pull an image from the Docker Hub registry.

Command:
```bash
$ docker pull hello-world
```

## 2.2 Running a Container

The `docker run` command is used to run a container from an image.

Command:
```bash
$ docker run hello-world
```

If we want to run in detached mode use `-d`.

example 

```bash
$ docker run nginx -d # It runs nginx in detached mode.
```

## 2.3 Stopping a Container

The `docker stop` command is used to stop a running container. You need to provide the container ID or name.

Example command:
```bash
$ docker stop <container_id_or_name>
```

## 2.4 Listing All Containers in Detail

The `docker ps -a` command lists all containers, including stopped ones, with detailed information.

Example command:
```bash
$ docker ps -a
```

## 2.5 Executing Commands in a Running Container

The `docker exec` command is used to execute commands inside a running container. This is useful for running additional processes or for interacting with the container's shell.

### Command:

```bash
$ docker exec [OPTIONS] <container_id_or_name> <command> [arg...]
```

- `<container_id_or_name>`: The ID or name of the running container.
- `<command>`: The command you want to execute inside the container.
- `[arg...]`: Optional arguments for the command.

### Options:

- `-i`: Keep STDIN open even if not attached.
- `-t`: Allocate a pseudo-TTY. This is often used for interactive shells.

### Example:

To open a bash shell inside a running container:

```bash
$ docker exec -it <container_id_or_name> /bin/bash
```

This command will give you an interactive shell inside the container, allowing you to run commands as if you were inside the container's environment.

## 2.6 Removing a Container

The `docker rm` command is used to remove a container. You need to provide the container ID or name.

Example command:
```bash
$ docker rm <id>
```

## 2.7 Removing an Image

The `docker rmi` command is used to remove one or more images from your local Docker environment. This is useful when you no longer need an image or want to free up space.

### Command:

```bash
$ docker rmi <image_id_or_name>
```

- `<image_id_or_name>`: The ID or name of the image you want to remove.

### Options:

- `-f`: Force remove the image, even if it's tagged or used by a stopped container.

### Example:

To remove an image with the name `my-image`:

```bash
$ docker rmi my-image
```

If you want to forcefully remove an image, you can use the `-f` option:

```bash
$ docker rmi -f my-image
```

Before removing an image, ensure that no containers are using it. If a container depends on the image, you'll need to stop and remove the container first, or use the `-f` option to force removal of the image.

 