# Spring Boot - Validations stopped working after upgrade from 2.2.5 to 2.3.0

If you are using Spring Boot 2.3 or higher, 
add this dependency in your pom.xml file as 
its no longer included within the 'web'-dependency itself.

```xml
<dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-validation</artifactId>
</dependency>
```

#### Jakarta Validation Support in Spring Boot :

Spring Boot 2.X does not support Jakarta EE, 
but support will come with Spring Boot 3.X.

```markdown
    #1 For Spring Boot 2.X you should stick with javax.
    #2 For Spring Boot 3.X you should stick with jakarta.
```

Checkout an application using spring-boot-starter-validation and Jakarta Validation support in Spring Boot:
https://github.com/navinkumarboddu/spring_boot_learning/tree/main/in28minutes