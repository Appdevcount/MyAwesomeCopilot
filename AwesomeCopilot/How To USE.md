Here’s how chat modes in the github/awesome-copilot repo relate to the instruction, collection, and prompt files, and how they work together:

## 1. Repository Structure & File Types

From the README.md:
````markdown
├── prompts/          # Task-specific prompts (.prompt.md)
├── instructions/     # Coding standards and best practices (.instructions.md)
├── chatmodes/        # AI personas and specialized modes (.chatmode.md)
├── collections/      # Curated collections of related items (.collection.yml)
└── scripts/          # Utility scripts for maintenance
````

### - .chatmode.md (Chat Modes)
- These files define specialized AI behaviors or personas for Copilot Chat.
- Example: “reviewer.chatmode.md” for reviewing code, “architect.chatmode.md” for architecture guidance.
- Chat modes can reference or bundle related prompts and instructions for richer context.

### - .prompt.md (Prompts)
- Ready-to-use templates for specific coding tasks or developer workflows.
- Prompts can be called directly in VS Code Copilot Chat via “/prompt-name”.

### - .instructions.md (Instructions)
- Set standards, best practices, or coding styles.
- Instructions can inform chat modes and prompts about project or org conventions.

### - .collection.yml (Collections)
- Curated groups of prompts, chat modes, and instructions organized by workflow or use case.
- Example: a “Frontend Web Development” collection might bundle React prompts, frontend instructions, and a frontend-focused chatmode.

## 2. How Chat Modes Use Other Files

- Chat modes are designed to work with related prompts and instructions.
- Collections act as bundles that bring together chat modes, prompts, and instructions for a targeted workflow.
- Example from a .collection.yml template:
    ```yaml
    items:
      - path: prompts/my-prompt.prompt.md
        kind: prompt
      - path: instructions/my-instructions.instructions.md  
        kind: instruction
      - path: chatmodes/my-chatmode.chatmode.md
        kind: chat-mode
    ```

- Chat modes may specify recommended prompts/instructions directly in their YAML frontmatter or usage guidance.

## 3. How They Interact in Practice

- A user installs a chat mode (e.g., “debugging.chatmode.md”).
- The chat mode may recommend or be bundled with relevant prompts (e.g., “debug-issue.prompt.md”) and instructions (e.g., “testing.instructions.md”).
- Collections help users discover and install all related assets for a workflow at once.

## 4. Code & Usage Documentation

- The update-readme.js script auto-generates documentation for all prompts, instructions, chat modes, and collections.
- Prompts like suggest-awesome-github-copilot-collections.prompt.md describe a process for fetching and suggesting collections based on current repo assets, scanning for relevant prompt, instruction, and chatmode files.
- CONTRIBUTING.md and instructions/prompt.instructions.md explain best practices for linking and composing these files.

---

**Summary Table**

| File Type        | Role                                        | How Chat Modes Use Them                               |
|------------------|---------------------------------------------|-------------------------------------------------------|
| .chatmode.md     | Persona/behavior for Copilot Chat           | May reference prompts/instructions, used in collections |
| .prompt.md       | Task templates for chat/commands            | Used directly or via chat modes/collections            |
| .instructions.md | Best practices/coding standards             | Used by chat modes/prompts to enforce standards        |
| .collection.yml  | Bundles of the above for workflows          | Brings together chat modes, prompts, instructions      |

**In summary:**  
Chat modes are specialized personas or workflows that can leverage prompts (for specific actions) and instructions (for standards/guidance). Collections are curated sets that bundle these assets for streamlined use in Copilot Chat.

If you want to see examples or relationships from specific files, let me know!


# Retail POS Application Development Guide using GitHub Copilot Chat Modes

This guide provides a comprehensive reference for developing a retail POS application using various GitHub Copilot chat modes available in the repository.

