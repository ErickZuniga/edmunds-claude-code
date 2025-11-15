---
description: Create a new Java/Spring Boot API endpoint with validation, error handling, and best practices
model: claude-sonnet-4-5
---

Create a new Java 21/Spring Boot API endpoint following modern best practices.

## Requirements

API Endpoint: $ARGUMENTS

## Implementation Guidelines

### 1. **Spring Boot 3+**
- Use Spring Web for REST controllers.
- Leverage dependency injection for services and repositories.
- Use `application.properties` or `application.yml` for configuration.

### 2. **Validation**
- Use **Jakarta Bean Validation** (`@Valid` annotation).
- Create DTOs (Data Transfer Objects) for request bodies with validation annotations (`@NotNull`, `@Size`, etc.).
- Return clear validation error messages (Spring's default handler is a good start).

### 3. **Error Handling**
- Use `@ControllerAdvice` for global exception handling.
- Create custom exception classes for specific error scenarios.
- Return a consistent error response format.
- Use appropriate HTTP status codes.

### 4. **Java 21**
- Use modern Java features like records for immutable DTOs.
- Use the Stream API for data manipulation.
- Follow standard Java naming conventions.

### 5. **Security**
- Use **Spring Security** for authentication and authorization.
- Secure endpoints with method-level security (`@PreAuthorize`) or security filter chains.
- Protect against CSRF, XSS, and other common vulnerabilities.

### 6. **Response Format**

**Success**
```json
{
  "data": { ... },
  "success": true
}
```

**Error**
```json
{
  "error": "Error message",
  "details": { ... },
  "success": false
}
```

## Code Structure

Generate the following components for a complete API endpoint:

1.  **Controller**: The `@RestController` class with endpoint mappings (`@GetMapping`, `@PostMapping`, etc.).
2.  **Service**: The `@Service` class containing the business logic.
3.  **Repository**: The Spring Data JPA `@Repository` interface for database operations.
4.  **Entity**: The JPA `@Entity` class representing the database table.
5.  **DTOs**: Java records for request and response objects with validation.
6.  **Global Exception Handler**: A `@ControllerAdvice` class for handling exceptions.
7.  **Example Usage**: A `curl` or Postman example for calling the new endpoint.

## Best Practices to Follow

-   **Separation of Concerns**: Keep logic separated between controllers, services, and repositories.
-   **Dependency Injection**: Use constructor injection.
-   **DTO Pattern**: Use DTOs to decouple the API layer from the data layer.
-   **Proper HTTP Status Codes**: Use meaningful status codes (200, 201, 400, 401, 404, 500).
-   **Logging**: Use a logging framework like SLF4J for logging requests, errors, and important events.
-   **Testing**: Include unit tests for the service layer and integration tests for the controller.

Generate production-ready code that I can immediately use in my Spring Boot project.
