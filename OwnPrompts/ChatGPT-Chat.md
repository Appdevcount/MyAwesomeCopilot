Excellent — you’re building an **AI-augmented Tech Lead workflow** using **GitHub Copilot Chat (GHCP)** in VS Code.
Let’s design a **complete set of detailed prompts, instructions, and file organization** for your use case — covering:

✅ **Code Generation**
✅ **Code Review (including Security & Architecture)**
✅ **Test Case Generation (xUnit)**
✅ **Tech Stack: .NET (C#), React, Angular, Terraform, SQL Server, CI/CD, Azure, Python**

Below is a **Tech Lead–level GHCP prompt system** — structured for **precision, consistency, and repeatability**.

---

## 🧠 1. GHCP Workspace Setup & File Structure

> Create a consistent folder structure in your repo to help GHCP context-switch efficiently.

```plaintext
/.github/
 ├── copilot/
 │    ├── CODEGEN_PROMPTS.md
 │    ├── REVIEW_PROMPTS.md
 │    ├── TESTCASE_PROMPTS.md
 │    ├── SECURITY_PROMPTS.md
 │    ├── ARCHITECTURE_PROMPTS.md
 │    └── INSTRUCTIONS.md
/docs/
 ├── ARCHITECTURE_DECISIONS.md
 ├── CODING_STANDARDS.md
 ├── API_CONTRACTS.md
 └── DEPLOYMENT_GUIDE.md
/src/
 ├── backend/ (C# API)
 ├── frontend-react/
 ├── frontend-angular/
 ├── infra/ (Terraform)
 └── scripts/ (Python utilities)
```

This structure helps GHCP interpret codebase purposefully when using “`@workspace`” context.

---

## ⚙️ 2. Universal Prompt Instructions (Best Practices)

Include this section in `/github/copilot/INSTRUCTIONS.md` and remind GHCP in chat using:

> **Prompt prefix:**
> “Follow the Tech Lead Copilot process and instruction file before execution.”

**Content:**

```
# GHCP Instructions for Tech Lead Use

1. Always analyze the context before responding (review architecture, language, or project structure).
2. Follow Clean Architecture and SOLID principles in all C# and React/Angular code.
3. Ensure security and performance are validated in all output.
4. Follow Microsoft and OWASP best practices for Azure-hosted apps.
5. Suggest and document assumptions in comments or markdown if context is partial.
6. For all C# code, generate async-safe, thread-safe, and testable components.
7. For frontend code (React/Angular), follow component reusability and state management best practices.
8. Use dependency injection, minimal coupling, and error handling.
9. Generate unit tests using xUnit or Jest with clear Arrange-Act-Assert sections.
10. When reviewing, classify feedback as: 
   - `Code Quality`
   - `Security`
   - `Performance`
   - `Architecture`
   - `Testing`
11. Provide references or code links (like `.cs` or `.tsx` file context) wherever applicable.
```

---

## 🚀 3. Code Generation Prompts (`CODEGEN_PROMPTS.md`)

### 🧩 Backend (C# API)

> **Prompt:**

```
You are a senior .NET architect. 
Generate a C# API component for {FeatureName} using Clean Architecture with layers:
- Domain
- Application
- Infrastructure
- API

Requirements:
- Follow SOLID principles
- Use dependency injection
- Async and cancellation tokens
- Include DTOs and FluentValidation validators
- Data access using EF Core (SQL Server)
- Add repository and service interfaces
- Add logging (Serilog) and telemetry hooks (OpenTelemetry)
- Add meaningful XML and inline comments
- Prepare for xUnit test coverage
```

📘 **Optional addition:**

> “Integrate with Azure Blob/Cosmos/Key Vault based on need. Use proper configuration patterns.”

---

### 🧠 Frontend (ReactJS / Angular)

> **Prompt:**

```
You are a senior frontend architect.
Generate a {React or Angular} component for {FeatureName}.

Follow:
- Clean component structure
- TypeScript with strong typing
- State management with Redux (React) or NGXS (Angular)
- API integration via Axios/HttpClient
- Error boundary and loading state
- Unit tests (Jest/Karma)
- Accessibility (ARIA) and responsive design

Ensure:
- Component is reusable
- Naming aligns with feature folder structure
- Comments explain props and logic
```

---

### 🌍 Infrastructure (Terraform / Azure)

> **Prompt:**

```
You are a DevOps architect.
Generate Terraform IaC for {AzureResource} with:
- Modules and variable reuse
- Environment separation (dev/test/prod)
- Secure naming and tagging conventions
- Use remote backend in Azure Storage
- Output sensitive values securely
- Apply Azure RBAC and Managed Identity

Add CI/CD YAML snippet for deployment via GitHub Actions or Azure DevOps.
```

---

## 🔍 4. Code Review Prompts (`REVIEW_PROMPTS.md`)

> **Prompt:**

```
You are a technical lead reviewing code for best practices.

Perform a detailed review of the following:
- Code Quality
- Security and OWASP compliance
- Performance
- Architectural consistency (Clean Architecture / SOLID)
- Readability and maintainability

Provide:
- Summary table of issues by category
- Recommended improvements with code snippets
- Risk assessment (Low, Medium, High)
- Optional: Suggest refactoring paths or design patterns
```

---

## 🧑‍💻 5. Security Review Prompts (`SECURITY_PROMPTS.md`)

> **Prompt:**

```
Perform a secure code review for {file or feature}.
Check for:
- Input validation and sanitization
- SQL injection or command injection
- Authentication & Authorization (Azure AD, B2C)
- Secrets management (KeyVault)
- Logging of sensitive info
- Proper use of HTTPS, CORS, CSRF
- API exposure via APIM
- React/Angular XSS & token storage

Provide:
- Vulnerability list
- Risk level and mitigation steps
```

---

## 🧱 6. Architecture Review Prompts (`ARCHITECTURE_PROMPTS.md`)

> **Prompt:**

```
You are an enterprise solution architect.
Review the architecture of {Feature/ServiceName}.

Evaluate:
- Alignment with Clean Architecture
- Domain and Application layer separation
- Reusability and scalability
- Event-driven or CQRS patterns if applicable
- Azure resource design (App Services, APIM, KeyVault, Service Bus)
- CI/CD design (GitHub Actions / ADO)
- Observability and monitoring strategy

Deliver:
- Architecture score (1–5) for each category
- Recommendations with reasoning
- Optional diagram structure (mermaid markdown)
```

---

## 🧪 7. Test Case Generation (xUnit) (`TESTCASE_PROMPTS.md`)

> **Prompt:**

```
Generate xUnit test cases for {C# class or feature}.
Follow Arrange-Act-Assert pattern.
Include:
- Positive and negative scenarios
- Validation and exception testing
- Mocking with Moq
- Dependency injection setup
- Edge case coverage

Ensure test naming convention: MethodName_Scenario_ExpectedResult
Output should include sample test file structure and coverage focus.
```

---

## 🧰 8. CI/CD & Automation Prompts

> **Prompt:**

```
You are a DevOps lead. 
Generate a GitHub Actions YAML pipeline for {.NET / React / Terraform / SQL} project.

Include:
- Build, test, lint, and deploy stages
- Security scan (CodeQL, OWASP Dependency Check)
- Publish artifacts to Azure App Service or Container Registry
- Environment-based secret usage
- Branch policy and PR validation

Follow principle: Fail fast, deploy safe.
```

---

## 🧩 9. Python Utility or Scripting Prompts

> **Prompt:**

```
Generate a Python script for {automation or data task}.
Follow:
- PEP8 standards
- Secure and modular code
- Logging and exception handling
- Option for CLI parameters
- Integration with Azure SDK or REST APIs
- Include pytest unit tests
```

---

## 🧠 10. Prompt Usage Technique (How to Interact with GHCP)

In VS Code GHCP Chat:

1. **Contextual mode** –
   Select a file → open GHCP → type:

   > `@workspace Review architecture of this service based on ARCHITECTURE_PROMPTS.md`

2. **Inline mode** –
   Highlight code →

   > `Explain performance or security issues in this block`

3. **Multi-file reasoning** –

   > `@workspace Review consistency between controller, service, and repository layers`

4. **Iterative refinement** –
   After first output, ask:

   > “Refine with Clean Architecture principle and ensure async-safe design.”

---

## 🏁 11. Bonus: Custom Command Aliases (Optional)

Add in `.copilot-instructions` or use VS Code snippets:

```plaintext
/codegen → uses CODEGEN_PROMPTS.md  
/review → uses REVIEW_PROMPTS.md  
/archreview → uses ARCHITECTURE_PROMPTS.md  
/secure → uses SECURITY_PROMPTS.md  
/tests → uses TESTCASE_PROMPTS.md
```

---

Would you like me to generate a **ready-to-commit `/github/copilot/` folder with all these markdown prompt files**, formatted and structured for direct import into your repo (so GHCP can detect and use them)?
It’ll contain 6 files with all these prompts neatly organized.
Perfect — let’s elevate this to a **Tech Lead / Solution Architect–grade GitHub Copilot (GHCP) prompt framework**, designed for **enterprise-scale engineering environments** where quality, security, and consistency are non-negotiable.

This version is **mature, structured, and opinionated**, following **architectural governance**, **AI-assisted engineering discipline**, and **copilot-first development practices** used by senior tech leads at Microsoft and enterprise DevOps teams.

---

# 🧭 GHCP Enterprise Prompt System — Tech Lead Framework

**Purpose:**
To establish a **repeatable AI-assisted engineering process** for design, development, code review, and testing across a modern multi-stack project (C#, React, Angular, Terraform, SQL Server, CI/CD, Azure, Python).

---

## 📁 1. Recommended Repository Structure

```
.github/
 └── copilot/
      ├── INSTRUCTIONS.md
      ├── CODEGEN_PROMPTS.md
      ├── REVIEW_PROMPTS.md
      ├── ARCHITECTURE_PROMPTS.md
      ├── SECURITY_PROMPTS.md
      ├── TESTCASE_PROMPTS.md
      ├── CICD_PROMPTS.md
      └── PYTHON_AUTOMATION_PROMPTS.md

/docs/
 ├── ARCHITECTURE_DECISIONS.md     # ADRs
 ├── CODING_GUIDELINES.md
 ├── SECURITY_STANDARDS.md
 ├── DEPLOYMENT_STANDARDS.md
 └── TESTING_STRATEGY.md

/src/
 ├── backend/                      # C# Clean Architecture API
 ├── frontend-react/               # ReactJS app
 ├── frontend-angular/             # Angular app
 ├── infra/                        # Terraform Infrastructure as Code
 └── scripts/                      # Python automation & utilities
```

> This separation allows GHCP to use `@workspace` context for cross-layer reasoning and preserves clarity across disciplines (app, infra, automation).

---

## 🧠 2. Global Copilot Principles (`INSTRUCTIONS.md`)

```
# GHCP Global Instructions — Tech Lead Level

## Purpose
These instructions define the behavioral contract between the developer and GitHub Copilot Chat. 
Copilot acts as a *pair architect and senior reviewer*, not just an autocomplete engine.

---

## Core Directives
1. **Context Awareness**
   - Always infer context from the file path, solution structure, and code content.
   - Ask for missing assumptions if required.

2. **Architecture Discipline**
   - Enforce Clean Architecture & SOLID principles.
   - Maintain strict separation between Domain, Application, Infrastructure, and API layers.
   - Never let entities or DTOs bleed across layers.

3. **Security First**
   - Apply OWASP Top 10 principles.
   - Never store secrets in code. Always use Azure Key Vault or environment variables.
   - Validate all inputs; sanitize all outputs.

4. **Code Excellence**
   - Prefer readability over cleverness.
   - Ensure thread-safety, async-safety, and testability.
   - Follow naming conventions aligned with `.editorconfig` and `CODING_GUIDELINES.md`.

5. **Testing Discipline**
   - Generate xUnit tests using Arrange-Act-Assert.
   - Include both positive and negative scenarios.
   - Ensure deterministic, side-effect-free tests.

6. **Cloud Native Readiness**
   - Design APIs for horizontal scalability.
   - Apply 12-factor app principles.
   - Ensure observability hooks (logging, metrics, tracing).

7. **Review Ethic**
   - Classify feedback by: Quality, Security, Performance, Architecture, Maintainability.
   - Rate severity: Low / Medium / High.
   - Always provide remediation guidance.

8. **Documentation**
   - Include concise XML or JSDoc comments.
   - For significant patterns, append an Architecture Decision Record reference (ADR-###).
```

---

## 🧩 3. Intelligent Code Generation (`CODEGEN_PROMPTS.md`)

### 🔹 C# Backend

```
You are acting as a principal .NET architect.

Generate production-ready C# components for {FeatureName} using Clean Architecture:

- Layers: Domain, Application, Infrastructure, API
- Use interfaces and dependency injection
- Async + CancellationToken support
- EF Core (SQL Server) with repository and UoW pattern
- Use Value Objects for core entities
- Include domain validators (FluentValidation)
- Apply OpenTelemetry and structured logging
- Enforce nullability and immutability where possible
- Design extensible methods suitable for unit testing

Expected Deliverables:
1. Domain entity + value object
2. Application service (CQRS handler if needed)
3. Infrastructure repository
4. API controller and DTOs
5. Minimal API registration snippet
6. Sample xUnit tests (optional stub)
```

---

### 🔹 ReactJS or Angular Frontend

```
You are a senior frontend engineer.

Generate a {ReactJS | Angular} component for {FeatureName}.

Requirements:
- TypeScript + Strong typing
- API interaction (Axios or HttpClient)
- State management (Redux Toolkit / NGXS)
- Accessible and responsive UI
- Error and loading state handling
- Modular folder structure
- Unit tests with Jest/Karma

Guidelines:
- Use atomic design principles (atoms → molecules → organisms)
- Avoid business logic in UI components
- Use environment configuration for URLs and secrets
```

---

### 🔹 Terraform / Azure Infrastructure

```
You are a cloud infrastructure architect.

Generate Terraform configuration for {AzureResourceType} with:
- Parameterized variables and outputs
- State management in Azure Storage (remote backend)
- Resource group, tags, RBAC, naming convention standards
- Environments: dev, test, prod
- Security baseline (TLS, KeyVault references)
- Include CI/CD pipeline integration snippet

Compliance:
- Follow Azure Well-Architected Framework pillars.
- Ensure idempotent apply/destroy.
```

---

## 🔍 4. Code Review & Quality Assurance (`REVIEW_PROMPTS.md`)

```
Perform a senior-level code review for {file or feature}.

Analyze and report findings by category:

| Category        | Observations | Severity | Recommendation |
|-----------------|---------------|-----------|----------------|
| Code Quality    |               |           |                |
| Security        |               |           |                |
| Performance     |               |           |                |
| Architecture    |               |           |                |
| Maintainability |               |           |                |

Guidelines:
- Check for SOLID adherence.
- Identify code smells or anti-patterns.
- Highlight async/threading issues.
- Suggest refactoring or pattern alignment (e.g., Strategy, Mediator, Repository).
- Comment inline with reasoning, not just verdicts.
```

---

## 🔐 5. Security Review (`SECURITY_PROMPTS.md`)

```
Perform a security review for {component or API endpoint}.

Checklist:
- Input validation and output encoding
- SQL injection, XSS, CSRF protection
- Secure token handling (Azure AD / B2C)
- Proper HTTPS enforcement and CORS settings
- Secrets not hard-coded (KeyVault or env vars used)
- Logs sanitized of PII or credentials
- Principle of least privilege for resources
- Security headers (CSP, HSTS, X-Frame-Options)

Output:
1. Vulnerability list with severity.
2. Suggested remediation or code change.
3. Reference to relevant OWASP rule.
```

---

## 🏗️ 6. Architecture Review (`ARCHITECTURE_PROMPTS.md`)

```
Act as an enterprise solution architect.

Review architecture of {Feature/ServiceName}.

Evaluation Dimensions (rate 1–5):
- Clean Architecture alignment
- Domain-driven design adherence
- Scalability and elasticity
- Security posture
- Observability and monitoring
- Maintainability and coupling
- Azure cloud resource topology

Deliver:
- Architectural assessment table
- Recommendations with reasoning
- Optional mermaid architecture diagram
- Suggested ADR references
```

---

## 🧪 7. Test Case Generation (`TESTCASE_PROMPTS.md`)

```
Generate xUnit test cases for {C# class or feature}.

Follow:
- AAA (Arrange, Act, Assert)
- Cover positive, negative, and exception scenarios
- Use Moq or NSubstitute for mocking
- Validate boundary conditions
- Ensure deterministic outcomes

Naming convention:
MethodName_Scenario_ExpectedOutcome

Output:
- Full test class with setup
- Explanations for test coverage reasoning
- Optional test data builder or fixture pattern
```

---

## ⚙️ 8. CI/CD Automation (`CICD_PROMPTS.md`)

```
Design a CI/CD pipeline for {ProjectType} using GitHub Actions or Azure DevOps.

Stages:
1. Checkout & Dependency Restore
2. Build & Lint
3. Run Unit & Integration Tests
4. Security Scans (CodeQL, OWASP)
5. Package Artifact (Docker/Zip)
6. Deploy to Azure (App Service, Container Apps, or AKS)
7. Post-Deployment Validation

Principles:
- Fail fast, deploy safe.
- Use environment-specific secrets from KeyVault.
- Implement PR validation gates and build status checks.
- Version all artifacts with semantic versioning.
```

---

## 🐍 9. Python Automation (`PYTHON_AUTOMATION_PROMPTS.md`)

```
You are a senior DevOps automation engineer.

Generate a Python script for {task}, ensuring:
- PEP8 compliance
- Secure file and credential handling
- Logging with timestamps and levels
- CLI args via argparse or typer
- Integration with Azure SDKs
- Unit tests with pytest
- Separation of core logic and I/O
```

---

## 🧭 10. GHCP Usage Protocol — “Copilot as Peer Engineer”

**Prompt Protocol (in VS Code GHCP):**

| Action                  | Example Command                   | Context                            |
| ----------------------- | --------------------------------- | ---------------------------------- |
| **Generate Feature**    | `/codegen @workspace FeatureName` | Creates feature scaffolding        |
| **Review Code**         | `/review @file`                   | Analyzes file for quality/security |
| **Architecture Review** | `/archreview @workspace`          | Reviews service or domain          |
| **Security Scan**       | `/secure @workspace`              | Performs security assessment       |
| **Generate Tests**      | `/tests @file`                    | Writes xUnit or Jest tests         |
| **CI/CD Help**          | `/cicd pipeline for .NET app`     | Suggests deployment pipelines      |

---

## 🧩 11. AI Governance Add-Ons

Optionally define GHCP “operational boundaries” in `.github/copilot/INSTRUCTIONS.md`:

```
# AI Operational Guardrails
- Do not propose code that violates licensing or confidentiality.
- Do not generate secrets, credentials, or tokens.
- Do not suggest external dependencies without justification.
- Explain architectural choices with trade-offs.
- Always include reasoning in comments when assumptions are made.
```

---

## 🎯 Outcome

By following this framework, GHCP becomes:

* Your **pair architect** for design & architecture reasoning
* Your **secure reviewer** for compliance and best practices
* Your **test co-author** for consistent xUnit coverage
* Your **DevOps assistant** for CI/CD and automation scaffolding

---

Would you like me to **generate all `.md` prompt files (INSTRUCTIONS + 7 prompt categories)** ready for direct use in your `.github/copilot/` folder — fully formatted with your tech stack references (C#, React, Angular, Terraform, Azure, SQL Server, Python)?
That way you can plug them directly into VS Code and use them as GHCP prompt references.


Excellent — you’re now moving into a **true Tech Lead Copilot Framework 2.0**, where GitHub Copilot (GHCP) not only generates code but also **acts as an architectural decision companion** capable of reasoning about patterns, architectural styles, and inter-service communication choices.

Below is a **mature, enterprise-grade enhancement** to the prior system — with **pattern-aware, architecture-driven, prompt-powered decisioning** integrated directly into your GHCP workflow.

---

# 🧭 GHCP Enterprise Prompt Framework 2.0

**(with Design Pattern, Architecture, and Communication Selection)**

> ✅ Use this framework to make GHCP behave like a **pair architect + code generation engine** that intelligently adapts to your **design intent** (e.g., pattern, communication, or architecture style).

---

## 📁 1. Recommended Structure (Updated)

```
.github/
 └── copilot/
      ├── INSTRUCTIONS.md
      ├── CODEGEN_PROMPTS.md
      ├── REVIEW_PROMPTS.md
      ├── SECURITY_PROMPTS.md
      ├── ARCHITECTURE_PROMPTS.md
      ├── TESTCASE_PROMPTS.md
      ├── CICD_PROMPTS.md
      ├── PYTHON_AUTOMATION_PROMPTS.md
      └── PATTERN_LIBRARY.md          # ✅ NEW
```

---

## 🧠 2. Enhanced Global Copilot Instructions (`INSTRUCTIONS.md`)

Add this section under the **Architecture Discipline** part:

```
### Design Pattern Awareness
When generating or reviewing code:
1. Identify suitable Gang of Four (GoF) or enterprise patterns based on problem context.
2. Offer user a choice (prompted selection) between:
   - Creational Patterns (Factory, Abstract Factory, Builder, Singleton)
   - Structural Patterns (Adapter, Decorator, Facade, Composite, Proxy)
   - Behavioral Patterns (Strategy, Command, Observer, Mediator, State)
   - Domain/Enterprise Patterns (Repository, Unit of Work, CQRS, Specification, Saga)
3. Always justify pattern selection with reasoning.

### Microservice Context Awareness
When user requests a new service:
1. Suggest microservice type (Transactional, Data Aggregation, Orchestration, Utility)
2. Offer communication options:
   - Synchronous (HTTP/gRPC)
   - Asynchronous (Azure Service Bus/Event Grid/Event Hub)
   - Hybrid (request/response + event notifications)
3. Ensure proper boundaries (bounded context, API contract, and domain isolation).
4. Include service-to-service authentication (Managed Identity, Azure AD, or API key).

### Application Architecture Choices
Allow selection from:
- Monolith (modular)
- Modular Monolith
- Microservices
- Event-driven microservices
- Service Mesh (Advanced)
After user selection, tailor code generation accordingly.
```

---

## 🧩 3. Advanced Code Generation Prompts (`CODEGEN_PROMPTS.md`)

### 💡 Adaptive Feature Generation Prompt

```
You are an AI-assisted principal architect.

Generate a complete implementation for {FeatureName} in {C# / React / Angular}.

Before generation:
1. Ask the user to choose:
   - Architecture Style: [Clean | Onion | Hexagonal | Event-Driven | Microservice]
   - Communication Type (if microservice): [HTTP REST | gRPC | Service Bus | Event Grid]
   - Design Pattern: (from PATTERN_LIBRARY.md)
2. Confirm selection before generating.

After selection:
- Implement code using selected architecture and pattern.
- Ensure separation of concerns across layers.
- Add comments explaining why pattern was applied.
- Include OpenTelemetry hooks and structured logging.
- Include sample xUnit tests.
```

---

### 🧩 Example Prompt Usage

In GHCP chat inside VS Code:

> `/codegen Feature: Order Processing using Hexagonal Architecture and Strategy Pattern. Use asynchronous event-based communication via Azure Service Bus.`

Expected GHCP behavior:

* It infers architecture skeleton → ports/adapters + domain logic
* Uses Strategy pattern for pricing rules
* Adds event publishing/subscription boilerplate (Service Bus)
* Generates unit tests and DTOs
* Annotates architectural reasoning in comments

---

## 🏗️ 4. Pattern Library (`PATTERN_LIBRARY.md`)

> This is a **menu of available patterns** GHCP can use during code generation.
> Each entry includes when to use, benefits, and sample prompt snippet.

### 🎯 Creational Patterns

| Pattern              | When to Use                          | Prompt Example                                                   |
| -------------------- | ------------------------------------ | ---------------------------------------------------------------- |
| **Factory Method**   | Object creation logic varies by type | “Generate Factory pattern for repository instantiation.”         |
| **Abstract Factory** | Create families of related objects   | “Use Abstract Factory for data provider selection (SQL/Cosmos).” |
| **Builder**          | Complex object construction          | “Apply Builder for DTO creation from multiple inputs.”           |
| **Singleton**        | Single shared instance               | “Create a thread-safe Singleton for configuration manager.”      |

---

### 🧩 Structural Patterns

| Pattern       | When to Use                      | Prompt Example                                           |
| ------------- | -------------------------------- | -------------------------------------------------------- |
| **Adapter**   | Interface compatibility          | “Use Adapter for external API response transformation.”  |
| **Decorator** | Add responsibilities dynamically | “Wrap logging and caching using Decorator pattern.”      |
| **Facade**    | Simplify complex subsystem       | “Expose Facade for order orchestration service.”         |
| **Composite** | Tree structure manipulation      | “Model complex rule evaluation using Composite pattern.” |
| **Proxy**     | Controlled access                | “Add caching proxy for repository.”                      |

---

### 🔄 Behavioral Patterns

| Pattern      | When to Use                    | Prompt Example                                        |
| ------------ | ------------------------------ | ----------------------------------------------------- |
| **Strategy** | Interchangeable algorithms     | “Use Strategy for different pricing logic.”           |
| **Command**  | Encapsulate actions            | “Implement Command for workflow execution.”           |
| **Observer** | Event notifications            | “Use Observer pattern for audit events.”              |
| **Mediator** | Coordinate interactions        | “Introduce Mediator for inter-service orchestration.” |
| **State**    | Object behavior based on state | “Model approval states using State pattern.”          |

---

### 🧱 Domain & Enterprise Patterns

| Pattern                    | When to Use               | Prompt Example                                            |
| -------------------------- | ------------------------- | --------------------------------------------------------- |
| **Repository + UoW**       | Abstract data access      | “Generate Repository & Unit of Work for Customer entity.” |
| **CQRS**                   | Split read/write models   | “Apply CQRS for Order microservice.”                      |
| **Event Sourcing**         | Maintain event log        | “Use Event Sourcing for audit trail in Order aggregate.”  |
| **Saga / Process Manager** | Long-running transactions | “Generate Saga for multi-step booking workflow.”          |
| **Specification Pattern**  | Dynamic query composition | “Use Specification for filtering customer data.”          |

---

## 🧱 5. Microservice Communication Prompt Extensions

### ✉️ Communication Option Prompts

| Type                    | Description                    | Prompt Example                                                |
| ----------------------- | ------------------------------ | ------------------------------------------------------------- |
| **HTTP REST**           | Standard request-response      | “Create API controller using REST for synchronous calls.”     |
| **gRPC**                | High-performance interservice  | “Generate gRPC client and server stubs for Payment service.”  |
| **Service Bus (Async)** | Event-driven messaging         | “Publish events via Azure Service Bus topic.”                 |
| **Event Grid**          | Serverless event notifications | “Raise domain events via Event Grid for downstream services.” |
| **SignalR**             | Real-time updates              | “Use SignalR for pushing notifications to React frontend.”    |

GHCP Response must:

* Choose appropriate SDKs
* Generate configuration setup (connection string/env var)
* Implement message contracts (DTO/Event schema)
* Suggest retry and dead-letter strategies

---

## 🧱 6. Architecture Style Prompts (Integrated)

| Architecture                  | When to Use                         | GHCP Prompt                                                          |
| ----------------------------- | ----------------------------------- | -------------------------------------------------------------------- |
| **Clean Architecture**        | Domain-driven backend               | “Generate API feature using Clean Architecture.”                     |
| **Onion Architecture**        | Enterprise consistency              | “Use Onion Architecture for consistent dependency inversion.”        |
| **Hexagonal Architecture**    | Ports/adapters, testable boundaries | “Generate Hexagonal Architecture skeleton for order domain.”         |
| **Event-Driven Microservice** | Async, scalable                     | “Implement microservice with Event-Driven design using Service Bus.” |
| **Modular Monolith**          | Transition to microservices         | “Design modular monolith with bounded contexts.”                     |

---

## 🔍 7. Multi-Dimensional Code Generation Prompt (Final Unified Template)

> **Prompt Template (Reusable)**

```
You are an enterprise-level AI engineering assistant.

Generate implementation for {FeatureName}.

Context:
- Stack: {C# / React / Angular / Terraform / Python}
- Architecture: {Clean | Onion | Hexagonal | Microservice | Event-driven}
- Communication: {HTTP | gRPC | Service Bus | Event Grid}
- Design Pattern: {Factory | Strategy | CQRS | Saga | Specification | Decorator}
- Data Layer: {EF Core | Dapper | Cosmos | SQL Server}
- Cloud: Azure
- Non-functional requirements: Security, Observability, Testability, Maintainability

Expectations:
1. Generate clean, modular, production-quality code.
2. Include architectural comments and assumptions.
3. Apply selected pattern with rationale.
4. Provide related xUnit or Jest tests.
5. Suggest relevant CI/CD steps (build/test/deploy).
```

---

## 🧪 8. Example Conversations

### 🔸 Example 1 — Backend

> `/codegen Feature: Claims Adjudication | Architecture: Hexagonal | Pattern: CQRS | Communication: Service Bus | Data: SQL Server`

→ GHCP builds:

* Command/Query handlers
* Domain layer with events
* Infrastructure adapters for Service Bus
* EF-based repositories
* Unit tests

---

### 🔸 Example 2 — Frontend

> `/codegen Feature: Claim Summary Dashboard | Architecture: Component-driven | Pattern: Observer | Framework: React | Communication: REST`

→ GHCP generates:

* React components with observer hooks
* REST API integration service
* Reusable state management logic
* Jest test coverage

---

### 🔸 Example 3 — Infrastructure

> `/codegen Terraform module for Event Grid setup with per-environment configuration and RBAC policies.`

→ GHCP generates:

* Parameterized Terraform module
* Remote backend config
* Outputs and variable files
* CI/CD YAML for apply/destroy

---

## 🧱 9. Optional: Pattern Discovery Prompt

```
@workspace 
Analyze this service. Recommend 3 suitable GoF or enterprise patterns to improve modularity or maintainability.
Explain pros, cons, and where each fits.
```

---

## 🏁 10. Summary

| Category                         | Purpose                                              |
| -------------------------------- | ---------------------------------------------------- |
| **INSTRUCTIONS.md**              | Defines Copilot’s behavioral and architectural rules |
| **CODEGEN_PROMPTS.md**           | Smart prompt scaffolds for full-stack generation     |
| **PATTERN_LIBRARY.md**           | Pattern reasoning and selection menu                 |
| **ARCHITECTURE_PROMPTS.md**      | Architecture evaluation and scoring                  |
| **REVIEW_PROMPTS.md**            | Code review and quality control                      |
| **SECURITY_PROMPTS.md**          | OWASP-based secure review                            |
| **TESTCASE_PROMPTS.md**          | xUnit and Jest test generation                       |
| **CICD_PROMPTS.md**              | Pipeline automation templates                        |
| **PYTHON_AUTOMATION_PROMPTS.md** | Python-based tooling and scripting automation        |

---

Would you like me to **generate all these files as a ready-to-commit `.github/copilot/` folder**, with pattern-aware prompt definitions, architecture templates, and microservice communication choices baked in — so GHCP can directly interpret and execute them?

(You’ll get 9 Markdown files fully populated and ready for your repo.)


Excellent — let’s build a **comprehensive, professional-grade GitHub Copilot / GHCP prompt framework** that you (as a Tech Lead / Solution Architect) can directly use in **VS Code with GHCP** to generate, review, and enforce high-quality, enterprise-grade code and architecture standards.

Below is a **complete consolidated version** covering:
✅ Prompt templates for **code generation, review, architecture, and security**
✅ Support for **C#, React, Angular, Terraform, SQL Server, Azure, and Python**
✅ Built-in options for **GoF patterns, architectural patterns, and communication patterns**
✅ File scaffolding for GHCP prompt workflows (system, developer, reviewer, architecture, and test prompts)
✅ **Example usages** and **sample prompt-output conversations** for clarity

---

## 🧭 1. Directory Structure (Recommended for GHCP + VSCode)

```plaintext
/.github/
  ├── prompts/
  │   ├── system/
  │   │   ├── codegen.md
  │   │   ├── codereview.md
  │   │   ├── archreview.md
  │   │   ├── securityreview.md
  │   │   ├── testgen.md
  │   │   ├── designpatterns.md
  │   │   └── architecturepatterns.md
  │   ├── developer/
  │   │   ├── csharp.md
  │   │   ├── react.md
  │   │   ├── angular.md
  │   │   ├── terraform.md
  │   │   ├── sqlserver.md
  │   │   ├── azure.md
  │   │   └── python.md
  │   └── guidelines/
  │       ├── code_quality.md
  │       ├── naming_conventions.md
  │       ├── exception_handling.md
  │       ├── logging_standards.md
  │       └── security_practices.md
  └── workflows/
      └── review.yml
```

---

## 🧩 2. System Prompts (GHCP-Level Contexts)

### 🧱 `codegen.md` – Code Generation Prompt

> **Purpose:** Generate clean, maintainable, enterprise-level code following Clean Architecture + SOLID + CQRS + DDD principles.

````markdown
# System Prompt: Code Generation

You are an AI Assistant acting as a Senior Solution Architect for an enterprise-scale system.
Your goal is to generate production-ready, well-structured, and testable code based on the provided requirements.

Follow these rules:
1. Use **Clean Architecture**: Layers = Domain, Application, Infrastructure, API.
2. Apply **CQRS** for command/query separation where applicable.
3. Apply **GoF Design Patterns** when explicitly requested (e.g., Strategy, Factory, Mediator).
4. Add **XML documentation**, meaningful naming, and comments.
5. Use **Dependency Injection**, **async/await**, and **cancellation tokens**.
6. Never expose domain entities directly to controllers — use DTOs and mapping.
7. Follow principles: SOLID, DRY, KISS, and YAGNI.
8. Provide example unit tests using **xUnit** and **Moq**.
9. Output should include: architecture explanation + code + brief test plan.

**Output format:**
```plaintext
### Architecture Overview
...

### Implementation (C# or React or other)
...

### Test Cases
...
````

````

---

### 🧾 `codereview.md` – Code Review Prompt

```markdown
# System Prompt: Code Review

You are an expert reviewer analyzing the submitted code for:
- Code quality (readability, maintainability)
- Architecture alignment (Clean, CQRS, DDD)
- Security (SQL Injection, XSS, secrets)
- Performance and scalability
- Exception handling, logging, validation

Provide:
1. A summary of strengths.
2. Issues categorized as:
   - 🚫 **Critical**
   - ⚠️ **Major**
   - 💡 **Suggestions**
3. A proposed refactored version if necessary.

End with a **Code Quality Score (0–10)**.
````

---

### 🧱 `archreview.md` – Architecture Review Prompt

```markdown
# System Prompt: Architecture Review

You are a Chief Architect reviewing a system design. Evaluate for:
- Architecture pattern compliance (Microservices / Clean / Onion / Hexagonal)
- Communication patterns (Sync REST, Async via Service Bus, Event-driven)
- Scalability, resilience, observability (OpenTelemetry)
- CI/CD readiness
- Security (Azure AD B2C, managed identity, secrets, key vaults)
- Deployment (Terraform or Bicep)
- Integration with other systems

Deliver output:
1. Architecture Rating (1–10)
2. Strengths and Gaps
3. Recommendations for improvements
4. Suggested communication or GoF pattern if missing
```

---

### 🔐 `securityreview.md` – Security Review Prompt

```markdown
# System Prompt: Security Review

Check the provided code or IaC (Terraform) for:
- Secrets in code
- Authentication/authorization flaws
- SQL injection, XSS, CSRF
- Secure headers, CORS
- Azure KeyVault usage
- Logging PII data
- Security best practices in APIs and SPAs

Output:
- Vulnerability category
- Code reference
- Fix recommendation
```

---

### 🧪 `testgen.md` – Test Case Generation Prompt

````markdown
# System Prompt: Test Generation (xUnit)

You are a QA automation architect generating tests for .NET services.

Rules:
- Use xUnit + Moq.
- Follow AAA (Arrange, Act, Assert).
- Cover positive, negative, edge cases.
- For API, use integration test via WebApplicationFactory.
- For React/Angular, generate Jest/Karma test stubs.

Output:
```plaintext
### Test Plan
...

### Test Cases (xUnit)
...
````

````

---

## 🧰 3. Developer Prompts (Per Language/Tech)

Example: **`developer/csharp.md`**

```markdown
# Developer Prompt: C#

Language: C#
Framework: .NET 8
Patterns: Clean Architecture + CQRS + DDD
Testing: xUnit + Moq
Database: SQL Server or CosmosDB
Logging: Serilog + Application Insights

When asked to generate code:
- Always separate layers.
- Use MediatR for commands and queries.
- Include repository abstraction in domain.
- Follow naming conventions and DTO boundaries.
````

(Similar structured prompts can be created for React, Angular, Terraform, etc.)

---

## 🧠 4. Design Pattern Prompt Options

### `designpatterns.md`

```markdown
Choose one or combine:

1. **Creational:** Factory, Builder, Singleton, Prototype
2. **Structural:** Adapter, Composite, Decorator, Facade, Proxy
3. **Behavioral:** Strategy, Observer, Mediator, Command, Chain of Responsibility

Prompt Example:
> Use the Strategy pattern to handle multiple discount rules dynamically in an e-commerce checkout service.
```

---

## 🏗️ 5. Architecture Pattern Options

### `architecturepatterns.md`

```markdown
Options:
1. Clean Architecture
2. Onion Architecture
3. Hexagonal Architecture
4. Event-driven Microservices
5. CQRS + Event Sourcing
6. Modular Monolith
7. Serverless (Azure Functions)

Prompt Example:
> Design this feature using Event-driven Microservices with CQRS. Use Azure Service Bus for communication between services.
```

---

## ⚙️ 6. Sample Prompt Usage (in GHCP)

### 🔸 Example 1: Code Generation

**Prompt:**

```
@codegen
Generate a C# service in Clean Architecture for managing patient records with CQRS and MediatR.
Apply Repository + Unit of Work + Factory pattern.
Database: SQL Server.
Add xUnit test for PatientService.
```

**Response (Summarized):**

* ✅ Architecture Overview (Domain, Application, Infrastructure, API)
* ✅ Implementation with interfaces and MediatR handlers
* ✅ Test Cases in xUnit with mocks
* ✅ Notes on Repository pattern use

---

### 🔸 Example 2: Code Review

**Prompt:**

```
@codereview
Review the following PatientService.cs for performance, security, and design pattern alignment.
```

**Response:**

* 🚫 Found blocking calls using `.Result` — suggest `await`.
* ⚠️ DTOs leak domain model — recommend mapping.
* 💡 Suggest caching strategy for repeated lookups.
* **Score:** 8.5/10

---

### 🔸 Example 3: Architecture Review

**Prompt:**

```
@archreview
Review this architecture diagram and API flow description.
We’re using Azure App Services + API Management + Azure SQL + B2C.
Event-driven via Service Bus. Is this resilient and scalable?
```

**Response:**

* Strengths: Modular, secure, well-scaled.
* Gaps: Missing circuit breaker and retry policy.
* Recommendation: Use Polly + Application Insights tracing.
* Architecture Rating: 9/10

---

### 🔸 Example 4: Test Generation

**Prompt:**

```
@testgen
Generate xUnit tests for PatientService with Moq. Cover validation, repository, and MediatR call.
```

**Response:**

* Test cases for CreatePatient_Success, CreatePatient_ThrowsValidationError
* Mock setup and verification
* Assertion coverage

---

## 🚀 7. How to Use in GHCP (GitHub Copilot Chat)

* Open VS Code → GHCP Chat pane.
* Type:

  ```
  @workspace /prompts/system/codegen.md
  Generate repository and service for Order management using Factory pattern.
  ```
* GHCP will contextually apply your system + developer prompt and output consistent, enterprise-grade code.

---

## 🧩 8. Optional Extensions

You can enhance this setup with:

* `.copilot-instructions.md` (global defaults)
* `.copilot/context.json` (map project modules to prompts)
* CI/CD GHCP workflows (to trigger auto code review comments)

---

Would you like me to **package this into a ready-to-import VS Code GHCP scaffolding (with all markdown files and example prompt folder structure)** in a downloadable ZIP format?
That way, you can directly plug it into your repo and start prompting professionally.


Excellent question — this shows you’re thinking like a **Tech Lead who wants to use GitHub Copilot / GHCP professionally and systematically** rather than just “asking it to code.”

Let’s unpack this carefully and **explain the rationale, purpose, and behavior** of each concept — `folder structure`, `@ vs / usage`, `system/developer/guidelines folders`, and `instructions` files — **in the context of GHCP (GitHub Copilot Chat for VSCode)**.

---

## 🧭 1. Why This Folder Structure Exists

The folder structure under `.github/prompts` is not random — it’s designed to give **Copilot (and you)** a *context hierarchy*.
It’s inspired by how GHCP (GitHub Copilot Chat for Professionals / GHCP) and advanced Copilot configurations organize **prompt contexts** for large enterprise codebases.

Here’s the reasoning:

```plaintext
/.github/
  ├── prompts/
  │   ├── system/          ← For system-level prompts (roles, behavior, style)
  │   ├── developer/       ← For language or tech-specific developer guides
  │   └── guidelines/      ← For shared coding, naming, and security standards
  └── workflows/           ← For GitHub Actions workflows (optional automation)
```

### 🎯 Purpose of Each:

| Folder          | Purpose                                                                                                                                                                                | Who Uses It                                                                                  | Example Files                                                            |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| **system/**     | “System prompts” define the *role* Copilot should take (e.g., code reviewer, architect, tester). These act like “personas.”                                                            | You (Tech Lead) use these explicitly when chatting with GHCP.                                | `codegen.md`, `codereview.md`, `archreview.md`, `testgen.md`             |
| **developer/**  | “Developer context prompts” contain **tech-specific instructions**. They tell Copilot how to code in that tech stack (C#, React, Terraform, etc.) following your internal conventions. | Automatically loaded if you use `/prompts/developer/...` or referenced from a system prompt. | `csharp.md`, `react.md`, `sqlserver.md`                                  |
| **guidelines/** | “Shared organization-level best practices.” Used by other prompts to enforce consistent style, naming, logging, and security patterns.                                                 | Usually referenced inside `system` or `developer` prompts.                                   | `naming_conventions.md`, `logging_standards.md`, `security_practices.md` |

So effectively:

* **system/** = “What to do”
* **developer/** = “How to do it in this tech”
* **guidelines/** = “What rules to follow”

---

## 🧩 2. Why Some Blogs Mention `/instructions`

Some teams or blogs use an **`/instructions`** folder instead of or alongside `/prompts`.

| Folder          | Typical Use                                                                                 | When to Prefer                                                                                 |
| --------------- | ------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `prompts/`      | Used for **prompt roles** — reusable templates for Copilot Chat.                            | Modern GHCP / Copilot Chat setups.                                                             |
| `instructions/` | Used for **static policy files** that GHCP reads globally, like `.copilot-instructions.md`. | When you want every chat or generation in repo to follow a baseline instruction automatically. |

In short:

* **`prompts/`** = reusable role or context prompts (called explicitly using `@`)
* **`instructions/`** = default configuration file applied **automatically** for all Copilot actions (no need to call manually)

👉 You can safely use both:

* Keep `prompts/` for interactive roles like `@codegen` or `@archreview`.
* Use `.copilot-instructions.md` or `/instructions/global.md` for defaults like “Always use Clean Architecture in .NET”.

---

## ⚙️ 3. Why Use `@` Instead of `/` When Calling Prompts

When you type in **GitHub Copilot Chat (VSCode)**:

### Example A — Using `@`:

```
@codegen
Generate a C# API for managing orders using CQRS pattern.
```

➡️ This tells GHCP:

> “Apply the **system-level prompt** named `codegen.md` from `.github/prompts/system/`.”

### Example B — Using `/`:

```
/prompts/system/codegen.md
Generate a C# API for managing orders using CQRS pattern.
```

➡️ This gives GHCP a **direct file path**. It’s supported but more verbose, used mostly for debugging or if GHCP doesn’t auto-index prompts.

### Difference Summary:

| Symbol | Meaning                                    | Typical Use                            |
| ------ | ------------------------------------------ | -------------------------------------- |
| **@**  | Calls a **prompt alias** (like a persona). | Human-friendly shorthand.              |
| **/**  | Calls a **direct path** to a file.         | Explicit, less readable, more control. |

👉 **Best Practice:**

* Use `@` for commonly used system/developer prompts (like `@codegen`, `@codereview`).
* Use `/` when testing or debugging a specific file (rarely needed in daily use).

---

## 🧠 4. How GHCP Resolves and Uses These Files

Here’s how GHCP processes prompts step-by-step when you call one:

### Step 1. Indexing

GHCP automatically scans:

* `.github/prompts/`
* `.github/instructions/`
  and builds an **index of available prompt names** (e.g., `@codegen`, `@csharp`, `@securityreview`).

### Step 2. Context Loading

When you type:

```
@codegen Generate PatientService with CQRS and MediatR
```

GHCP loads:

1. `.github/prompts/system/codegen.md` → defines the system behavior (what to generate, style, structure).
2. Then, if your project has `developer/csharp.md`, it merges it as **tech-specific context**.
3. If `guidelines/` files are referenced in `codegen.md` (like security or logging), they’re also included.

### Step 3. Context Fusion

It merges these layers:

```
System prompt (role) 
+ Developer tech context 
+ Guidelines (organization standards) 
+ Your inline message
```

This becomes the **effective final prompt** Copilot uses.

Example internal composition:

```plaintext
System prompt: You are a code generator following Clean Architecture
Developer prompt: For C# projects, use CQRS, DDD, MediatR
Guidelines: Follow naming conventions and security practices
User: Generate PatientService with async repository pattern
```

That’s how it produces consistent, policy-aligned output across your org.

---

## 🧩 5. Example Flow — End-to-End Usage

Let’s walk through an example:

### Step 1. You type:

```
@codegen
Generate a PatientService using Factory + Repository pattern.
Use C#, MediatR, xUnit tests.
```

### Step 2. GHCP does:

* Loads `system/codegen.md` → defines structure + test generation rule.
* Merges `developer/csharp.md` → adds syntax, frameworks, DI style.
* Loads `guidelines/security_practices.md` and `naming_conventions.md` if referenced.

### Step 3. Output:

* Full Clean Architecture structure (Domain, Application, Infrastructure, API)
* Repository, Factory pattern implementation
* xUnit test cases
* Logging + exception handling aligned with your guidelines

---

## 🧩 6. Real-World Analogy

Think of this setup like **a layered instruction book for an AI engineer**:

| Layer             | Analogy                     | Example                                                       |
| ----------------- | --------------------------- | ------------------------------------------------------------- |
| System Prompt     | Job role                    | “You are a Solution Architect generating enterprise C# code.” |
| Developer Prompt  | Department specialization   | “We use .NET 8, CQRS, MediatR, Serilog.”                      |
| Guidelines        | Company policy              | “Follow logging and naming conventions.”                      |
| Instructions File | Company onboarding manual   | “Always apply Clean Architecture by default.”                 |
| @codegen          | Calling a specific engineer | “Hey, codegen, build me this module.”                         |

---

## 🧩 7. Recommended Enhancement — Add an `instructions/global.md`

If you want your **entire Copilot setup to follow Clean Architecture and SOLID rules by default** (without having to remind it), add:

**`.github/instructions/global.md`**

```markdown
# Global Copilot Instructions
Always:
- Use Clean Architecture and CQRS.
- Prefer async/await and dependency injection.
- Never mix domain and infrastructure concerns.
- Use DTOs for API layers.
- Include xUnit test generation if applicable.
```

Now GHCP will automatically apply these defaults even when you don’t specify `@codegen`.

---

## ✅ 8. Quick Summary Table

| Concept                          | Purpose                     | Example Usage                  | Effect                        |
| -------------------------------- | --------------------------- | ------------------------------ | ----------------------------- |
| `.github/prompts/system/`        | Define roles/personas       | `@codegen`, `@codereview`      | Sets task-specific behavior   |
| `.github/prompts/developer/`     | Tech-specific config        | Auto when generating C#, React | Adds framework context        |
| `.github/prompts/guidelines/`    | Reusable best practices     | Linked in system prompt        | Enforces standards            |
| `.github/instructions/global.md` | Global defaults             | Auto-applied                   | Consistent behavior repo-wide |
| `@`                              | Shortcut alias for a prompt | `@archreview`                  | Simple to use                 |
| `/`                              | Direct file path            | `/prompts/system/codegen.md`   | Explicit control, rare use    |

---

Would you like me to show you **a fully wired sample `.github/prompts` structure** (with references, alias setup, and internal linking between system, developer, and guidelines) — so you can drop it directly into your repo and start using `@codegen`, `@codereview`, etc. out of the box?
I can include internal linking examples and GHCP-ready markdown for each role.


Excellent — now we’ll evolve your GHCP prompt setup into a **true enterprise-grade architecture framework** suitable for review and governance by an **Enterprise Architect**.

This version is modeled on how large enterprises (Microsoft, JP Morgan, Accenture, etc.) standardize **AI-assisted software engineering guardrails** in GitHub Copilot for Business or GHCP setups.

---

# 🏢 ENTERPRISE-GRADE GHCP PROMPT FRAMEWORK

## 🧭 1. Core Design Principles

| Principle                          | Description                                                                                                   |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| **Consistency through Governance** | All AI-assisted outputs (code, IaC, documentation) must align with architectural guardrails and standards.    |
| **Separation of Context**          | Prompts are modular: *system* (role logic), *developer* (tech policy), *guidelines* (shared governance).      |
| **Traceability & Audit**           | Each prompt file is versioned, reviewed, and traceable in Architecture Review Boards (ARB).                   |
| **Cross-Functional Integration**   | Supports code generation, reviews, test scaffolding, DevSecOps, observability, and architectural conformance. |
| **Scalability**                    | Same structure can support 10+ tech stacks and microservices across multiple domains.                         |

---

## 🗂️ 2. Enterprise Folder Structure (Governed Layout)

```plaintext
/.github/
  ├── prompts/
  │   ├── system/                # System role prompts (architectural personas)
  │   │   ├── codegen.md
  │   │   ├── codereview.md
  │   │   ├── archreview.md
  │   │   ├── securityreview.md
  │   │   ├── testgen.md
  │   │   ├── designpatterns.md
  │   │   └── architecturepatterns.md
  │   │
  │   ├── developer/             # Tech-specific development standards
  │   │   ├── csharp.md
  │   │   ├── react.md
  │   │   ├── angular.md
  │   │   ├── terraform.md
  │   │   ├── sqlserver.md
  │   │   ├── azure.md
  │   │   └── python.md
  │   │
  │   ├── guidelines/            # Enterprise guardrails and reusable standards
  │   │   ├── code_quality.md
  │   │   ├── naming_conventions.md
  │   │   ├── exception_handling.md
  │   │   ├── logging_standards.md
  │   │   ├── security_practices.md
  │   │   ├── observability.md
  │   │   └── performance_standards.md
  │   │
  │   └── metadata/
  │       ├── taxonomy.json      # Map prompt aliases (@codegen, @archreview)
  │       ├── governance.md      # Explains governance flow and review ownership
  │       └── change_log.md      # Version tracking for ARB review
  │
  ├── instructions/
  │   ├── global.md              # Default Copilot instruction baseline
  │   ├── secure_coding.md       # Always loaded for any generation
  │   └── architecture_guardrails.md
  │
  └── workflows/
      └── review.yml             # Optional: triggers architecture/security review pipelines
```

---

## 🧩 3. Prompt Hierarchy (System → Developer → Guidelines)

### 📘 System Prompts – “Role-based Persona Definitions”

> These define **who** Copilot is acting as and **what goal** it serves.

| Prompt                    | Responsibility                                          | Key Enforcement                                     |
| ------------------------- | ------------------------------------------------------- | --------------------------------------------------- |
| `codegen.md`              | Generate code following Clean Architecture + DDD + CQRS | Output structure, test coverage, SOLID compliance   |
| `codereview.md`           | Review code for quality, performance, maintainability   | Lint, performance hints, code score                 |
| `archreview.md`           | Evaluate system design and communication patterns       | Identify gaps vs. enterprise reference architecture |
| `securityreview.md`       | Identify and mitigate vulnerabilities                   | OWASP + Azure security standards                    |
| `testgen.md`              | Auto-generate xUnit / Jest test coverage                | Test coverage > 80% recommended                     |
| `designpatterns.md`       | Suggest GoF patterns contextually                       | Encourage reusability & extensibility               |
| `architecturepatterns.md` | Enforce architecture paradigms (Clean, Hex, EDA)        | Alignment with enterprise target state              |

---

### 🧑‍💻 Developer Prompts – “Technology Implementation Contracts”

> These define **how** a developer in that stack should implement solutions.

| Prompt         | Scope          | Example Enforcement                                           |
| -------------- | -------------- | ------------------------------------------------------------- |
| `csharp.md`    | .NET stack     | Use DI, async/await, MediatR, Serilog, Azure App Insights     |
| `react.md`     | React stack    | Use hooks, component composition, state mgmt, testing-library |
| `angular.md`   | Angular stack  | Standalone components, DI, interceptors, RxJS patterns        |
| `terraform.md` | IaC standards  | AzureRM modules, backend state mgmt, security rules           |
| `sqlserver.md` | DB design      | Schema normalization, indexing, query performance             |
| `azure.md`     | Azure patterns | Key Vault, Managed Identity, APIM, Functions, CI/CD           |
| `python.md`    | Data/AI tasks  | Virtual env, dependency mgmt, PEP8 compliance                 |

---

### 🧱 Guidelines – “Enterprise Guardrails”

> Shared across all stacks. These act as **architectural and coding governance documents**.

Examples:

* `security_practices.md` → OWASP, secret management, encryption, B2C integration.
* `logging_standards.md` → correlation ID, distributed tracing, App Insights.
* `exception_handling.md` → use global handlers, no raw stack trace leaks.
* `observability.md` → OpenTelemetry instrumentation, metric standards.
* `performance_standards.md` → response time SLAs, caching, async I/O usage.

These can be referenced by any `system/` or `developer/` prompt like:

```markdown
# Refer to
../guidelines/security_practices.md
../guidelines/logging_standards.md
```

---

## ⚙️ 4. Why This Hierarchy Exists

| Layer            | Ownership                       | Review Cadence        | Purpose                                  |
| ---------------- | ------------------------------- | --------------------- | ---------------------------------------- |
| **System**       | Solution / Enterprise Architect | Quarterly             | Define AI roles for generation & review  |
| **Developer**    | Tech Leads per domain           | Monthly               | Capture per-stack implementation norms   |
| **Guidelines**   | Architecture Board (ARB)        | Annually or on change | Maintain enterprise-wide guardrails      |
| **Instructions** | Architecture Governance Office  | Static                | Define default Copilot behavior baseline |

---

## 🧠 5. `@` vs `/` (Enterprise Behavior Clarified)

| Symbol | Meaning                                                                              | Enterprise Policy                                               |
| ------ | ------------------------------------------------------------------------------------ | --------------------------------------------------------------- |
| **@**  | Alias resolved via `taxonomy.json`. Used for calling a persona (e.g. `@archreview`). | ✅ Standard for daily use by developers.                         |
| **/**  | Explicit file reference (e.g. `/prompts/system/codegen.md`).                         | 🔒 Restricted to Architects or Debugging; ensures traceability. |

**taxonomy.json** maps:

```json
{
  "aliases": {
    "@codegen": "/.github/prompts/system/codegen.md",
    "@codereview": "/.github/prompts/system/codereview.md",
    "@archreview": "/.github/prompts/system/archreview.md",
    "@testgen": "/.github/prompts/system/testgen.md"
  }
}
```

This alias map allows uniform prompt calling across projects — standard governance.

---

## 🧩 6. Global Instructions (Applied Implicitly)

**File:** `.github/instructions/global.md`

```markdown
# Global Copilot Instructions (Enterprise Default)
- Always align code generation with Clean Architecture principles.
- Enforce SOLID and DRY.
- Generate xUnit tests by default for all C# modules.
- Include observability via OpenTelemetry and structured logging.
- All secrets and credentials must be managed via Azure Key Vault.
- Never use `.Result` or `.Wait()` in async code.
- Follow organization’s naming and exception handling conventions.
```

This ensures even ad-hoc Copilot use outside GHCP chat stays compliant.

---

## 🔐 7. Governance & Review Workflow

### 1️⃣ Developer Interaction (Local)

* Developer types:
  `@codegen Generate OrderService using Factory pattern and CQRS`
* GHCP uses the `system → developer → guidelines` merge chain.

### 2️⃣ Code Review (PR Stage)

* Reviewer triggers `@codereview` in GHCP or GitHub comment.
* Copilot evaluates code quality and architecture alignment.

### 3️⃣ Architecture Review (ARB Stage)

* Architect runs `@archreview` prompt for major design decisions.
* Review logged in `metadata/change_log.md`.

### 4️⃣ Continuous Governance

* `workflows/review.yml` auto-runs security and architecture reviews nightly.

---

## 💬 8. Sample Prompt Exchanges (Enterprise-Style)

### 🧩 Code Generation

```
@codegen
Create a .NET 8 microservice named ClaimProcessingService following Clean Architecture.
Apply Mediator + Factory patterns.
Use Azure Service Bus for async communication.
Include xUnit tests and OpenTelemetry tracing.
```

**Copilot Output:**

* Multi-layered architecture summary
* CQRS + MediatR handlers
* Service Bus publisher/subscriber
* Telemetry instrumentation
* xUnit + Moq tests

---

### 🧩 Architecture Review

```
@archreview
Evaluate this microservice architecture: App Service + APIM + Azure SQL + KeyVault + Event Grid.
Is it compliant with event-driven architecture standards and security posture?
```

**Copilot Output:**

* Architecture Rating: 9/10
* Strengths: Scalability, resilience, security.
* Gaps: Missing retry policies, distributed tracing coverage.
* Recommendation: Add Polly policies + Service Bus DLQ monitoring.

---

### 🧩 Security Review

```
@securityreview
Analyze Terraform IaC for network exposure, secret handling, and RBAC violations.
```

**Copilot Output:**

* 🚫 Critical: Hardcoded connection string in variable.tf
* ⚠️ Major: Missing NSG rules for internal subnet
* ✅ Recommendation: Use Key Vault secrets, restrict inbound rules.

---

## 🧱 9. Enterprise Readiness Checklist (for Architect Review)

| Category            | Check                                                  | Description                 |
| ------------------- | ------------------------------------------------------ | --------------------------- |
| **Structure**       | ✅ `.github/prompts` hierarchy in place                 | Consistent naming and roles |
| **Governance**      | ✅ `metadata/governance.md` defines review ownership    | Reviewed quarterly by ARB   |
| **Security**        | ✅ `securityreview.md` follows OWASP + Azure guidelines | Automated scan included     |
| **Observability**   | ✅ `observability.md` mandates OpenTelemetry tracing    | Required for production     |
| **Test Automation** | ✅ `testgen.md` creates 80%+ coverage baseline          | Enforced in PR pipeline     |
| **Compliance**      | ✅ `taxonomy.json` alias map versioned                  | Enables consistent @ usage  |
| **Documentation**   | ✅ Change logs and architecture reviews stored          | Traceable across services   |

---

## 🧩 10. Summary: How Each Layer Works Together

| Layer                 | Purpose                           | Invoked By                | Reviewed By          |
| --------------------- | --------------------------------- | ------------------------- | -------------------- |
| **System Prompts**    | Define Copilot’s functional roles | Developer / Architect     | Solution Architect   |
| **Developer Prompts** | Inject tech-specific rules        | Auto-included             | Tech Lead            |
| **Guidelines**        | Enforce enterprise rules          | Referenced implicitly     | Architecture Board   |
| **Instructions**      | Set universal defaults            | Auto-applied              | Governance Office    |
| **Metadata**          | Trace and version control         | Architecture Review Board | Enterprise Architect |

---

## 🧰 11. Optional Enhancement (Enterprise-Scale)

Add an **“Architecture Conformance Testing”** step:
Use custom GHCP prompts + OpenAI API via CI/CD to **auto-validate PRs** against the rules defined in `.github/prompts`.

This ensures:

* 100% Copilot-generated code adheres to your architectural principles.
* Deviations are flagged automatically.

---

Would you like me to generate this **entire `.github/prompts` folder tree (with markdown templates pre-filled)** in a downloadable ZIP (enterprise-ready, GHCP-compatible, with alias mapping and governance files)?
It will be structured for direct review by an Enterprise Architect and deployable in your Azure DevOps / GitHub enterprise repositories.

Your enterprise-grade **GHCP prompt system folder** has been created successfully. You can download it here:

📦 [Download ghcp_enterprise_prompts.zip](sandbox:/mnt/data/ghcp_enterprise_prompts.zip)

This ZIP includes:

* ✅ **System** orchestration and prompt resolution logic
* ✅ **Developer** prompt templates for codegen, reviews, and CI/CD
* ✅ **Guidelines** for enterprise prompt authoring
* ✅ **Patterns** (GoF + architecture)
* ✅ **Reviews** (code, security, architecture)
* ✅ **Testcase** generation with xUnit
* ✅ **Azure CI/CD pipeline** generation prompt

Would you like me to include **Python prompt templates** (for data scripts, AI agents, or Terraform automation) next?

