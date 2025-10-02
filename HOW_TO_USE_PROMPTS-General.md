# GitHub Copilot Prompts Usage Guide

This guide demonstrates how to effectively use prompts with GitHub Copilot for various development scenarios. Each section includes the exact commands and prompt patterns to use.

## How to Use Prompts

Prompts can be used in three ways:
1. Inline comments in code
2. Direct questions to Copilot
3. Context-setting blocks

## Code Generation Prompts

### Domain Model Generation

1. **Entity Creation**
```csharp
// @prompt: Create a Product entity for a retail POS system with the following properties:
// - SKU (string)
// - Name (string)
// - Price (decimal)
// - Category (enum)
// - Stock level (int)
// Include data annotations and implement value object patterns
public class Product
```

2. **Service Implementation**
```csharp
// @prompt: Implement an inventory service with the following requirements:
// - Check stock availability
// - Reserve inventory
// - Release reserved inventory
// - Update stock levels
// Use DDD patterns and include error handling
public class InventoryService
```

### API Endpoint Design

1. **Controller Creation**
```csharp
// @prompt: Create a RESTful API controller for managing sales with the following endpoints:
// - Create new sale
// - Get sale by ID
// - Get sales by date range
// - Update sale status
// Include proper response types and error handling
[ApiController]
public class SalesController
```

### React Component Design

1. **Component Structure**
```typescript
// @prompt: Create a React component for a product catalog with:
// - Grid layout
// - Search functionality
// - Filtering by category
// - Sorting options
// Use TypeScript and include proper prop types
interface ProductCatalogProps {
```

2. **Custom Hook**
```typescript
// @prompt: Create a custom hook for managing shopping cart with:
// - Add to cart
// - Remove from cart
// - Update quantity
// - Calculate totals
// Include proper TypeScript types and error handling
const useShoppingCart = () => {
```

## Database Design Prompts

### Table Creation

```sql
-- @prompt: Create SQL tables for a retail POS system with:
-- - Products table
-- - Inventory table
-- - Sales table
-- - Customers table
-- Include proper relationships, indexes, and constraints
CREATE TABLE Products
```

### Stored Procedure Design

```sql
-- @prompt: Create a stored procedure for processing sales that:
-- - Validates inventory
-- - Updates stock levels
-- - Records the sale
-- - Handles errors and rollbacks
CREATE PROCEDURE ProcessSale
```

## Infrastructure Prompts

### Terraform Configuration

```hcl
# @prompt: Create Terraform configuration for:
# - App Service Plan
# - Azure SQL Database
# - Application Insights
# - Key Vault
# Include proper naming conventions and tags
resource "azurerm_resource_group" "pos_system" {
```

### Docker Configuration

```dockerfile
# @prompt: Create a Dockerfile for:
# - .NET 8 API application
# - Multi-stage build
# - Security best practices
# - Health checks
# Base image selection and optimization
FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS base
```

## Testing Prompts

### Unit Tests

```csharp
// @prompt: Create unit tests for the InventoryService:
// - Test stock availability check
// - Test reservation process
// - Test concurrent reservations
// - Test error conditions
// Use xUnit and follow AAA pattern
public class InventoryServiceTests
```

### Integration Tests

```csharp
// @prompt: Create integration tests for the sales process:
// - Test end-to-end sale creation
// - Test inventory updates
// - Test concurrent sales
// - Test error scenarios
// Use WebApplicationFactory and in-memory database
public class SalesIntegrationTests
```

## Best Practices for Prompts

### 1. Context Setting

Always start with clear context:
```
// @prompt: Context: Retail POS system
// Architecture: Clean Architecture with DDD
// Current component: Sales processing
// Task: Implement sale completion logic
```

### 2. Requirement Specification

Break down requirements clearly:
```
// @prompt: Requirements:
// 1. Input validation
// - Valid product IDs
// - Non-negative quantities
// - Valid payment information
// 2. Business rules
// - Check inventory availability
// - Calculate totals with tax
// 3. Error handling
// - Insufficient inventory
// - Payment processing failures
```

### 3. Pattern Requirements

Specify patterns and practices:
```
// @prompt: Implement using:
// - Repository pattern
// - Unit of Work
// - CQRS pattern
// - Event-driven updates
```

### 4. Progressive Enhancement

Start simple and add complexity:
```
// @prompt: Phase 1: Basic implementation
// Then: Add validation
// Then: Add error handling
// Then: Add logging and monitoring
```

## Tips for Effective Prompt Usage

1. **Be Specific and Clear**
```
// @prompt: Create a method that:
// Input: ProductId (string), Quantity (int)
// Output: ReservationResult (success/failure with reason)
// Behavior: Attempts to reserve inventory
```

2. **Include Constraints**
```
// @prompt: Implementation constraints:
// - Must be thread-safe
// - Maximum timeout: 5 seconds
// - Retry policy: 3 attempts
// - Logging: Required for all failures
```

3. **Request Variations**
```
// @prompt: Show alternative implementations:
// 1. Using async/await
// 2. Using TPL
// 3. Using reactive patterns
```

4. **Ask for Explanations**
```
// @prompt: Explain the implementation:
// - Why specific patterns were chosen
// - Performance implications
// - Security considerations
// - Testing approach
```

## Common Prompt Patterns

1. **Feature Implementation**
```
// @prompt: Feature: [Feature Name]
// Requirements:
// - Requirement 1
// - Requirement 2
// Constraints:
// - Constraint 1
// - Constraint 2
// Expected Behavior:
// - Behavior 1
// - Behavior 2
```

2. **Code Review**
```
// @prompt: Review this implementation for:
// - Clean code principles
// - Performance optimizations
// - Security vulnerabilities
// - Testing coverage
```

3. **Refactoring**
```
// @prompt: Refactor this code to:
// - Improve readability
// - Enhance maintainability
// - Optimize performance
// - Follow [specific pattern]
```

Remember:
- Keep prompts focused and specific
- Include necessary context
- Specify constraints and requirements
- Ask for explanations when needed
- Use progressive enhancement for complex features

This guide provides a structured approach to using prompts effectively with GitHub Copilot. Adapt these patterns to your specific needs while maintaining clarity and specificity in your prompts.