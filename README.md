## KUT-MSA-Design-Pattern-1

### Development environment settings
- JDK 17
- Gradle & Maven
- STS + STS Plug-ins & Visual Studio Code + Plug-ins

### Microservices Patterns With examples in Java(GitHub)

      https://github.com/microservices-patterns/ftgo-application

### .profile
      #export DOCKER_HOST=localhost:2375
      export DOCKER_HOST_IP=192.168.15.101
      export COMPOSE_HTTP_TIMEOUT=240

### dynamodblocal-init

      # FROM python:2.7.16-alpine3.9
      FROM python:3-alpine3.11
      RUN pip install awscli --upgrade
      COPY create-dynamodb-tables.sh .
      COPY ftgo-order-history.json .
      COPY wait-for-dynamodblocal.sh .
      RUN chmod +x *.sh
      HEALTHCHECK --interval=10s --retries=10 --timeout=3s CMD [[ -f /tables-created ]]
      
      CMD ./wait-for-dynamodblocal.sh && ./create-dynamodb-tables.sh
