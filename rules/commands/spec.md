# /spec - Requirements Documentation

The user wants to create requirements documentation for: $ARGUMENTS

You are tasked with creating structured requirements documentation based on the above feature request. This is the first phase of a three-part documentation process (Requirements → Design → Tasks).

## Your Tasks

### 1. Analyze the Feature Request
Based on the user's request above, ask targeted questions to understand:
- Core functionality and expected outcomes
- Users and stakeholders
- Technical constraints and performance needs
- Scope boundaries and future considerations
- Integration requirements and dependencies
- Data handling and security needs
- Success criteria and metrics

### 2. Create Requirements Document (in User's Language)
Generate `specs/[feature-name]/requirements.md` in the user's language with:
- **Introduction**: Overview, context, and key functionality
- **Requirements**: User stories with acceptance criteria
  - Format: `As a [user], I want [feature], so that [benefit]`
  - WHEN/THEN criteria for testable requirements
  - IF/THEN for exception handling

### 3. Requirement Notation
- SHALL = mandatory
- SHOULD = recommended
- Each requirement has 2-5 acceptance criteria
- All criteria must be specific and testable

### 4. Get User Approval
After creating requirements.md:
1. Show the created requirements.md to the user
2. Ask for their approval or feedback
3. Make any requested modifications
4. Once approved, translate the document to English if it was written in another language

## After User Approval
1. If the document was written in a non-English language:
   - Copy the approved document to `human-docs/[feature-name]/requirements.md` to preserve the user's language version
   - Then translate the document in `specs/[feature-name]/requirements.md` to English
2. Inform the user that the approved requirements.md has been finalized
3. Suggest running `/design specs/[actual-path]/requirements.md` to proceed to design phase
4. Replace [actual-path] with the actual directory name you used

## When specs/[name] Directory Already Exists
Ask the user whether to:
  - Overwrite existing documentation
  - Create versioned directory
  - Resume from last document
  - Cancel operation