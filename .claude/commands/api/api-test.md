---
description: Generate comprehensive tests for a Spring Boot API endpoint
model: claude-sonnet-4-5
---

Generate comprehensive API tests for the specified Spring Boot endpoint.

## Target

$ARGUMENTS

## Test Strategy for Spring Boot

Create practical, maintainable tests using modern Java testing frameworks:

### 1. **Testing Approach**
- **Unit Tests**: For service layer and business logic (using Mockito).
- **Integration Tests**: For the full API flow, from controller to database (using `@SpringBootTest`).
- **Edge Case Coverage**: Test boundary conditions and unexpected inputs.
- **Error Scenario Testing**: Verify correct error handling and HTTP status codes.

### 2. **Tools**
- **JUnit 5**: The standard for Java testing.
- **Mockito**: For mocking dependencies in unit tests.
- **Spring Boot Test**: For integration testing with a running application context.
- **MockMvc**: For testing controllers without a running server.
- **AssertJ**: For fluent and readable assertions.
- **Testcontainers**: For running a real PostgreSQL database in a Docker container during tests.

### 3. **Test Coverage**

**Happy Paths**
- Valid inputs return expected results and a 2xx status code.
- Correct response structure and data.

**Error Paths**
- Invalid input triggers validation and returns a 400 status code.
- Unauthorized requests return a 401/403 status code.
- Requests for non-existent resources return a 404 status code.
- Server-side errors result in a 500 status code.

**Edge Cases**
- Empty request bodies.
- Malformed JSON.
- Large payloads.
- Special characters and potential injection attacks.

### 4. **Test Structure**

```java
import org.junit.jupiter.api.Test;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.web.servlet.AutoConfigureMockMvc;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.test.web.servlet.MockMvc;

import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.*;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.*;

@SpringBootTest
@AutoConfigureMockMvc
class MyControllerIntegrationTest {

    @Autowired
    private MockMvc mockMvc;

    @Test
    void testSuccessCase() throws Exception {
        mockMvc.perform(get("/api/resource"))
               .andExpect(status().isOk());
    }

    @Test
    void testValidationError() throws Exception {
        mockMvc.perform(post("/api/resource").content("{}"))
               .andExpect(status().isBadRequest());
    }
}
```

### 5. **What to Generate**

1.  **Integration Test File**: A complete `@SpringBootTest` class for the controller.
2.  **Unit Test File**: A JUnit 5 test class for the service layer, using Mockito to mock the repository.
3.  **Mock Data**: Realistic test data and fixtures.
4.  **Setup/Teardown**: Use `@BeforeEach` and `@AfterEach` for test setup and cleanup.
5.  **Test Profile**: An `application-test.properties` file for test-specific configuration (e.g., in-memory database or Testcontainers).

## Key Testing Principles

-   **Test Behavior, Not Implementation**: Focus on what the API does, not how it does it.
-   **Clear, Descriptive Test Names**: Use names that clearly state the test's purpose.
-   **Arrange-Act-Assert Pattern**: Structure tests for clarity.
-   **Independent Tests**: Ensure tests can run in any order without affecting each other.
-   **Use Test Profiles**: Separate test configuration from production configuration.

Generate production-ready tests that I can run immediately with `./mvnw test` or `./gradlew test`.
