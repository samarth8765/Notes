FROM node

WORKDIR /app

# COPY [from_current_system] to [image file system]
COPY package.json /app

# RUN command is executed when creating a image
RUN npm install

COPY . /app

# Port forwarding exposing our docker port 80.
EXPOSE 80

# CMD command is executed when creating a container
CMD ["node", "server.js"] 