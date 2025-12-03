FROM node:20 AS builder
WORKDIR /opt/server
EXPOSE 8080
COPY package.json .  /
       *.js .
RUN npm install
ENV MONGO="true" \
    REDIS_URL="redis://redis:6379" \
    MONGO_URL="mongodb://mongodb:27017/users"
CMD [ "server.js"]
ENTRYPOINT ["node"]