# Gestion PFA — Backend

REST API backend for the **Gestion PFA** platform, designed to manage the end-of-study project process, including student assignments, project topics, supervision, defense scheduling, and evaluation.

## Features

- **Authentication & Authorization** — User authentication, JWT-based access, role management, and account handling.
- **Student Management** — Student information and academic data management.
- **Project Topics** — Topic creation, validation, availability, and student topic selection.
- **Student Teams** — Team (binôme) management and project assignment workflows.
- **Supervision** — Professor management, availability, and supervision assignments.
- **Defense Scheduling** — Defense sessions, time slots, jury-related management, and scheduling.
- **Results & Evaluation** — Defense results and evaluation criteria management.
- **Dashboards** — Aggregated statistics and role-specific data.
- **Notifications** — Notification management and updates.
- **Messaging** — Chat-related backend endpoints.
- **AI Recommendations** — Personalized project topic recommendations based on student academic performance and similar students' choices, with explanations generated through Ollama.

## Tech Stack

- **Java 17**
- **Spring Boot 3.5.4**
- **Spring Web** — REST API
- **Spring Security** — Security configuration
- **Spring Data JPA / Hibernate** — Persistence
- **MySQL** — Relational database
- **JWT** — Authentication tokens
- **Ollama** — Local LLM-based recommendation explanations
- **Maven** — Dependency management and build
- **Lombok**
- **Apache POI** — Excel document processing
- **iText** — PDF generation

## Architecture

The backend follows a layered architecture:

```text
Controller
    ↓
Service
    ↓
Repository
    ↓
Database
```

- **Controllers** handle HTTP requests and expose API endpoints.
- **Services** implement business logic.
- **Repositories** handle database access.
- **Entities & DTOs** represent persisted data and API payloads.
- **Configuration** handles security, CORS, and application setup.

## Getting Started

### Prerequisites

- Java 17
- Maven
- MySQL
- Ollama (for AI recommendation explanations)

### Database Setup

Create the MySQL database:

```sql
CREATE DATABASE pfa_db;
```

Database initialization data is also provided in `seed.sql`.

### Configuration

Configure the application in:

```text
src/main/resources/application.properties
```

Set your MySQL credentials and other environment-specific properties.

Example:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/pfa_db
spring.datasource.username=root
spring.datasource.password=YOUR_PASSWORD

ollama.url=http://localhost:11434
ollama.model=gemma2:2b

server.port=8085
```

### Run Ollama

Install Ollama and pull the model:

```bash
ollama pull gemma2:2b
```

Ensure Ollama is running locally before using the AI recommendation functionality.

### Run the Application

Using Maven:

```bash
mvn spring-boot:run
```

Or on Windows:

```bash
mvnw.cmd spring-boot:run
```

The backend API will be available at:

```text
http://localhost:8085
```

## Project Structure

```text
src/main/java/tn/enicarthage/projetspring/
├── aspect/         # Performance monitoring
├── config/        # Application, security, CORS, exception handling
├── controller/    # REST API endpoints
├── dto/          # Data transfer objects
├── entity/       # JPA entities
├── repository/   # Data access
└── service/      # Business logic

src/main/resources/
└── application.properties

seed.sql
pom.xml
```

## AI Recommendation System

The recommendation module suggests project topics based on:

- Student academic average
- Topic difficulty
- Choices made by students with similar academic averages

The system ranks available topics and uses **Ollama** to generate a short explanation for each recommendation.

## Database

The application uses MySQL with JPA/Hibernate for persistence.

Main domain entities include:

- Students
- Professors
- Project topics
- Student teams
- Assignments
- Defense sessions
- Defense slots
- Results
- Notifications
- Messages

## API

REST endpoints are organized by domain controllers, including authentication, students, professors, topics, assignments, defenses, results, notifications, dashboards, and recommendations.



---

*Backend developed as part of the Gestion PFA academic project.*
