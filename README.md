# 🛠️ Job Portal Microservices System

This is a production-grade backend system for a Job Portal, built using Spring Boot Microservices architecture with Docker, Eureka, Gateway, JWT authentication, and more.

---

## 🚀 Tech Stack

- Java 17
- Spring Boot 3.x
- Spring Cloud (Eureka, Config Server, Gateway)
- PostgreSQL
- Kafka or RabbitMQ
- Docker & Docker Compose
- JWT for authentication
- GitHub Actions for CI/CD
- Swagger/OpenAPI for API docs

---

## 🧩 Microservices Overview

| Service               | Description                                 | Port |
|----------------------|---------------------------------------------|------|
| Config Server         | Centralized config management               | 8888 |
| Discovery Server      | Eureka Service Registry                     | 8761 |
| API Gateway           | Single entry-point for all microservices    | 8080 |
| User Service          | Signup, login, JWT auth                     | 8081 |
| Job Service           | Create/search/apply for jobs                | 8082 |
| Notification Service  | Sends emails/SMS on job application events  | 8083 |

---

## 📁 Project Structure
job-portal-microservices/
├── README.md
├── docker-compose.yml
├── .github/
│   └── workflows/
│       └── ci.yml
├── config-server/
│   ├── src/
│   └── application.yml
├── api-gateway/
│   ├── src/
│   └── application.yml
├── discovery-server/
│   ├── src/
│   └── application.yml
├── user-service/
│   ├── src/
│   ├── Dockerfile
│   └── application.yml
├── job-service/
│   ├── src/
│   ├── Dockerfile
│   └── application.yml
├── notification-service/
│   ├── src/
│   ├── Dockerfile
│   └── application.yml
├── config-repo/
│   ├── user-service.yml
│   ├── job-service.yml
│   ├── notification-service.yml
│   └── api-gateway.yml
├── scripts/
│   └── init-db.sql
└── docs/
    └── architecture-diagram.png



---

## 🔐 Authentication

Implemented via `JWT`. Authenticated users receive a token which is passed in the header:  
`Authorization: Bearer <jwt_token>`

---

## 📦 Running the Project (via Docker Compose)

```bash
git clone https://github.com/yourname/job-portal-microservices.git
cd job-portal-microservices
docker-compose up --build
