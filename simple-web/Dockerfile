# Specify base image.
FROM node:alpine

# Define the working directory.
# All commands below will be executed in the scope of this directory.
WORKDIR /usr/app

# Copy package.json to working directory.
# /usr/app/package.json
# We do this so that if any changes happen that do not effect
# the package.json (dependencies) we don not end up executing
# 'npm install' when we didn't really need too.
COPY ./package.json .

# Install some dependencies.
RUN npm install

# Copy necessary files to working directory.
# /usr/app/Dockerfile
# /usr/app/index.js
# /usr/app/node_modules
COPY . .

# Execute image.
CMD ["npm", "start"]

# docker run -p 8080:8080 <id|tag>