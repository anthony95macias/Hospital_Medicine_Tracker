# client/Dockerfile

# Use the official Node.js image with Alpine as the base image
FROM node:18-alpine

# Set the working directory
WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN pnpm install

# Copy the rest of the application code
COPY . .

# Build the application
RUN pnpm run build

# Use Nginx with Alpine for serving the built assets
RUN apk add --no-cache nginx

# Copy built assets from the previous stage
COPY /dist /usr/share/nginx/html

# Expose the port Nginx is running on
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]

