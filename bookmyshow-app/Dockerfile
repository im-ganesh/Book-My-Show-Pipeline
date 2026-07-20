# ---------- Stage 1: Build React App ----------
FROM node:16

WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm install --legacy-peer-deps

# Copy application source
COPY . .

# Build React application
RUN npm run build

# ---------- Stage 2: Nginx ----------
FROM nginx:alpine

# Copy React build files
COPY --from=0 /app/build /usr/share/nginx/html

# Expose port
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
