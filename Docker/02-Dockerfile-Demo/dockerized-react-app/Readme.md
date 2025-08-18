### 1. Difference between RUN and CMD in Docker

`RUN` is used to execute a command while building an image. It is usually used to install packages or set environment variables.

`CMD` is used to set the default command to run when the container is started. It can be overridden by the user when running the container with the `docker run` command.

## 2. Docker File in detail.f

The above Dockerfile is a multi-stage Dockerfile which builds a Docker image for a React application.

The Dockerfile is using the `node:22-alpine` base image, which is a minimal image that contains Node.js 22 and the Alpine Linux distribution.

The `WORKDIR /app` instruction sets the working directory in the container to `/app`.

The `COPY package*.json ./` instruction copies the `package.json` and `package-lock.json` files to the working directory in the container.

The `RUN npm install` instruction installs all the dependencies listed in the `package.json` file.

The `COPY . .` instruction copies all the files from the current directory to the working directory in the container.

The `EXPOSE 5173` instruction exposes the port 5173 on the container to the host, which is the default port for the React development server.

The `CMD ["npm", "run", "dev"]` instruction sets the default command to run when the container is started. The command is `npm run dev`, which starts the React development server. This can be overridden by the user when running the container with the `docker run` command.
