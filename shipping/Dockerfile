FROM maven:3.9.11 AS build



WORKDIR /opt/server
COPY src ./src
COPY pom.xml .
RUN mvn clean package
RUN mv target/shipping-1.0.jar shipping.jar 



 FROM eclipse-temurin:17-jre-alpine

WORKDIR /opt/server
COPY --from=build --chown=roboshop:roboshop /opt/server /opt/server
ENV CART_ENDPOINT=cart:8080 \
    DB_HOST=mysql
    CMD ["java" , "-jar", "shipping.jar"]
EXPOSE 8080
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
USER roboshop
ENTRYPOINT ["sh", "-c", "sleep 30 && java -jar shipping.jar"]
