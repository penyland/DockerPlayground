# Use the official Node.js image as a base image
FROM node:23-alpine AS base

# Set the working directory
WORKDIR /usr/src/app

# Copy hello.js to the working directory
COPY server.js .

# Expose port 3000
EXPOSE 3000

# Run the server.js script
CMD ["node", "server.js"]