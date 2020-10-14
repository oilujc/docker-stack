# Docker stack

## Environment

To start the docker-compose it is necessary to include the .env file


## Running the application

The application is built with Node.js and already has all environment configured with docker. To start the application you will need `docker` and `docker-compose` installed on the machine. Having that you may run:

```shell
docker-compose -f docker-compose.stack.yml up
```

And then the application and database will be started:

```shell
Starting stack_db ... done
```

## Using external networks

```yaml
# docker-compose2
version: '3.1'
services:
  app:
    build: .
    networks: 
      - docker-stack_dev-network
    external_links:
      - pg_db:pg_db

networks:
  docker-stack_dev-network:
    external: true
```
