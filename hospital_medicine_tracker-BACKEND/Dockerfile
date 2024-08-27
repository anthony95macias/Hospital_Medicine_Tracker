# server/Dockerfile

# Use the official Node.js image with Alpine as the base image
FROM node:18-alpine

# Set the working directory
WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN pnpm install

# Copy the rest of the application code
COPY . .

# Expose the port your server is running on
EXPOSE 3000

# Start the server
CMD ["node", "server.js"]
