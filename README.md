# Welcome to spring-boot-postgres Sample project

## Pre requisites
Java 8
Maven 3.3.x
PostGreSql running instance (H2 for dev profile)

## Postgres Instance Configuration
In order to use your instance please update the [ Database Configuration Section ] section in ```src/main/resources/application.yml```

```yaml

spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/blood
    username: sampleuser
    password: sampledb
    platform: POSTGRESQL
  jpa:
    hibernate:
      ddl-auto: create-drop
    show-sql: true
server:
  port: 8080

endpoints:
  health:
    sensitive: false

management:
  security:
    enabled: false
```

## Run Application Locally
```mvn -Dspring.profiles.active={dev-prod} spring-boot:run```

## Run Integration Tests
```mvn test```

##  Build
```mvn package```

## Use Application
to add a user make a POST like this example : ```http://localhost:8080/user/demis.rizzotto```
to list all application users : ```http://localhost:8080/user```
