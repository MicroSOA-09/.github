# 🧭 Distributed Tourism App - Hobby Project

Welcome to my hobby project! Motivated by a strong interest in distributed systems and microservice architecture, I decided to redesign an existing modular monolith tourism application (originally built with ASP.NET) into a set of independent microservices using **Golang**

---

## 🚀 Project Overview

- Original monolith application built with ASP.NET (modular architecture).
- Fully restructured into multiple **microservices**, each handling specific domain responsibilities.
- Introduced a **Gateway service** written in **Golang**, acting as the single entry point for the client application (Angular).
- **Authentication** logic has been extracted from the ASP.NET monolith and moved into a dedicated **Auth service**.
- All requests to protected routes are first validated by the Auth service before being forwarded to the target service.
- Every service has its own **dedicated database**, following the Database-per-service pattern.
- All services are **fully Dockerized**, using multi-stage builds and best Docker practices.

---

## 🧱 Tech Stack

- **Golang** – Gateway & new microservices
- **ASP.NET** – Legacy modules (initial version)
- **Angular** – Frontend (client)
- **Docker** – Containerization
- **PostgreSQL/MongoDB** – Per-service databases
- **JWT** – Authentication
- **REST** – Current communication protocol

---

## 🛠️ In Progress / Roadmap

- ✅ **Microservice restructuring**
- ✅ **Authentication service**
- ✅ **Gateway integration**
- ✅ **NoSQL Databases**
- ✅ **Dockerization**
  
Planned features:
- 🔜 Implement **Redis** for caching frequently accessed resources.
- 🔜 Add **Monitoring and Logging** mechanisms.
- 🔜 Introduce a **Follower service** using **Neo4j** for user relationships (graph database).
- 🔜 Switch from HTTP to **gRPC** communication between services for improved performance.

---

## 📦 Running the Project

> Full setup instructions and Docker Compose configuration coming soon.

---
