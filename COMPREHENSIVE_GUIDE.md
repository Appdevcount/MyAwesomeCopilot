# Comprehensive GitHub Copilot Usage Guide

This guide consolidates all usage patterns for GitHub Copilot, including chat modes, prompts, and repository-based interactions.

## Table of Contents
1. [Understanding Interaction Types](#understanding-interaction-types)
2. [Chat Modes](#chat-modes)
3. [General Prompts](#general-prompts)
4. [Repository-Based Prompts](#repository-based-prompts)
5. [Development Workflows](#development-workflows)
6. [Advanced Usage](#advanced-usage)

## Understanding Interaction Types

You can interact with GitHub Copilot in three primary ways:
1. Chat modes for specialized conversations
2. General prompts for specific tasks
3. Repository-based prompts for standardized workflows

## Chat Modes

### System Design & Architecture
```
/chat mode system-design-discussion
```
Use this mode for:
- Scalable architecture design
- System component planning
- Integration patterns
- Performance considerations

### Azure Principal Architect
```
/chat mode azure-principal-architect
```
Perfect for:
- Cloud architecture planning
- Azure service selection
- Infrastructure design
- Cost optimization

### Implementation Planning
```
/chat mode implementation-plan
```
Helps with:
- Project timelines
- Resource allocation
- Sprint planning
- Milestone definition

### .NET Development
```
/chat mode expert-dotnet-software-engineer
```
Ideal for:
- Domain model design
- API implementation
- Service layer development
- Clean Architecture practices

### Frontend Development
```
/chat mode expert-react-frontend-engineer
```
Specialized for:
- React component design
- State management
- UI/UX implementation
- Frontend architecture

### Database Design
```
/chat mode ms-sql-dba
```
Focused on:
- Schema design
- Query optimization
- Index strategies
- Database administration

## General Prompts

### Solution Discussion
```
/prompt solution-discussion
```
Use for:
- Technical approach analysis
- Implementation strategies
- Trade-off discussions
- Best practice guidance

### Code Generation

#### Domain Models
```csharp
// @prompt: Create a domain entity with:
// - Properties
// - Validation
// - Business rules
```

#### API Controllers
```csharp
// @prompt: Design RESTful endpoints for:
// - CRUD operations
// - Custom actions
// - Response types
```

#### React Components
```typescript
// @prompt: Create components with:
// - Props interface
// - State management
// - Event handlers
```

## Repository-Based Prompts

### Using Prompt Files
```
/prompt [prompt-name]
```
or
```
@ [prompt-name]
```

### Common Scenarios

#### Blueprint Mode
```
/prompt blueprint-mode
```
For:
- Project structure
- Architecture setup
- Initial scaffolding

#### Architecture Decision Records
```
/prompt adr-template
```
Documents:
- Technical decisions
- Considered options
- Implementation impact

#### Code Review
```
/prompt code-review
```
Focuses on:
- Code quality
- Security practices
- Performance aspects
- Best practices

## Development Workflows

### Initial Project Setup
1. Start with architecture planning (azure-principal-architect)
2. Create implementation plan
3. Set up project structure (blueprint-mode)
4. Begin development with specialized modes

### Feature Development
1. Design discussion (system-design-discussion)
2. Implementation approach (solution-discussion)
3. Development using expert modes
4. Code review and testing

### Database Development
1. Schema design (ms-sql-dba)
2. Query optimization
3. Index strategy
4. Performance testing

## Advanced Usage

### Combining Modes
Switch between modes based on the current task:
1. Start with system design
2. Move to implementation details
3. Switch to expert modes for specific tasks

### Best Practices
1. Clearly define requirements before starting
2. Use appropriate mode for each task
3. Maintain context between mode switches
4. Document decisions and rationale

### Tips for Better Results
1. Be specific in requirements
2. Provide relevant context
3. Use appropriate mode for the task
4. Follow up with clarifying questions

## Conclusion

This guide consolidates different ways to interact with GitHub Copilot effectively. Choose the appropriate interaction mode based on your current task and needs. Remember to:
- Use chat modes for specialized conversations
- Apply prompts for specific tasks
- Leverage repository prompts for standardized workflows