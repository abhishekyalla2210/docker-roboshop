FROM node:20
WORKDIR /opt/server
COPY server.js ./
COPY package.json ./
RUN npm install 

# FROM node:20-alpine3.21
# WORKDIR /opt/server
EXPOSE 8080
RUN groupadd -r roboshop && useradd -r -g roboshop roboshop
# COPY --from=build --chown=roboshop:roboshop /opt/server /opt/server 
ENV  REDIS_HOST="redis" \
     CATALOGUE_HOST="catalogue" \
     CATALOGUE_PORT="8080"
CMD ["node" , "server.js"]
USER roboshop