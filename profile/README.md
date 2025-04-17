MicroSOA: Microservices Architecture for Tourism Application
Welcome to MicroSOA, a hobby project exploring distributed systems by transforming a modular monolithic tourism application into a scalable microservices architecture. Built with modern technologies like Golang, Docker, and gRPC, MicroSOA demonstrates best practices in modularity, security, and performance optimization.


Project Overview
MicroSOA is a passion project to reimagine a monolithic tourism application (originally built with ASP.NET) as a distributed system. The goal was to enhance scalability, modularity, and maintainability by adopting a microservices architecture. Key features include:

Modular Design: Isolated services for authentication, blog, and user management, each with dedicated databases.
Scalable Infrastructure: Containerized with Docker and optimized for horizontal scaling using NoSQL databases.
Modern Communication: Transitioning from HTTP to gRPC for low-latency, type-safe inter-service communication.
Secure Access: Centralized authentication with token verification for protected routes.

The project showcases expertise in distributed systems, cloud-native development, and real-time communication, aligning with industry trends in microservices.
Architecture
MicroSOA follows a microservices architecture with a gateway pattern:

Gateway Service: Acts as the entry point, handling client requests (from an Angular frontend) and routing them to appropriate services.
Authentication Service: Secures the system by verifying JWT tokens for protected routes.
Blog Service: Manages blog posts, comments, and ratings, with data stored in MongoDB.
User Service: Handles user profiles and preferences, using PostgreSQL for structured data.
Frontend Service: Provides an Angular-based UI for user interaction.
Infrastructure: Includes database configurations (MongoDB, PostgreSQL, Redis) and NGINX for load balancing.

All services are containerized with Docker, ensuring consistent deployment. Redis supports caching and real-time data, while gRPC is being adopted for efficient inter-service communication.
(Diagram to be added illustrating Gateway, Services, Databases, and NGINX.)
Services
Gateway Service

Repository: gateway-service
Description: The Gateway Service, written in Golang, serves as the single entry point for client requests. It routes HTTP requests from the Angular frontend to appropriate microservices and handles load balancing with NGINX.
Key Features:
Routes requests based on URL paths (e.g., /blog to Blog Service, /user to User Service).
Integrates with Authentication Service to enforce token verification for protected routes.
Supports CORS and request validation.


Technologies: Golang, NGINX, Docker, gRPC (in progress).

Authentication Service

Repository: auth-service
Description: Manages user authentication and authorization, migrated from the original ASP.NET monolith to a standalone Golang service. Uses JWT for secure token-based access.
Key Features:
Issues and verifies JWT tokens for protected routes.
Supports user login, registration, and password reset.
Stores user credentials in MongoDB with encrypted passwords.


Technologies: Golang, MongoDB, JWT, Docker, gRPC (in progress).

Blog Service

Repository: blog-service
Description: Handles blog-related functionality, such as creating, updating, and retrieving posts, comments, and ratings. Isolated from the monolith for independent scaling.
Key Features:
Stores blog data in MongoDB for flexible schema and scalability.
Uses Redis for caching popular posts and comments.
Exposes REST and gRPC endpoints for integration.


Technologies: Golang, MongoDB, Redis, Docker, gRPC (in progress).

User Service

Repository: user-service
Description: Manages user profiles, preferences, and settings, extracted from the monolith to enable modular development.
Key Features:
Stores structured user data in PostgreSQL for relational queries.
Provides endpoints for profile updates and preference management.
Integrates with Authentication Service for user validation.


Technologies: Golang, PostgreSQL, Docker, gRPC (in progress).

Frontend Service

Repository: frontend-service
Description: An Angular-based frontend for user interaction, communicating with the Gateway Service via HTTP.
Key Features:
Responsive UI for browsing blogs, managing user profiles, and authentication.
Integrates JWT tokens for secure API requests.
Deployed as a Docker container for consistency.


Technologies: Angular, TypeScript, Docker, NGINX.

Infrastructure

Repository: infrastructure
Description: Contains configurations for databases, caching, and load balancing, ensuring a cohesive ecosystem.
Key Features:
Docker Compose files for orchestrating MongoDB, PostgreSQL, Redis, and NGINX.
Scripts for initializing database schemas and seeding data.
NGINX configuration for load balancing across Gateway Service instances.


Technologies: Docker, Docker Compose, MongoDB, PostgreSQL, Redis, NGINX.

Technologies
MicroSOA leverages a modern tech stack:

Languages: Golang, JavaScript/TypeScript, C# (legacy ASP.NET).
Frameworks: Angular (frontend), ASP.NET (monolith).
Databases:
MongoDB: Flexible storage for Authentication and Blog Services.
PostgreSQL: Relational storage for User Service.
Redis: Caching and real-time data.


Tools:
Docker: Containerization for services and databases.
NGINX: Load balancing and reverse proxy.
gRPC: High-performance inter-service communication (in progress).
Git: Version control via GitHub.


Protocols: HTTP (transitioning to gRPC), JWT for authentication.

Setup Instructions
To run MicroSOA locally:

Prerequisites:
Install Docker and Docker Compose.
Install Golang for building services.
Ensure ports 8080 (Gateway), 27017 (MongoDB), 5432 (PostgreSQL), and 6379 (Redis) are free.


Clone Repositories:git clone https://github.com/SOA-Team9/gateway-service.git
git clone https://github.com/SOA-Team9/auth-service.git
git clone https://github.com/SOA-Team9/blog-service.git
git clone https://github.com/SOA-Team9/user-service.git
git clone https://github.com/SOA-Team9/frontend-service.git
git clone https://github.com/SOA-Team9/infrastructure.git


Run with Docker Compose:cd infrastructure
docker-compose up --build

This starts all services, databases, and NGINX. The Gateway Service will be accessible at http://localhost:8080.
Access the Frontend:
Open http://localhost:8080 in a browser to interact with the Angular frontend.


Environment Variables:
Configure variables in .env files (see infrastructure/.env.example for templates).
Example: JWT_SECRET, MONGO_URI, POSTGRES_URI, REDIS_HOST.


Build gRPC Services (Optional):
For services using gRPC, generate stubs with:protoc --go_out=. --go-grpc_out=. proto/service.proto


Requires protoc.



Contributing
Contributions are welcome! To contribute:

Fork the repository you want to work on.
Create a feature branch (git checkout -b feature-name).
Commit changes (git commit -m "Add feature").
Push to your fork (git push origin feature-name).
Open a Pull Request with a clear description.

Please follow the Code of Conduct and ensure tests pass before submitting.
Contact
For questions or collaboration:

Email: slobodanobradovic3@gmail.com
LinkedIn: linkedin.com/in/slobodanobradovic
GitHub: github.com/obradovicsl

Thank you for exploring MicroSOA! This project reflects a passion for building scalable, modern systems and is open to feedback and contributions.
