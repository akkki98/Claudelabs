# Lab: Interacting with Claude Code for Java Spring Boot

## Lab Title

**Using Claude Code to Assist Development in a Java Spring Boot Application**

---

## Target Audience

* Java Developers
* Spring Boot Developers
* Backend Engineers
* DevOps Engineers

---

## Lab Duration

**60 minutes**

---

## Lab Objectives

By the end of this lab, you will be able to:

* Understand how to interact with Claude Code in a development workflow
* Use Claude Code for code generation, explanation, and debugging
* Apply Claude Code to enhance a Spring Boot application
* Use structured prompts for better AI-assisted development

---

## Prerequisites

* Java 17 or above
* Maven or Gradle installed
* Basic knowledge of Spring Boot
* A code editor (VS Code / IntelliJ IDEA)
* Access to Claude Code (CLI or integrated tool)

---

## Lab Setup

### Step 1: Create a Spring Boot Project

You can create a project using Spring Initializr:

* Project: Maven
* Language: Java
* Dependencies:

  * Spring Web
  * Spring Boot DevTools

Or use CLI:

```bash
curl https://start.spring.io/starter.zip \
  -d dependencies=web \
  -d name=demo \
  -o demo.zip
unzip demo.zip
cd demo
```

---

### Step 2: Open Project in IDE

Open the project in your preferred IDE:

```bash
code .
```

---

### Step 3: Run the Application

```bash
./mvnw spring-boot:run
```

Verify:

```
http://localhost:8080
```

---

## Exercise 1: Generate a REST Controller using Claude Code

### Prompt

Use Claude Code with the following prompt:

```
Create a Spring Boot REST controller with endpoint /hello that returns "Hello, World!"
```

### Expected Output

* A `HelloController.java` file
* A GET endpoint `/hello`

### Sample Code

```java
@RestController
public class HelloController {

    @GetMapping("/hello")
    public String hello() {
        return "Hello, World!";
    }
}
```

---

## Exercise 2: Enhance Controller with Query Parameters

### Prompt

```
Update the controller to accept a query parameter 'name' and return "Hello, <name>"
```

### Expected Behavior

```
GET /hello?name=Akshay
Response: Hello, Akshay
```

---

## Exercise 3: Ask Claude Code to Explain Code

### Prompt

```
Explain this Spring Boot controller in simple terms
```

### Learning Outcome

* Understand annotations like `@RestController`, `@GetMapping`
* Understand request handling in Spring Boot

---

## Exercise 4: Add Service Layer Using Claude Code

### Prompt

```
Refactor the controller to use a service class for business logic
```

### Expected Structure

```
controller/
service/
```

### Example

```java
@Service
public class HelloService {
    public String greet(String name) {
        return "Hello, " + name;
    }
}
```

---

## Exercise 5: Error Handling with Claude Code

### Prompt

```
Add exception handling if name is null or empty using @ControllerAdvice
```

### Learning Outcome

* Global exception handling
* Clean API responses

---

## Exercise 6: Generate Unit Tests

### Prompt

```
Write JUnit tests for the HelloController
```

### Expected

* Test class with mock MVC or unit tests
* Coverage for endpoint behavior

---

## Exercise 7: Debugging with Claude Code

### Scenario

Introduce a bug:

```java
return "Hello " + name.toUpperCase();
```

### Prompt

```
Fix potential NullPointerException in this code
```

### Learning Outcome

* Defensive coding
* Null checks

---

## Exercise 8: Generate API Documentation

### Prompt

```
Add Swagger/OpenAPI documentation to this Spring Boot project
```

### Expected Output

* Swagger dependency
* API docs at `/swagger-ui.html`

---

## Best Practices for Using Claude Code

### 1. Be Specific

Bad:

```
Improve code
```

Good:

```
Refactor this controller to follow clean architecture principles
```

---

### 2. Provide Context

```
This is a Spring Boot application. Optimize this service for performance.
```

---

### 3. Iterate Prompts

* Start simple
* Refine output
* Ask follow-up questions

---

### 4. Use for Multiple Tasks

* Code generation
* Refactoring
* Debugging
* Documentation
* Testing

---

## Challenge Exercise

Use Claude Code to:

* Add a new endpoint `/goodbye`
* Return JSON response:

```json
{
  "message": "Goodbye, Akshay"
}
```

* Include proper HTTP status codes

---

## Summary

In this lab, you learned how to:

* Use Claude Code effectively in a Spring Boot project
* Generate and refactor code
* Debug and test applications
* Improve productivity with AI-assisted development

---

## Next Steps

* Integrate Claude Code into CI/CD workflows
* Use with microservices architecture
* Combine with GitHub Copilot for hybrid AI workflows

---
