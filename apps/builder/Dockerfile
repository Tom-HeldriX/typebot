# Use the official Node.js 14 image.
# https://hub.docker.com/_/node
FROM node:14

# Install pnpm
RUN npm install -g pnpm

# Create and change to the app directory.
WORKDIR /usr/src/app

# Copy application dependency manifests to the container image.
# A wildcard is used to ensure both package.json AND pnpm-lock.yaml are copied.
COPY package*.json ./

# Install dependencies using pnpm
RUN pnpm install

# Copy local code to the container image.
COPY . .

# Expose the port the app runs on
EXPOSE 8080

# Run the web service on container startup.
CMD [ "pnpm", "start" ]
