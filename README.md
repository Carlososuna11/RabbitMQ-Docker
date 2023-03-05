# RabbitMQ Docker Configuration

> RabbitMQ is the most widely deployed open source message broker. [RabbitMQ](https://www.rabbitmq.com/)

This repository contains the configuration files for running RabbitMQ in Docker containers. It is based on the [Faith Musyoka](https://www.section.io/engineering-education/dockerize-a-rabbitmq-instance/p) tutorial.

## Configuration

1. Set up a RabbitMQ container

   The Docker Compose file below will run everything for you via Docker.

```yml
version: "3.8"
services:
  rabbitmq:
    container_name: "rabbitmq"
    image: rabbitmq:3.8-management-alpine
    env_file:
      - ./.env
    ports:
      # AMQP protocol port
      - "5672:5672"
      # HTTP management UI
      - "15672:15672"
```

2. Start the RabbitMQ docker

   From a directory containing the `docker-compose.yml` file created in the previous step, run this command to start all services in the correct order.

```bash
docker-compose up -d
```
