
# Personalized AI Learning Companion – Backend

This is the **Spring Boot microservices backend** for the Personalized AI Learning Companion.  
It provides authentication, user management, progress tracking, courses, and quiz management.

---

## Services Included
- `service-registry` → Eureka service discovery
- `api-gateway` → Spring Cloud Gateway for routing
- `auth-service` → Authentication & JWT
- `user-service` → User profiles
- `course-service` → Course metadata + lecture content
- `progress-service` → User progress tracking
- `quiz-service` → Quiz generation + AI integration

---

## Tech Stack
- Spring Boot 3.x
- Spring Cloud (Eureka, Gateway, Config)
- PostgreSQL (structured data)
- MongoDB (lecture notes, generated content)
- Maven (multi-module build)
- AWS Elastic Beanstalk / EC2 (deployment)

---

## Setup

### Prerequisites
- [PostgreSQL](https://www.postgresql.org/download/)
- [MongoDB](https://www.mongodb.com/try/download/community)
- Java 17+
- Maven

### Run Services
Start databases, then:

```bash
# from each service folder
./mvnw spring-boot:run
