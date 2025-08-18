# Multistage Build - Builder Stage
FROM node:18-alpine AS builder

WORKDIR /app

# Copy only the package files first for better caching
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the source files
COPY . .

# Build the application
RUN npm run build

# Serve Stage - Production Image
FROM nginx:alpine

# Remove default nginx static files
RUN rm -rf /usr/share/nginx/html/*

# Copy built static files from builder
COPY --from=builder /app/build /usr/share/nginx/html

# Optional: Copy custom nginx config if available
# COPY nginx.conf /etc/nginx/nginx.conf

# Expose port
EXPOSE 80

# Start Nginx in foreground
CMD ["nginx", "-g", "daemon off;"]
