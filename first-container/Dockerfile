# Test web app that returns the name of the host/pod/container servicing req
# Linux x64

#FROM must be the first non-comment instruction in the Dockerfile.
#FROM <image>:<tag>
FROM node:current-alpine

#LABEL <key>=<value> [<key>=<value> ...]
#The LABEL instruction adds metadata to an image.
#To include spaces within a LABEL value, use quotes and backslashes as you would in command-line parsing.
LABEL org.opencontainers.image.title="Hello Guys!" \
      org.opencontainers.image.description="Web server showing host that responded" \
      org.opencontainers.image.authors="@muyerina"

# Create directory in container image for app code
RUN mkdir -p /usr/src/app

# Copy app code (.) to /usr/src/app in container image
COPY . /usr/src/app

# Set working directory context
WORKDIR /usr/src/app

# Install dependencies from packages.json
RUN npm install

# Command for container to execute
ENTRYPOINT [ "node", "app.js" ]