# /design - Technical Design Documentation

Document directory: specs/$ARGUMENTS

You are tasked with creating technical design documentation based on the requirements document at the path specified above. This is the second phase of the documentation process (Requirements → Design → Tasks).

## Your Tasks

### 1. Analyze Requirements
You must:
- Read and analyze the requirements document
- Identify technical components needed
- Determine appropriate architecture patterns
- Consider non-functional requirements

### 2. Create Design Document (in User's Language)
Generate `design.md` in the same directory as requirements.md, using the user's language, with:

#### Structure
1. **Overview**: Technical approach and key design decisions
2. **Architecture**: System layers and responsibilities
   - Technology stack (frameworks, libraries, tools)
3. **Components and Interfaces**: Core components with TypeScript interfaces
4. **Data Models**: Type definitions and relationships
5. **Processing Pipeline**: Major workflows and algorithms
6. **Error Handling**: Error categories and strategies
7. **Testing Strategy**: 
   - Logic/Business logic: Test-Driven Development (TDD) - Write tests first, then implement to pass tests
   - UI Components: Manual verification and human approval for behavior testing
   - Complex integration tests: Not performed
8. **Performance Considerations**: Optimization and scalability

### 3. Design Guidelines
- Include concrete technical details
- Reference specific technologies
- Provide code examples for interfaces
- Address all requirements from requirements.md
- Consider edge cases and failure scenarios

### 4. Get User Approval
After creating design.md:
1. Show the created design.md to the user
2. Ask for their approval or feedback
3. Make any requested modifications

## After User Approval
1. Inform the user that the approved design.md has been finalized
2. Suggest running `/task [feature-name]` to proceed to task creation
3. Replace [feature-name] with the actual directory name used

## Validation
- Ensure requirements.md exists before proceeding
- Verify all requirements are addressed in design
- Maintain traceability between requirements and design elements