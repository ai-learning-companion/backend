# Personalized AI Learning Companion – Backend

This is the **Spring Boot microservices backend** for the Personalized AI Learning Companion.  
It provides authentication, user management, progress tracking, courses, and quiz management.

---

## Services Included
| Service | Description | Port |
|---------|-------------|------|
| `service-registry` | Eureka service discovery | 8761 |
| `api-gateway` | Spring Cloud Gateway for routing | 8080 |
| `auth-service` | Authentication & JWT | 9001 |
| `user-service` | User profiles | 9002 |
| `course-service` | Course metadata + lecture content | 9003 |
| `progress-service` | User progress tracking | 9004 |
| `quiz-service` | Quiz generation + AI integration | 9005 |

---

## Tech Stack
- **Spring Boot 3.x**
- **Spring Cloud** (Eureka, Gateway)
- **PostgreSQL** (structured data)
- **MongoDB** (lecture notes, generated content)
- **Maven** (multi-module build)
- **Java 17+**
- **AWS Elastic Beanstalk / EC2** (deployment, optional)

---

## Prerequisites
- [PostgreSQL](https://www.postgresql.org/download/)
- [MongoDB](https://www.mongodb.com/try/download/community)
- Java 17 or higher
- Maven 3.x
- IDE (IntelliJ IDEA, VS Code, etc.)

**Databases to create:**
- PostgreSQL: `authdb`, `userdb`, `coursedb`, `progressdb`, `quizdb`
- MongoDB: `course_db`, `quiz_db`

---

## Setup & Run

1. **Start Databases**
   - PostgreSQL: `sudo service postgresql start` or using Docker
   - MongoDB: `sudo service mongod start` or using Docker

2. **Run Services in Order**
   ```bash
   # 1. Service Registry
   cd service-registry
   ./mvnw spring-boot:run

   # 2. API Gateway
   cd ../api-gateway
   ./mvnw spring-boot:run

   # 3. Business Services
   cd ../auth-service
   ./mvnw spring-boot:run

   cd ../user-service
   ./mvnw spring-boot:run

   cd ../course-service
   ./mvnw spring-boot:run

   cd ../progress-service
   ./mvnw spring-boot:run

   cd ../quiz-service
   ./mvnw spring-boot:run

