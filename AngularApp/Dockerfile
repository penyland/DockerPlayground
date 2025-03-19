# Stage 1: Build the Angular app
FROM node:alpine AS build

WORKDIR /app

# Copy package.json and package-lock.json
COPY my-app/package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application
COPY my-app/ ./

# Build the application
RUN npm run build -- --configuration production

# Stage 2: Serve the app with Nginx
FROM nginx:alpine

# Copy the build output to replace the default nginx contents
COPY --from=build /app/dist/my-app/browser/*/. /usr/share/nginx/html/

# Copy custom nginx config if needed
# COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose port 80
EXPOSE 80

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]