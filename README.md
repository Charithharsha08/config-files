# Smart Parking Management System – Configuration Files

This repository contains the YAML configuration files for all microservices in the **Smart Parking Management System**.

These files are used by the Spring Cloud Config Server to centralize and manage configuration across all services.

## 📁 Microservice Configuration Files

| Microservice Name        | Configuration File       |
|--------------------------|--------------------------|
| API Gateway              | `api-gateway.yml`        |
| User Service             | `user-service.yml`       |
| Vehicle Service          | `vehicle-service.yml`    |
| Parking Space Service    | `parking-space-service.yml` |
| Config Server            | `config-server.yml`      |
| Discovery Server (Eureka)| `discovery-server.yml`   |

> Each file corresponds to the value of `spring.application.name` used in the respective microservice.

## ⚙️ Usage with Spring Cloud Config Server

Make sure your **Config Server** is pointing to this GitHub repository by adding the following to its `application.yml`:

```yaml
spring:
  cloud:
    config:
      server:
        git:
          uri: https://github.com/Charithharsha08/config-files.git
````

In each microservice, add the following to `application.properties`:

```property File

spring.application.name= "service-name"
spring.config.import=configserver:http://localhost:8888
spring.cloud.config.uri=http://localhost:8888
```

## 💡 Notes

* Keep sensitive information like passwords and secrets out of this public repo or use a secure vault system.
* Version control of config files ensures traceability and easier rollback.

---

### 🧑‍💻 Developed By

**Charith Harsha** – Software Engineering students from IJSE , Sri Lanka 🇱🇰

---

```
