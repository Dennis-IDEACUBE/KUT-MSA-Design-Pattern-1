## KUT-MSA-Design-Pattern-1

http://naver.me/57rzy3wd

### Development environment settings
- JDK 17
- Gradle & Maven
- STS + STS Plug-ins & Visual Studio Code + Plug-ins

| Server Role             | Server Hostname           | Specs                                             | IP Address      | Host Port |
| ----------------------- | ------------------------- | ------------------------------------------------- | --------------- | --------- |
| Windows Clinet          | windev                    | 2 vCPU, 4 GB RAM, 100GB Disk EACH                 | 192.168.15.11   |           |
| Docker Server           | dockersvr                 | 4 vCPU, 8 GB RAM(or Higher), 100B Disk EACH       | 192.168.15.101  | 22101     |

### Microservices Patterns With examples in Java(GitHub)

      https://github.com/microservices-patterns/ftgo-application
      
### docker-compose

      sudo apt-get install docker-compose

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

### git config

      git config user.name "Dennis"
      git config user.email "itgenius1004@gmail.com"

      git config user.name
      git config.user.email

### uninstall openjdk

      Remove OpenJDK,
      execute the following command on terminal:
      $ sudo apt-get remove openjdk*
      
      Remove OpenJDK along with dependencies,
      execute the following command on terminal:
      $ sudo apt-get remove --auto-remove openjdk*
      
      Remove OpenJDK and it’s configuration files,
      xecute the following command on terminal:
      $ sudo apt-get purge openjdk*
      
      Remove OpenJDK along with dependencies and it’s configuration files, execute the following command on terminal:
      $ sudo apt-get purge --auto-remove openjdk*
      
