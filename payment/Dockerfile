FROM python:3.9
WORKDIR /opt/server
COPY payment.ini .
COPY *.py .
COPY *.txt .
RUN pip3 install -r requirements.txt
ENV CART_HOST=cart
ENV CART_PORT=8080
ENV USER_HOST=user
ENV USER_PORT=8080
ENV AMQP_HOST=rabbitmq

ENV AMQP_USER="roboshop"
ENV AMQP_PASS="roboshop123"
CMD ["uwsgi" , "--ini","payment.ini"]