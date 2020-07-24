# Eureka Client

This is eureka client example

## Docker Build
Build the Spring Boot application image in Docker. Execute below command to build the Docker image.
```sh
docker build -f Dockerfile -t eureka-client .
```

(-f is Docker filename, -t is tagname). <br/>

To view Docker image, execute below command.
```sh
docker images eureka-client
```

To run the Docker image eureka-client, execute the below command
```sh
docker run -p 8101:8101 eureka-client
```

Before performing above steps, please make sure you need to update property eureka.client.service-url.defaultZone in application.properties file located at src/main/resources.

eureka.client.service-url.defaultZone = http://localhost:8761/eureka

or 

eureka.client.service-url.defaultZone = http://<IP address of Docker>:8761/eureka

Now, you try to browse Eureka Server http://localhost:8761 and you will notice that Eureka Client registered with Eureka server.

With security:

```sh
eureka.client.service-url.defaultZone = http://admin:pwd@localhost:8761/eureka/
```

## Docker compose
To running with docker-compose, eureka-server is pre-required.

CD to docker folder, execute below command:
```sh
docker-compose up
```

In docker-compose.yml file, we can update environment variables if necessary. 
