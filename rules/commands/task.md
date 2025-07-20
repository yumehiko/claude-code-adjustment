# /task - Implementation Task List

Design document path: $ARGUMENTS

You are tasked with creating actionable implementation tasks based on the design document at the path specified above. This is the final phase of the documentation process (Requirements → Design → Tasks).

## Your Tasks

### 1. Analyze Design
You must:
- Read requirements.md and design.md
- Identify all components to implement
- Determine task dependencies
- Plan implementation order

### 2. Create Tasks Document (in User's Language)
Generate `tasks.md` in the same directory as design.md, using the user's language, with:

#### Task Format
```markdown
- [ ] [Task Number]. [Task Description]
  - [Subtask 1 description]
  - [Subtask 2 description]
  - [Implementation details]
  - Run lint, tests, and build
  - Request UAT if needed
  - _Requirements: [Requirement numbers addressed]_
```

#### Organization
- Infrastructure and setup tasks first
- Core functionality implementation
- UI components
- Integration work
- Testing and optimization last

### 3. Task Guidelines
- **Logic Layer Tasks**: Use TDD approach - write tests first, then implementation
- **UI/Integration Tasks**: One complete unit including manual testing request
- Each task is one atomic unit for coding agent execution
- Start with action verbs (Create, Implement, Build)
- Include specific technical details
- Reference requirement numbers
- Respect dependencies

## Task Management
- Tasks numbered sequentially (1, 2, 3...)
- Subtasks use decimals (1.1, 1.2...)
- Checkbox format for tracking progress
- Mark completed with `[x]` only after:
  - All tests pass (for TDD tasks)
  - Lint and build succeed
  - UAT approved by human (if required)

### 4. Get User Approval
After creating tasks.md:
1. Show the created tasks.md to the user
2. Ask for their approval or feedback
3. Make any requested modifications

## After User Approval
1. If the document was written in a non-English language:
   - Copy the approved document to `human-docs/[feature-name]/tasks.md` to preserve the user's language version
   - Then translate the document in `specs/[feature-name]/tasks.md` to English
2. Inform the user that the approved tasks.md has been finalized
3. Explain that the implementation plan is complete with full requirement traceability
4. Note that each task can be executed independently

## Validation
- Ensure design.md and requirements.md exist
- Verify all design components have tasks
- Maintain requirement traceability
- Check task dependencies are logical