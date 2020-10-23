

### Actuator监控

http://${ip}:${port}/actuator

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```

```properties
management.endpoints.web.exposure.include=*
management.endpoint.health.show-details=always
```

