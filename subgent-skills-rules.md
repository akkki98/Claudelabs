# Lab: Using Claude Code Subagents, Skills, and Rules

---

## Lab Title

**Designing and Using Subagents, Skills, and Rules in Claude Code for Structured Development**

---

## Target Audience

* Developers (Java / Spring Boot / Backend)
* AI/LLM Engineers
* DevOps Engineers
* Tech Leads

---

## Lab Duration

**75–90 minutes**

---

## Lab Objectives

By the end of this lab, you will be able to:

* Understand **Subagents**, **Skills**, and **Rules** in Claude Code
* Create specialized subagents for different tasks
* Define reusable skills for development and testing
* Apply rules to enforce consistency and governance
* Combine all three for real-world workflows

---

## Prerequisites

* Basic knowledge of Java & Spring Boot
* Familiarity with testing frameworks (JUnit, Mockito)
* Claude Code access (CLI / IDE integration)
* Sample project (Spring Boot recommended)

---

# Section 1: Concept Overview

---

## What are Subagents?

Subagents are **specialized AI roles** designed for specific tasks.

Examples:

* `dev-agent` → writes application code
* `test-agent` → generates test cases
* `review-agent` → performs code reviews

---

## What are Skills?

Skills are **reusable capabilities** that Claude can invoke.

Examples:

* Generate REST API
* Write unit tests
* Refactor code
* Debug errors

---

## What are Rules?

Rules are **constraints and guidelines** that control behavior.

Examples:

* Follow coding standards
* Enforce architecture patterns
* Prevent unsafe code

---

# Section 2: Creating Subagents

---

## Exercise 1: Create a Development Subagent

Create a folder:

```bash id="sa01"
mkdir .claude
cd .claude
touch dev-agent.md
```

### Add Configuration

```markdown id="sa02"
# Subagent: Dev Agent

## Role
You are a Java Spring Boot developer.

## Responsibilities
- Create REST APIs
- Implement business logic
- Follow layered architecture

## Constraints
- Use Java 17
- Use constructor injection
- Follow clean code principles
```

---

## Exercise 2: Create a Testing Subagent

```bash id="sa03"
touch test-agent.md
```

```markdown id="sa04"
# Subagent: Test Agent

## Role
You are a QA engineer.

## Responsibilities
- Write unit tests
- Validate edge cases
- Ensure high coverage

## Tools
- JUnit 5
- Mockito

## Constraints
- Follow AAA pattern
- Mock dependencies
```

---

## Exercise 3: Create a Code Review Subagent

```bash id="sa05"
touch review-agent.md
```

```markdown id="sa06"
# Subagent: Review Agent

## Role
You are a senior code reviewer.

## Responsibilities
- Review code quality
- Suggest improvements
- Identify bugs

## Rules
- Enforce SOLID principles
- Ensure proper naming conventions
```

---

# Section 3: Creating Skills

---

## Exercise 4: Define Development Skill

```bash id="sk01"
touch skills-dev.md
```

```markdown id="sk02"
# Skill: Generate REST API

## Description
Generates a Spring Boot REST API.

## Input
- Entity name
- Fields

## Output
- Controller
- Service
- Repository

## Rules
- Use DTO pattern
- Include validation
```

---

## Exercise 5: Define Testing Skill

```bash id="sk03"
touch skills-test.md
```

```markdown id="sk04"
# Skill: Generate Unit Tests

## Description
Creates unit tests for service classes.

## Input
- Service class

## Output
- JUnit test class

## Rules
- Use Mockito
- Cover success and failure cases
```

---

## Exercise 6: Define Debugging Skill

```bash id="sk05"
touch skills-debug.md
```

```markdown id="sk06"
# Skill: Debug Code

## Description
Identifies and fixes issues in code.

## Input
- Code snippet

## Output
- Fixed code
- Explanation

## Rules
- Handle null checks
- Avoid breaking functionality
```

---

# Section 4: Defining Rules

---

## Exercise 7: Create Global Rules

```bash id="rl01"
touch rules.md
```

```markdown id="rl02"
# Global Rules

## Coding Standards
- Follow Java naming conventions
- Avoid hardcoded values

## Architecture
- Use Controller → Service → Repository pattern

## Security
- Validate all inputs
- Avoid exposing sensitive data

## Performance
- Avoid unnecessary loops
- Optimize database calls
```

---

## Exercise 8: Add Testing Rules

```markdown id="rl03"
## Testing Rules
- Minimum 80% coverage
- Test all public methods
- Include edge cases
```

---

# Section 5: Using Subagents, Skills, and Rules

---

## Exercise 9: Invoke Dev Subagent

### Prompt

```text id="use01"
Use dev-agent to create a Product REST API with CRUD operations
```

---

## Exercise 10: Invoke Testing Subagent

```text id="use02"
Use test-agent to generate unit tests for ProductService
```

---

## Exercise 11: Invoke Review Subagent

```text id="use03"
Use review-agent to review the ProductController code
```

---

## Exercise 12: Use Skills Explicitly

```text id="use04"
Use the "Generate REST API" skill for an Order entity with fields id, name, price
```

---

## Exercise 13: Combine Everything

```text id="use05"
Using dev-agent, test-agent, skills, and rules, build a complete Order Management API with tests and review feedback
```

---

# Section 6: Real-World Workflow

---

## Scenario: Feature Development Lifecycle

1. **Dev Agent**

   * Generates API

2. **Test Agent**

   * Writes tests

3. **Review Agent**

   * Reviews code

4. **Rules**

   * Ensure consistency

5. **Skills**

   * Accelerate tasks

---

# Best Practices

---

## 1. Keep Subagents Focused

* One responsibility per subagent

---

## 2. Make Skills Reusable

* Avoid duplication
* Keep inputs/outputs clear

---

## 3. Enforce Strong Rules

* Prevent bad code
* Maintain standards

---

## 4. Use Clear Prompts

Bad:

```text id="bp01"
Create API
```

Good:

```text id="bp02"
Use dev-agent and Generate REST API skill to create a Customer API with validation
```

---

# Challenge Exercise

---

## Task

Build a **User Management System** using:

* Subagents:

  * dev-agent
  * test-agent
  * review-agent

* Skills:

  * API generation
  * testing
  * debugging

* Rules:

  * Coding standards
  * testing coverage
  * security

### Prompt

```text id="challenge02"
Using all subagents, skills, and rules, create a complete User Management system with CRUD APIs, unit tests, and code review suggestions
```

---

# Summary

In this lab, you learned:

* How to design **subagents for specialization**
* How to create **skills for reuse**
* How to define **rules for governance**
* How to combine all three for **real-world development workflows**

---

# Next Steps

* Integrate with CI/CD pipelines
* Add security and performance subagents
* Combine with GitHub Copilot for hybrid AI workflows

---
