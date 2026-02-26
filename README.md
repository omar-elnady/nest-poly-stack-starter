<div align="center">
  <h1>🚀 Polyglot NestJS General Boilerplate</h1>
  <p>A robust, scalable, and enterprise-ready backend boilerplate powered by NestJS v11 and a polyglot data stack.</p>

  <!-- Badges -->
  <p>
    <img src="https://img.shields.io/badge/NestJS-v11-E0234E?style=for-the-badge&logo=nestjs&logoColor=white" alt="NestJS">
    <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript">
    <img src="https://img.shields.io/badge/pnpm-F69220?style=for-the-badge&logo=pnpm&logoColor=white" alt="pnpm">
    <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL">
    <img src="https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white" alt="Prisma">
    <img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white" alt="Redis">
    <img src="https://img.shields.io/badge/Neo4j-018BFF?style=for-the-badge&logo=neo4j&logoColor=white" alt="Neo4j">
    <img src="https://img.shields.io/badge/Elasticsearch-005571?style=for-the-badge&logo=elasticsearch&logoColor=white" alt="Elasticsearch">
    <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker">
  </p>
</div>

<br />

## 📖 Overview

This is a high-performance, general-purpose backend boilerplate designed to accelerate development for complex applications. By leveraging a polyglot architecture, it ensures the right database technology is used for specific data access patterns (Relational, Graph, Search, Key-Value/Caching). Containerized with Docker Compose, it provides an out-of-the-box infrastructure setup perfect for production scalability.

---

## 🛠️ Tech Stack Table

| Technology                                                                       | Purpose                                                                              |
| -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| **[NestJS (v11)](https://nestjs.com/)**                                          | Core backend framework for building scalable server-side applications.               |
| **[TypeScript](https://www.typescriptlang.org/)**                                | Strongly-typed programming language.                                                 |
| **[pnpm](https://pnpm.io/)**                                                     | Fast, disk space efficient package manager.                                          |
| **[PostgreSQL](https://www.postgresql.org/) & [Prisma](https://www.prisma.io/)** | Primary relational database alongside Prisma as the modern ORM.                      |
| **[Redis](https://redis.io/)**                                                   | High-performance caching layer and message broker for queues.                        |
| **[Neo4j](https://neo4j.com/)**                                                  | Graph database optimized for highly connected data and complex relationship queries. |
| **[Elasticsearch](https://www.elastic.co/)**                                     | Distributed search and analytics engine for advanced full-text search.               |
| **[Winston](https://github.com/winstonjs/winston)**                              | Advanced structured logging system with daily file rotation.                         |
| **[Docker Compose](https://docs.docker.com/compose/)**                           | Container orchestration for unified local infrastructure deployment.                 |

---

## 📋 Prerequisites

Before you begin, ensure you have the following installed on your machine:

- **Node.js** (v18 or higher recommended)
- **pnpm** (`npm install -g pnpm`)
- **Docker** & **Docker Compose**

---

## 🚀 Getting Started

Follow these step-by-step instructions to get the project up and running locally:

**1. Clone the repository:**

```bash
git clone https://github.com/omar-elnady/nest-poly-stack-starter
cd nest-poly-stack-starter
```

**2. Install dependencies using pnpm:**

```bash
pnpm install
```

**3. Setup environment variables:**

```bash
cp .env.example .env
```

_(Make sure to update the `.env` file with any necessary distinct credentials for your local setup)_

**4. Spin up the infrastructure (Databases, Cache, SearchEngine):**

```bash
docker compose up -d
```

**5. Apply database migrations (Prisma):**

```bash
pnpm prisma migrate dev
```

**6. Start the development server:**

```bash
pnpm start:dev
```

The application should now be running locally, typically on `http://localhost:3000`.

---

## 📂 Project Structure

A clean, modular architectural representation of the `src/` directory:

```text
src/
├── common/             # Global guards, interceptors, decorators, and filters
├── config/             # Application configuration and environment variables
├── modules/            # Domain-specific feature modules
│   ├── auth/           # Authentication and authorization logic
│   ├── users/          # User management utilizing PostgreSQL
│   ├── graph/          # Modules interacting with Neo4j
│   └── search/         # Modules integrating with Elasticsearch
├── providers/          # Third-party integrations & database connections
│   ├── prisma/         # Prisma service and schemas
│   ├── redis/          # Redis caching and queue configurations
│   ├── neo4j/          # Neo4j driver configurations
│   └── elasticsearch/  # Elasticsearch client configurations
├── utils/              # Helper functions and utilities
│   └── logger/         # Winston logger configuration
├── app.module.ts       # Root module of the application
└── main.ts             # Application entry point
```

---

## 📝 Logging System

This project is configured with a robust custom logger leveraging **Winston**.

- **Console Logging:** During development, Winston outputs colorful, aesthetically pleasing, formatted logs to the console for real-time tracking of requests, queries, and errors.
- **File Logging (Daily Rotate):** Using the `winston-daily-rotate-file` transport, logs are automatically persisted gracefully to the `/logs` directory at the project root. Logs are typically separated into:
  - `error-%DATE%.log`: Exclusive collection for error tracking.
  - `combined-%DATE%.log`: Full aggregation of all log levels (info, warn, error).

Old log files are automatically compressed or deleted based on standard retention configurations, ensuring optimal disk space usage.

---

## 🔒 License

This project is **UNLICENSED / Private**. All rights reserved. Do not distribute, modify, or copy without explicit permission from the original author.
