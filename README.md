# Library Management System

A full-stack library management application with a **Spring Boot REST API** and a **React** frontend. Manage books, authors, categories, and users, and handle borrow/return operations.

## Features

- **Books** — Create, list, view, borrow, and return
- **Authors** — Create, list, and view books by author
- **Categories** — Create and list categories
- **Users** — Full CRUD for library members
- **Database options** — MySQL (local or Docker) or H2 in-memory for quick testing

## Tech Stack

| Layer     | Technology                              |
|-----------|-----------------------------------------|
| Backend   | Java 17, Spring Boot 3, Spring Data JPA |
| Database  | MySQL 8 (Docker) / H2 (dev profile)     |
| Frontend  | React 18, Vite                          |

## Prerequisites

- Java 17+
- Maven (or IntelliJ bundled Maven)
- Node.js 18+ (for frontend)
- Docker Desktop (optional, for MySQL via Docker Compose)

## Getting Started

### 1. Database (choose one)

**Option A — Docker MySQL (recommended)**

```bash
docker compose up -d
```

Run the API in IntelliJ with active profile: **`docker`**

**Option B — H2 in-memory (no MySQL needed)**

Run the API with IntelliJ profile: **`h2`**

**Option C — Local MySQL**

Install MySQL, create database `library_db`, and use default `application.properties`.

### 2. Run the backend

```bash
mvn spring-boot:run
```

API runs at: **http://localhost:8080**

### 3. Run the frontend

```bash
cd frontend
npm install
npm run dev
```

Frontend runs at: **http://localhost:5173**

Copy `frontend/.env.example` to `frontend/.env` if needed:

```
VITE_API_BASE=http://localhost:8080
```

## API Endpoints

| Resource   | Endpoints                                                                                          |
|------------|----------------------------------------------------------------------------------------------------|
| Books      | `GET/POST /books`, `GET /books/{id}`, `PUT /books/{id}/borrow/{userId}`, `PUT /books/{id}/return` |
| Authors    | `GET/POST /authors`, `GET /authors/{id}/books`                                                     |
| Categories | `GET/POST /categories`                                                                             |
| Users      | `GET/POST /users`, `GET/PUT/DELETE /users/{id}`                                                    |

## Project Structure

```
├── src/main/java/com/library/   # Spring Boot API
├── frontend/                    # React + Vite UI
├── docker-compose.yml           # MySQL for local dev
└── pom.xml
```

## Author

**Aniketkundal9172** — [GitHub](https://github.com/Aniketkundal9172)
