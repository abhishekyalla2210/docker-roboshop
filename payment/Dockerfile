FROM python:3.9 AS builder
WORKDIR /opt/server
COPY payment.ini  *.py *.txt .
RUN pip3 install -r --prefix=/install requirements.txt





FROM python:3.9.25-alpine
EXPOSE 8080
WORKDIR /opt/server
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop

COPY --from=build /opt/server /opt/server
ENV CART_HOST=cart
ENV CART_PORT=8080
ENV USER_HOST=user
ENV USER_PORT=8080
ENV AMQP_HOST=rabbitmq

ENV AMQP_USER="roboshop"
ENV AMQP_PASS="roboshop123"
CMD ["uwsgi" , "--ini","payment.ini"]
