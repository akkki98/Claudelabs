# Lab: Writing Claude Instructions for Development & Testing

---

## Lab Title

**Creating Effective Claude Instructions for Development and Testing Workflows**

---

## Target Audience

* Developers (Java / Spring Boot / Backend)
* QA Engineers / SDETs
* DevOps Engineers
* Tech Leads

---

## Lab Duration

**60–75 minutes**

---

## Lab Objectives

By the end of this lab, you will be able to:

* Understand what Claude Instructions are
* Write structured instructions for development tasks
* Create reusable instructions for testing workflows
* Guide Claude to follow coding standards and testing practices
* Improve consistency and quality of AI-generated outputs

---

## Prerequisites

* Basic knowledge of Java & Spring Boot
* Familiarity with unit testing (JUnit / Mockito)
* Access to Claude Code (CLI or IDE integration)
* Sample Spring Boot project

---

## What are Claude Instructions?

Claude Instructions are **persistent guidelines** that define how Claude should behave when generating or modifying code.

They help enforce:

* Coding standards
* Architecture patterns
* Testing strategies
* Naming conventions
* Output structure

---

## Lab Setup

Ensure you have a Spring Boot project ready.

Create a folder for instructions:

```bash id="c7t9as"
mkdir claude
cd claude
touch dev-instructions.md
touch test-instructions.md
```

---

# Part 1: Development Instructions

---

## Exercise 1: Create Base Development Instructions

Open `dev-instructions.md` and add:

```markdown id="d1dev01"
# Development Instructions

## Tech Stack
- Java 17
- Spring Boot
- Maven

## Coding Standards
- Follow standard Java naming conventions
- Use constructor-based dependency injection
- Avoid field injection

## Architecture
- Use layered architecture:
  - Controller
  - Service
  - Repository

## API Guidelines
- Use REST principles
- Return proper HTTP status codes
- Use DTOs instead of exposing entities
```

---

## Exercise 2: Add Spring Boot-Specific Rules

Enhance instructions:

```markdown id="d1dev02"
## Spring Boot Guidelines
- Use @RestController for REST endpoints
- Use @Service for business logic
- Use @Repository for data access
- Validate inputs using @Valid

## Error Handling
- Use @ControllerAdvice for global exception handling
- Return meaningful error messages
```

---

## Exercise 3: Add Code Quality Rules

```markdown id="d1dev03"
## Code Quality
- Write clean and readable code
- Add comments only when necessary
- Avoid duplicate code
- Follow SOLID principles

## Logging
- Use SLF4J for logging
- Avoid System.out.println
```

---

## Exercise 4: Use Development Instructions with Claude

### Prompt Example

```text id="devprompt01"
Using the provided development instructions, create a Spring Boot REST API for managing users with CRUD operations.
```

### Expected Outcome

* Structured project
* Proper layering
* Clean, maintainable code

---

# Part 2: Testing Instructions

---

## Exercise 5: Create Base Testing Instructions

Open `test-instructions.md`:

```markdown id="t1test01"
# Testing Instructions

## Testing Framework
- JUnit 5
- Mockito

## General Rules
- Write unit tests for all service classes
- Use descriptive test method names
- Follow Arrange-Act-Assert pattern
```

---

## Exercise 6: Add Unit Testing Guidelines

```markdown id="t1test02"
## Unit Testing
- Mock external dependencies
- Test both success and failure scenarios
- Ensure high code coverage

## Naming Convention
- should<ExpectedBehavior>When<Condition>()
```

---

## Exercise 7: Add Controller Testing Rules

```markdown id="t1test03"
## Controller Testing
- Use MockMvc for API testing
- Validate HTTP status codes
- Validate response body

## Example
- shouldReturn200WhenUserExists
- shouldReturn404WhenUserNotFound
```

---

## Exercise 8: Add Edge Case Testing

```markdown id="t1test04"
## Edge Cases
- Null inputs
- Empty values
- Invalid formats
- Exception scenarios
```

---

## Exercise 9: Use Testing Instructions with Claude

### Prompt Example

```text id="testprompt01"
Using the testing instructions, generate unit tests for the UserService class.
```

### Expected Output

* JUnit test class
* Mockito-based mocks
* Coverage for edge cases

---

# Part 3: Combining Dev + Test Instructions

---

## Exercise 10: Unified Prompt

```text id="combined01"
Using the development and testing instructions, create a complete Spring Boot CRUD application for Product and include unit tests.
```

---

## Expected Outcome

* Clean architecture
* REST APIs
* Proper exception handling
* Fully tested service layer

---

# Best Practices for Claude Instructions

---

## 1. Keep Instructions Structured

Use:

* `#` for title
* `##` for sections
* `###` for rules

---

## 2. Be Explicit

Bad:

```text id="bad01"
Write good code
```

Good:

```text id="good01"
Use constructor injection and follow layered architecture
```

---

## 3. Make Instructions Reusable

* Store in repo
* Share across teams
* Version control them

---

## 4. Separate Concerns

* Dev instructions
* Test instructions
* Security instructions (optional)

---

## Challenge Exercise

Create a new instruction file:

```bash id="challenge01"
touch security-instructions.md
```

Add:

* Input validation rules
* Authentication guidelines
* Secure coding practices

### Prompt

```text id="challengeprompt"
Using development, testing, and security instructions, build a secure REST API for order management.
```

---

# Summary

In this lab, you learned:

* How to write Claude Instructions for development
* How to define testing standards
* How to guide AI for consistent outputs
* How to combine instructions for full application development

---

# Next Steps

* Integrate instructions into CI/CD pipelines
* Use with GitHub Copilot for hybrid workflows
* Expand instructions for:

  * Performance testing
  * Security testing
  * Microservices

---