## Table of Contents
- [Architecture and Planning](#architecture-and-planning)
- [Backend Development](#backend-development)
- [Frontend Development](#frontend-development)
- [Database Design](#database-design)
- [Code Quality and Security](#code-quality-and-security)
- [Documentation](#documentation)
- [Infrastructure and DevOps](#infrastructure-and-devops)

## Architecture and Planning

### Initial System Design
Primary Chat Mode: `principal-software-engineer.chatmode.md`
```plaintext
Use for:
- Overall system architecture
- Component interaction design
- Scalability planning
- Performance considerations
```

### Cloud Architecture
Primary Chat Mode: `azure-principal-architect.chatmode.md`
```plaintext
Use for:
- Cloud service selection
- Resource planning
- Integration patterns
- Scalability strategies
```

## Backend Development

### .NET API Development
Primary Chat Mode: `expert-dotnet-software-engineer.chatmode.md`
```plaintext
Use for:
- Domain model implementation
- Application layer development
- Infrastructure setup
- API endpoint design
```

Supporting Chat Modes:
- `blueprint-mode.chatmode.md` for initial project setup
- `implementation-plan.chatmode.md` for structured development
- `principal-software-engineer.chatmode.md` for architectural decisions

### DDD and Clean Architecture
Workflow:
1. Start with `blueprint-mode.chatmode.md`:
   - Project structure setup
   - Layer separation
   - Initial scaffolding

2. Switch to `expert-dotnet-software-engineer.chatmode.md`:
   - Domain model implementation
   - Repository patterns
   - Service layer development

3. Use `principal-software-engineer.chatmode.md`:
   - Pattern implementation review
   - Architecture compliance
   - Best practices validation

## Frontend Development

### React Enterprise Application
Primary Chat Mode: `expert-react-frontend-engineer.chatmode.md`
```plaintext
Use for:
- Component architecture
- State management
- API integration
- Performance optimization
```

Development Workflow:
1. Initial Setup (`blueprint-mode.chatmode.md`):
   - Project scaffolding
   - Dependency setup
   - Basic configuration

2. Component Development (`expert-react-frontend-engineer.chatmode.md`):
   - Component hierarchy
   - State management implementation
   - API integration patterns

3. Implementation Planning (`implementation-plan.chatmode.md`):
   - Feature roadmap
   - Component specifications
   - Testing strategy

## Database Design

### SQL Server Development
Primary Chat Mode: `ms-sql-dba.chatmode.md`
```plaintext
Use for:
- Schema design
- Table creation
- Stored procedure development
- Index optimization
```

Supporting Chat Mode: `principal-software-engineer.chatmode.md`
```plaintext
Use for:
- Data modeling
- Performance considerations
- Integration patterns
```

## Code Quality and Security

### Code Review Process
Primary Chat Modes:
1. `csharp-dotnet-janitor.chatmode.md`:
   - Code quality checks
   - Best practices compliance
   - Performance optimization

2. `critical-thinking.chatmode.md`:
   - Security analysis
   - Vulnerability assessment
   - Risk evaluation

3. `address-comments.chatmode.md`:
   - PR review responses
   - Code improvement suggestions
   - Documentation updates

### Security Review Workflow
1. Use `critical-thinking.chatmode.md`:
   ```plaintext
   - Authentication review
   - Authorization checks
   - Input validation
   - Data protection measures
   ```

2. Use `janitor.chatmode.md`:
   ```plaintext
   - Code smell detection
   - Security best practices
   - Performance implications
   ```

## Documentation

### Technical Documentation
Primary Chat Mode: `specification.chatmode.md`
```plaintext
Use for:
- API documentation
- Component specifications
- Integration guides
- Architecture Decision Records (ADRs)
```

### User Documentation
Primary Chat Mode: `microsoft_learn_contributor.chatmode.md`
```plaintext
Use for:
- README files
- User guides
- API usage examples
- Configuration guides
```

## Infrastructure and DevOps

### Azure Infrastructure
Primary Chat Mode: `azure-verified-modules-terraform.chatmode.md`
```plaintext
Use for:
- Infrastructure as Code
- Resource provisioning
- Environment configuration
- Deployment pipelines
```

### Containerization
Primary Chat Mode: `azure-saas-architect.chatmode.md`
```plaintext
Use for:
- Container architecture
- Docker configuration
- Service orchestration
- Scaling strategies
```

## Best Practices for Chat Mode Usage

1. **Sequential Progression**:
   - Start with architecture and planning chat modes
   - Move to implementation-specific modes
   - Finish with review and documentation modes

2. **Combine Chat Modes**:
   - Use principal-software-engineer for overall guidance
   - Switch to specialized modes for specific tasks
   - Return to review modes for validation

3. **Iterative Development**:
   - Use implementation-plan mode for feature planning
   - Switch to specialized modes for development
   - Use review modes for quality assurance

4. **Documentation Integration**:
   - Document decisions using specification mode
   - Create user guides with microsoft_learn_contributor
   - Maintain technical documentation throughout development

## Conclusion

This reference guide provides a structured approach to using GitHub Copilot chat modes for developing a retail POS application. Follow the recommended workflows and combinations of chat modes to ensure high-quality, secure, and well-documented development process.

├── prompts/          # Task-specific prompts (.prompt.md)
├── instructions/     # Coding standards and best practices (.instructions.md)
├── chatmodes/        # AI personas and specialized modes (.chatmode.md)
├── collections/      # Curated collections of related items (.collection.yml)
└── scripts/          # Utility scripts for maintenance