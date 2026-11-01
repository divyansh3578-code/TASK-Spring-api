# Task API

A basic Spring Boot 3 REST backend (CRUD for tasks) with validation, error handling, an in-memory H2 database, and tests.

**Stack:** Java 17, Spring Boot 3.3, Spring Web, Spring Data JPA, Bean Validation, H2, Maven

## Run

```bash
mvn spring-boot:run
```

The API starts on `http://localhost:8080`.

## Test

```bash
mvn test
```

## Endpoints

| Method | URL                | Description                    |
|--------|--------------------|--------------------------------|
| GET    | `/api/tasks`       | List tasks (`?completed=true`) |
| GET    | `/api/tasks/{id}`  | Get one task                   |
| POST   | `/api/tasks`       | Create a task                  |
| PUT    | `/api/tasks/{id}`  | Update a task                  |
| DELETE | `/api/tasks/{id}`  | Delete a task                  |

### Example

```bash
curl -X POST http://localhost:8080/api/tasks \
  -H "Content-Type: application/json" \
  -d '{"title":"Learn Spring Boot","description":"Build a REST API","completed":false}'

curl http://localhost:8080/api/tasks
```

## Project structure

```
src/main/java/com/example/taskapi
├── controller/   REST endpoints
├── service/      Business logic
├── repository/   Spring Data JPA repository
├── model/        JPA entity
└── exception/    Custom exception + global handler
```

## Switching to MySQL/PostgreSQL

Replace the H2 dependency in `pom.xml` with your database driver and update the `spring.datasource.*` properties in `application.properties`.
