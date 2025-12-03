FROM node:20-alpine3.21 AS build
WORKDIR /opt/server
COPY server.js ./
COPY package.json ./
RUN npm install 

FROM node:20-alpine3.21
WORKDIR /opt/server
EXPOSE 8080
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
COPY --from=build /opt/server /opt/server
RUN chown=roboshop:roboshop /opt/server 
ENV  REDIS_HOST="redis" \
     CATALOGUE_HOST="catalogue" \
     CATALOGUE_PORT="8080"
CMD ["node" , "server.js"]
USER roboshop