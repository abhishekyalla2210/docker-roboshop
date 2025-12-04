FROM rabbitmq:3.12-management

# Set default user and password
ENV RABBITMQ_DEFAULT_USER=roboshop
ENV RABBITMQ_DEFAULT_PASS=roboshop123

# Expose AMQP and management ports
EXPOSE 5672 15672

# Optional: enable any additional plugins
# RUN rabbitmq-plugins enable --offline rabbitmq_shovel rabbitmq_federation
