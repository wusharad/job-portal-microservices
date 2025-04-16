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
```text
job-portal-microservices/
│
├── README.md
├── docker-compose.yml                # Orchestrates all services
├── .github/workflows/ci.yml         # GitHub Actions for CI/CD
│
├── config-server/                   # Central config service
│   ├── src/
│   └── application.yml
│
├── api-gateway/                     # Entry point to system
│   ├── src/
│   └── application.yml
│
├── discovery-server/                # Eureka server
│   ├── src/
│   └── application.yml
│
├── user-service/                    # Handles registration/login
│   ├── src/
│   ├── Dockerfile
│   └── application.yml
│
├── job-service/                     # Manage jobs (create/list/apply)
│   ├── src/
│   ├── Dockerfile
│   └── application.yml
│
├── notification-service/           # Email/SMS on job apply
│   ├── src/
│   ├── Dockerfile
│   └── application.yml
│
├── config-repo/                     # Git-backed configs (for config-server)
│   ├── user-service.yml
│   ├── job-service.yml
│   └── notification-service.yml
│
├── scripts/                         # DB scripts, init Kafka, etc.
│   └── init-db.sql
│
└── docs/                            # Diagrams, API docs, Postman collections
    └── architecture-diagram.png
```

---

## 🔐 Authentication

Implemented via `JWT`. Authenticated users receive a token which is passed in the header:  
`Authorization: Bearer <jwt_token>`

---

## 📦 Running the Project (via Docker Compose)

```bash
git clone https://github.com/wusharad/job-portal-microservices.git
cd job-portal-microservices
docker-compose up --build
```
---

## 📚 API Documentation

Each service exposes Swagger UI at:  
- `http://localhost:8081/swagger-ui.html` → User Service  
- `http://localhost:8082/swagger-ui.html` → Job Service  
- `http://localhost:8083/swagger-ui.html` → Notification Service  

---

## 📸 Architecture Diagram

![Architecture](./docs/architecture-diagram.png)

---

## ✅ Features

- Microservices with service discovery & routing
- Secure APIs using JWT
- Inter-service communication using REST and Kafka
- Swagger documentation
- CI/CD with GitHub Actions

---

## 💡 Future Enhancements

- Add Admin dashboard
- Redis Caching layer
- CI/CD with staging server deployment

---

## 📜 License

Apache License 2.0

