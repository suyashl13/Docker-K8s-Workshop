# A Stage starts from the base image.
FROM node:22-alpine AS builder

# Set the working directory to /app in working directory
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY package*.json ./

# Install any needed packages
RUN npm install

# Copy the current directory contents into the container at /app
COPY . .

# STAGE 2: Production environment
FROM builder

# Set the working directory to /app in working directory
WORKDIR /app

# Define environment variable
ENV PORT=3333

# Make port 3333 available to the world outside this container
EXPOSE 3333

# Run app.js when the container launches
CMD [ "npm", "run", "start" ]