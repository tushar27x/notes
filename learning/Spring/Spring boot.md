
- Running applications
```shell
java -jar myApp.jar
```

- spring developer tool
```xml
<dependency>  
    <groupId>org.springframework.boot</groupId>  
    <artifactId>spring-boot-devtools</artifactId>  
    <scope>runtime</scope>  
    <optional>true</optional>  
</dependency>
```

- spring actuator
```xml
...
<dependency>  
    <groupId>org.springframework.boot</groupId>  
    <artifactId>spring-boot-starter-actuator</artifactId>  
</dependency>
...
```

```java
// application.starter
// adds meta data about the application

spring.application.name=demo  
  
// management.endpoints.web.exposure.include=health,info  

// we can use '*' to add all endpoints
management.endpoints.web.exposure.include=*
management.info.env.enabled=true  
  
info.app.name = My app  
info.app.description=My first spring application  
info.app.version= 1.0.0

```

- spring boot starter security
```xml
<dependency>  
    <groupId>org.springframework.boot</groupId>  
    <artifactId>spring-boot-starter-security</artifactId>  
</dependency>
```