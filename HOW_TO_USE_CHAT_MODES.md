# How to Use GitHub Copilot Chat Modes - Practical Guide

This guide demonstrates the exact commands and prompts to use with GitHub Copilot Chat modes for developing applications.

## Solution Design & Architecture

1. Start a system design discussion:
```
/chat mode system-design-discussion
I need to design a scalable microservices architecture for a new e-commerce platform. Key requirements include high availability, eventual consistency, and support for real-time inventory updates.
```

2. Discuss implementation solutions:
```
/prompt solution-discussion
What's the best approach to implement real-time inventory synchronization across multiple microservices while maintaining consistency?
```

## Initial Setup

1. First, activate the principal architect mode:
```
/chat mode azure-principal-architect
Hello! I'm starting a new retail POS application. I need help with initial architecture planning. The system needs to handle inventory, sales, customer management, and reporting.
```

2. Switch to implementation planning:
```
/chat mode implementation-plan
Based on the architecture discussion, help me create a detailed implementation plan for the retail POS system with priorities and milestones.
```

## Backend Development

### Setting up .NET API with DDD

1. Start with blueprint mode:
```
/chat mode blueprint-mode
Create a new .NET Core API project structure following DDD and Clean Architecture for a retail POS system. Include domain, application, infrastructure, and API layers.
```

2. Switch to .NET expert mode for implementation:
```
/chat mode expert-dotnet-software-engineer
I need to implement the following domain entities for the retail POS system:
1. Product
2. Inventory
3. Sale
4. Customer
Please help with the domain models following DDD principles.
```

3. For domain services:
```
/chat mode expert-dotnet-software-engineer
Help me implement domain services for:
1. Inventory management
2. Sales processing
3. Customer management
Include domain events and ensure proper encapsulation.
```

## Frontend Development

1. Start React project setup:
```
/chat mode expert-react-frontend-engineer
I need to set up a new React frontend for a retail POS system. Include:
- TypeScript configuration
- State management setup (Redux/Context)
- Routing structure
- Component hierarchy plan
```

2. For component development:
```
/chat mode expert-react-frontend-engineer
Help me create the following components for the POS system:
1. Product catalog with search and filters
2. Shopping cart with real-time updates
3. Checkout process flow
4. Inventory management dashboard
```

## Database Design

1. Database architecture:
```
/chat mode ms-sql-dba
Design the database schema for a retail POS system including:
1. Products and inventory tracking
2. Sales and transactions
3. Customer management
4. Reporting tables
Include proper relationships and indexing strategy.
```

2. For stored procedures:
```
/chat mode ms-sql-dba
Create stored procedures for:
1. Processing new sales
2. Updating inventory levels
3. Generating daily sales reports
Include error handling and transaction management.
```

## Code Review and Security

1. Code review:
```
/chat mode csharp-dotnet-janitor
Review the following aspects of my POS application:
1. API endpoint security
2. Data validation
3. Error handling
4. Performance optimization
```

2. Security analysis:
```
/chat mode critical-thinking
Perform a security analysis of the POS system focusing on:
1. Authentication implementation
2. Authorization rules
3. Data protection
4. API security
```

## Documentation

1. Technical documentation:
```
/chat mode specification
Help me create technical documentation for:
1. API endpoints
2. Database schema
3. Authentication flow
4. Deployment process
```

2. User guide:
```
/chat mode microsoft_learn_contributor
Create user documentation for:
1. System overview
2. Installation guide
3. Configuration steps
4. Troubleshooting guide
```

## Infrastructure Setup

1. Azure infrastructure:
```
/chat mode azure-verified-modules-terraform
Help me create Terraform configurations for:
1. App Service for API
2. SQL Database
3. Storage accounts
4. Application Insights
Include best practices for production deployment.
```

2. Containerization:
```
/chat mode azure-saas-architect
Help me containerize the POS application:
1. Dockerfile for API
2. Dockerfile for frontend
3. Docker Compose setup
4. Container registry configuration
```

## Architecture Review

```
/chat mode principal-software-engineer
Review the complete architecture focusing on:
1. Scalability
2. Performance
3. Maintainability
4. Security
Provide recommendations for improvements.
```

## Design Patterns Implementation

```
/chat mode principal-software-engineer
Help me implement appropriate design patterns for:
1. Order processing pipeline
2. Inventory management
3. Payment processing
4. Event handling
```

## Best Practices for Chat Interactions

1. **Be Specific**: Always provide clear context and requirements in your prompts.

2. **Iterative Approach**: Break down complex tasks into smaller chunks:
```
/chat mode expert-dotnet-software-engineer
Let's implement the order processing feature:
Step 1: Create the Order domain model
```
Then:
```
Next step: Implement the OrderService
```

3. **Request Reviews**: After implementation:
```
/chat mode critical-thinking
Review the implementation of [feature] focusing on security and best practices.
```

4. **Documentation Updates**: After major changes:
```
/chat mode specification
Update the technical documentation for the recent changes in [feature].
```

## Tips for Effective Usage

1. **Start Each Session with Context**:
```
/chat mode [selected-mode]
I'm working on the retail POS system. Previous task: [previous task]. Current goal: [current goal].
```

2. **Switch Modes When Needed**:
```
/chat mode [new-mode]
Continuing from previous discussion about [topic], now I need to [new task].
```

3. **Request Validations**:
```
/chat mode principal-software-engineer
Validate my implementation of [feature] against our architectural principles and patterns.
```

Remember to:
- Always provide context when switching chat modes
- Break down complex tasks into smaller chunks
- Request reviews and validations regularly
- Keep documentation updated as you progress

This guide provides practical examples of how to interact with different chat modes. Adjust the prompts based on your specific needs while maintaining the structured approach to development.