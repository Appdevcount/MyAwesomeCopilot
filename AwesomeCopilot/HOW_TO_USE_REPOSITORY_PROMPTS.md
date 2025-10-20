# Using GitHub Copilot Prompts from Repository

This guide shows how to use the prompts available in the repository for different development scenarios.

## Understanding Prompt Types

In this repository, prompts are organized in the `prompts/` directory and typically have the `.prompt.md` extension. Here's how to use them effectively.

## How to Use Repository Prompts

### 1. Basic Command Structure
```
/prompt [prompt-name]
```
or
```
@ [prompt-name]
```

### 2. Using Solution Discussion Prompts
```
/prompt solution-discussion
```
Use this prompt when you need to:
- Analyze technical solutions
- Discuss implementation approaches
- Evaluate trade-offs between different options
- Plan implementation strategy

### 3. Using System Design Chat Mode
```
/chat mode system-design-discussion
```
Ideal for:
- Architectural decisions
- System design discussions
- Scalability planning
- Component interaction design

## Common Prompt Usage Scenarios

### Architecture and Design

1. **Blueprint Mode Usage**
```
/prompt blueprint-mode
Context: Creating a new retail POS system
Requirements:
- Clean Architecture
- DDD principles
- Microservices approach
```

2. **Architecture Decision Records**
```
/prompt adr-template
Project: Retail POS System
Decision: Database Technology Selection
Options:
- SQL Server
- PostgreSQL
Considerations:
- Scalability
- Cost
- Performance
```

### Development Workflows

1. **Code Review**
```
/prompt code-review
Type: Pull Request Review
Focus:
- Security practices
- Performance
- Clean code
- Best practices
```

2. **Implementation Planning**
```
/prompt implementation-plan
Feature: Shopping Cart Module
Requirements:
- Real-time inventory check
- Price calculations
- Discount handling
```

### Testing and Quality

1. **Test Planning**
```
/prompt test-plan
Component: Inventory Management
Scope:
- Unit tests
- Integration tests
- Performance tests
```

2. **Security Review**
```
/prompt security-review
Module: Payment Processing
Concerns:
- Data encryption
- Input validation
- Authorization
```

## Repository-Specific Prompts Directory Structure

```
prompts/
├── architecture/
│   └── suggest-architecture.prompt.md
├── development/
│   └── implement-feature.prompt.md
├── review/
│   └── code-review.prompt.md
└── testing/
    └── create-tests.prompt.md
```

## Examples for Different Development Phases

### 1. Starting a New Project

```
/prompt new-project
Project: Retail POS System
Architecture: Clean Architecture with DDD
Tech Stack:
- .NET 8 API
- React Frontend
- SQL Server Database
```

### 2. Feature Implementation

```
/prompt implement-feature
Feature: Shopping Cart
Requirements:
- Add/Remove items
- Update quantities
- Calculate totals
- Check inventory
```

### 3. Code Review

```
/prompt review-code
Module: Payment Processing
Focus Areas:
- Security
- Performance
- Error handling
```

### 4. Testing

```
/prompt create-tests
Component: Order Processing
Test Types:
- Unit tests
- Integration tests
- E2E tests
```

## Best Practices for Repository Prompts

1. **Start with Context**
```
/prompt [prompt-name]
Context:
- Project: [project-name]
- Module: [module-name]
- Current Phase: [phase]
```

2. **Specify Requirements**
```
/prompt [prompt-name]
Requirements:
1. Functional:
   - Requirement 1
   - Requirement 2
2. Non-Functional:
   - Performance
   - Security
```

3. **Include Constraints**
```
/prompt [prompt-name]
Constraints:
- Technical limitations
- Business rules
- Time constraints
```

## Using Prompts for Different Roles

### 1. For Architects
```
/prompt architecture-review
System: Retail POS
Focus:
- Scalability
- Performance
- Security
- Integration patterns
```

### 2. For Developers
```
/prompt implement-component
Component: Inventory Management
Details:
- Business rules
- Data models
- API endpoints
```

### 3. For Reviewers
```
/prompt review-checklist
Type: Security Review
Areas:
- Authentication
- Authorization
- Data protection
```

## Tips for Effective Prompt Usage

1. **Be Specific**
   - Include clear requirements
   - Specify desired outcomes
   - List any constraints

2. **Provide Context**
   - Project background
   - Current state
   - Target state

3. **Progressive Enhancement**
   - Start with basic requirements
   - Add complexity gradually
   - Validate each step

## Common Workflows

### 1. Feature Development Workflow
```
Step 1: /prompt design-feature
Step 2: /prompt implement-feature
Step 3: /prompt create-tests
Step 4: /prompt review-code
```

### 2. Architecture Review Workflow
```
Step 1: /prompt architecture-analysis
Step 2: /prompt identify-patterns
Step 3: /prompt document-decisions
Step 4: /prompt review-architecture
```

### 3. Quality Assurance Workflow
```
Step 1: /prompt test-strategy
Step 2: /prompt security-review
Step 3: /prompt performance-review
Step 4: /prompt documentation-review
```

## Remember

1. Always check the prompt documentation in the repository
2. Use the most specific prompt for your needs
3. Provide clear context and requirements
4. Follow the progressive enhancement approach
5. Validate outputs against requirements

This guide provides a structured approach to using the prompts available in this repository. Adjust the usage patterns based on your specific needs while maintaining the recommended practices for clear and effective communication with GitHub Copilot.