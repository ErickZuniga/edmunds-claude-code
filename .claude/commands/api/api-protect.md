---
description: Add Spring Security-based authentication, authorization, and validation to a Java API endpoint
model: claude-sonnet-4-5
---

Add comprehensive security, authentication, and authorization to the specified Spring Boot API endpoint using Spring Security.

## Target API Route

$ARGUMENTS

## Security Layers to Implement

### 1. **Authentication** (Who are you?)
-   Verify user identity using mechanisms like JWT, OAuth2, or session-based authentication.
-   Implement `UserDetailsService` to load user-specific data.
-   Configure authentication providers in the Spring Security filter chain.

### 2. **Authorization** (What can you do?)
-   Implement Role-Based Access Control (RBAC).
-   Use method-level security with `@PreAuthorize` or `@Secured`.
-   Configure authorization rules in the security filter chain (e.g., `http.authorizeHttpRequests`).

### 3. **Input Validation**
-   Use Jakarta Bean Validation (`@Valid`) on DTOs in the controller layer.
-   Protect against injection attacks by using prepared statements (default in Spring Data JPA).
-   Sanitize outputs to prevent XSS if serving HTML content.

### 4. **Rate Limiting**
-   Implement rate limiting to prevent abuse, possibly using a library like Bucket4j.
-   Apply limits on a per-user or per-IP basis.

### 5. **CORS**
-   Configure CORS globally or on a per-controller basis to control cross-origin requests.
-   Whitelist allowed origins, methods, and headers.

## Implementation Approach using Spring Security

### 1. **Security Configuration**
-   Create a `@Configuration` class that extends `WebSecurityConfigurerAdapter` (or defines a `SecurityFilterChain` bean in modern Spring Security).
-   Define password encoding, authentication manager, and the security filter chain.

### 2. **JWT-based Authentication (Common for REST APIs)**
-   Generate a JWT upon successful login.
-   Include user roles/permissions as claims in the token.
-   Create a filter to validate the JWT on incoming requests and set the `Authentication` in the `SecurityContextHolder`.

### 3. **Method-Level Security**
-   Enable global method security with `@EnableGlobalMethodSecurity(prePostEnabled = true)`.
-   Use `@PreAuthorize("hasRole('ADMIN')")` or `@PreAuthorize("hasAuthority('READ_PRIVILEGE')")` on controller methods.

## Security Checklist

**Authentication**
-   [ ] Securely store passwords using a strong hashing algorithm (e.g., BCrypt).
-   [ ] Handle invalid/expired tokens with a 401 Unauthorized response.
-   [ ] Implement refresh token logic for better security.

**Authorization**
-   [ ] Use roles and authorities to enforce the principle of least privilege.
-   [ ] Return a 403 Forbidden response for authorization failures.
-   [ ] Log authorization failures for security monitoring.

**Input Validation**
-   [ ] Validate all incoming DTOs with `@Valid`.
-   [ ] Limit payload sizes to prevent resource exhaustion.

**Error Handling**
-   [ ] Create a custom `AuthenticationEntryPoint` to handle authentication errors.
-   [ ] Create a custom `AccessDeniedHandler` to handle authorization errors.
-   [ ] Avoid exposing sensitive security details in error messages.

## What to Generate

1.  **Updated Controller**: The controller method annotated with security rules.
2.  **Security Configuration**: A `SecurityFilterChain` bean with authentication and authorization rules.
3.  **JWT Utilities**: (If applicable) Classes for generating and validating JWTs.
4.  **Custom Filter**: A custom filter for processing authentication tokens.
5.  **User Details Service**: An implementation of `UserDetailsService`.
6.  **Usage Examples**: `curl` examples showing both authenticated and unauthenticated requests.

Generate production-ready, secure code that follows modern Spring Security best practices.
