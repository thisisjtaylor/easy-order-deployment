# Easy Order — Deployment & CI/CD

A containerized deployment and continuous integration/continuous delivery (CI/CD) solution for the **Easy Order** full-stack application, built using **Docker, Docker Compose, and Jenkins**.

This repository manages the infrastructure and deployment configuration required to build, test, and run the Easy Order application.

Easy Order is a retail order management system designed to replace handwritten order tickets with a centralized digital platform for creating, managing, searching, and tracking customer orders.

The deployment environment integrates three primary application components:

- **Frontend:** React and JavaScript
- **Backend:** Java and Spring Boot
- **Database:** MySQL

The project demonstrates practical experience with containerization, automated build pipelines, environment configuration, service orchestration, and deployment verification.

---

## Technology Stack

| Technology | Purpose |
|---|---|
| Docker | Containerization of application services |
| Docker Compose | Multi-container orchestration |
| Jenkins | CI/CD pipeline automation |
| Git | Source code version control |
| GitHub | Repository hosting and source code integration |
| Maven | Backend build and automated testing |
| npm | Frontend dependency management and builds |
| Java / Spring Boot | Backend REST API |
| React / Vite | Frontend application |
| MySQL | Relational database |

---

## System Architecture

Easy Order uses a containerized architecture in which the frontend, backend, and database run as separate services.

Docker Compose manages service configuration, networking, dependencies, and persistent storage.

### Application Architecture

```text
                     User Browser
                          |
                          v
                  React Frontend
                   Docker Container
                          |
                          | HTTP / REST
                          v
                 Spring Boot Backend
                   Docker Container
                          |
                          | JDBC / JPA
                          v
                    MySQL Database
                   Docker Container
                          |
                          v
                   Docker Volume
                 Persistent Storage
```

### Deployment Architecture

```text
                      GitHub
                         |
          +--------------+--------------+
          |              |              |
          v              v              v
       Frontend        Backend       Deployment
       Repository      Repository    Repository
          |              |              |
          +--------------+--------------+
                         |
                         v
                  Jenkins Pipeline
                         |
                         v
                 Build & Test Code
                         |
                         v
                 Docker Image Build
                         |
                         v
                   Docker Compose
                         |
             +-----------+-----------+
             |           |           |
             v           v           v
          Frontend     Backend      MySQL
          Container    Container   Container
```

This architecture separates application components while allowing them to communicate through Docker networking.

---

## Repository Structure

The deployment repository is organized around Docker Compose configuration, environment variables, and Jenkins pipeline automation.

```text
easy-order-deployment/
│
├── compose.yaml
├── Jenkinsfile
├── .env.example
├── .gitignore
└── README.md
```

**Note:** The Compose file may be named `docker-compose.yml` or `compose.yml` depending on the current repository configuration.

### File Descriptions

| File | Purpose |
|---|---|
| `compose.yaml` | Defines application containers, networking, volumes,
