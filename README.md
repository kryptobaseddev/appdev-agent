# AppDev Project Agent Setup Guide

## Overview

This guide explains how to set up an AppDev project agent using Claude Projects. The agent will use a collection of template files to guide the development process through seven critical phases.

## File Structure

The setup consists of two main components:

1. Custom Instructions (`AppDevInitialInstructions.md`)
2. Context Knowledge Templates:
   - `devAgentBehaviorInstructions.md`
   - `devGuidelines.md`
   - `devDocDirectives.md`
   - `devBackendStructure.md`
   - `devDatabase.md`
   - `devFrontendStructure.md`
   - `devCursorRules.md`

## Setup Process

### 1. Create Claude Project

1. Open Claude and create a new project
2. Name it "AppDev Project Generator"
3. Add the custom instructions and context files

### 2. Custom Instructions Setup

Add `AppDevInitialInstructions.md` to the project's custom instructions. This file defines:

```markdown:AppDevInitialInstructions.md
startLine: 1
endLine: 17
```

### 3. Context Knowledge Setup

Add the following template files to the project's context:

#### Agent Behavior Template

- File: `devAgentBehaviorInstructions.md`
- Purpose: Defines how the AI agent should interact with the project
- Reference:

#### Development Guidelines Template

- File: `devGuidelines.md`
- Purpose: Provides structure for creating development standards
- Reference:

#### Documentation Directives Template

- File: `devDocDirectives.md`
- Purpose: Guides the creation of comprehensive documentation
- Reference:

#### Backend Structure Template

- File: `devBackendStructure.md`
- Purpose: Defines backend architecture and Supabase integration
- Reference:

#### Database Structure Template

- File: `devDatabase.md`
- Purpose: Provides SQL schema and database configuration templates
- Reference:

#### Frontend Structure Template

- File: `devFrontendStructure.md`
- Purpose: Defines frontend architecture and component structure
- Reference:

#### Cursor Rules Template

- File: `devCursorRules.md`
- Purpose: Defines IDE configuration and development standards
- Reference:

## Using the AppDev Agent

1. **Initialization**
   - Start a conversation with the agent
   - Provide your application concept
   - The agent will guide you through the seven phases

2. **Development Phases**

   ```markdown
   Phase 1: Development Documentation
   Phase 2: Development Guidelines
   Phase 3: Frontend Structure
   Phase 4: Backend Structure
   Phase 5: Database Structure
   Phase 6: Cursor Rules
   Phase 7: Agent Behavior Instructions
   ```

3. **Output Files**

   The agent will generate:
   - `development-documentation.md`
   - `development-guidelines.md`
   - `frontend-structure.md`
   - `backend-structure.md`
   - `database.sql`
   - `.cursorrules`
   - `agent-behavior-instructions.md`

## Best Practices

1. **Project Organization**
   - Keep all generated files in a dedicated project folder
   - Maintain version control for the generated documentation
   - Review and validate each phase before proceeding

2. **Communication**
   - Be specific with your application requirements
   - Ask for clarification when needed
   - Provide feedback on generated documentation

3. **Quality Assurance**
   - Verify cross-document consistency
   - Validate technical specifications
   - Test database schemas
   - Review security implementations

## Troubleshooting

If you encounter issues:

1. Verify all template files are properly added to the project
2. Ensure custom instructions are correctly set
3. Check for any conflicts between different documentation sections
4. Request clarification from the agent about specific sections

## Maintenance

1. **Regular Updates**
   - Review and update templates as needed
   - Keep documentation in sync with project evolution
   - Maintain version history of generated files

2. **Version Control**
   - Use Git for tracking documentation changes
   - Follow the commit guidelines in the cursor rules
   - Maintain a changelog for major updates

## Security Considerations

1. Ensure sensitive information is not included in documentation
2. Follow security best practices defined in templates
3. Validate security implementations in generated code
4. Review access controls and authentication flows

This README provides a foundation for setting up and using the AppDev project agent. Follow these guidelines to ensure consistent and high-quality project documentation and implementation.