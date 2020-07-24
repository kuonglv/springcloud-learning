# Eureka Server Sample

Run this project as a Spring Boot app (e.g. import into IDE and run
main method, or use "mvn spring-boot:run or gradle bootRun or ./gradlew bootRun"). It will start up on port
8761 and serve the Eureka API from "/eureka".

## Resources

| Path             | Description  |
|------------------|--------------|
| /                        | Home page (HTML UI) listing service registrations          |
| /eureka/apps         | Raw registration metadata |

## Docker Build
To build docker image, run the following command:
```sh
docker build -t eureka-server .
```

-t: tagname (eureka-server for example) <br/>
. : current folder that contains Dockerfile <br/><br/>

To view docker image, execute below command:
```sh
docker images -a
```

To run the Docker image eureka-server, execute the below command
```sh
docker run -p 8761:8761 eureka-server
```

To see the containers running in Docker, execute the below command.
```sh
docker ps
```
## Docker Container

There is a Maven goal (using a [plugin](https://github.com/spring-cloud-samples/eureka/blob/feature/docker/pom.xml#L48)) to 
generate the Docker container. The container is published in dockerhub at `springcloud/eureka`.
