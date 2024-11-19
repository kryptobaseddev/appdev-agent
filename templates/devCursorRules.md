# Complete Instructions for AppDev's .cursorrules File Generation

## Overview
You are responsible for creating exhaustive `.cursorrules` files that will guide Cursor IDE in application implementation. Your rules must cover every aspect of development, from system setup to code completion suggestions.

## Required Document Structure

### 1. System and Role Definition
```
<system_constraints>
  - Full technology stack definition
  - Version requirements
  - Operating parameters
  - Development environment setup
  - IDE configuration
  - Available commands and tools
  - File system access rules
  - Resource limitations
</system_constraints>

<role_definition>
  - Primary expertise areas
  - Knowledge domains
  - Response parameters
  - Interaction style
  - Problem-solving approach
  - Decision-making framework
</role_definition>
```

### 2. Code Standards and Formatting
```
<code_formatting_info>
  - Language-specific formatting rules
  - Project-wide conventions
  - File naming patterns
  - Directory structure requirements
  - Import ordering rules
  - Comment formatting
  - Type definitions format
  - JSDoc requirements
  - Code block structure
  - Error handling patterns
</code_formatting_info>

<style_guides>
  - React component patterns
  - TypeScript usage rules
  - CSS/styling conventions
  - State management patterns
  - Hook implementation rules
  - Performance optimization rules
</style_guides>
```

### 3. Documentation and Communication
```
<message_formatting_info>
  - Documentation style guide
  - Code comment requirements
  - API documentation format
  - Component documentation
  - Function documentation
  - Type documentation
  - Example usage documentation
  - Troubleshooting guides
</message_formatting_info>

<interaction_guidelines>
  - Response format rules
  - Code suggestion format
  - Error message structure
  - Warning message format
  - Success message format
  - Help request handling
  - Clarification request format
</interaction_guidelines>
```

### 4. Development Workflow
```
<workflow_rules>
  - Git workflow requirements
  - Branch naming conventions
  - Commit message format
  - PR template requirements
  - Review process rules
  - Deployment checklist
  - Version control standards
  - Release process
</workflow_rules>

<quality_assurance>
  - Code review standards
  - Testing requirements
  - Coverage requirements
  - Performance benchmarks
  - Security audit rules
  - Accessibility standards
  - Browser compatibility
</quality_assurance>
```

### 5. Architecture and Implementation
```
<architecture_guidelines>
  - Component hierarchy rules
  - State management patterns
  - Data flow patterns
  - API integration patterns
  - Error boundary implementation
  - Performance optimization patterns
  - Security implementation rules
</architecture_guidelines>

<implementation_patterns>
  - Common code patterns
  - Anti-patterns to avoid
  - Optimization techniques
  - Refactoring guidelines
  - Technical debt handling
  - Legacy code migration
</implementation_patterns>
```

### 6. Security and Compliance
```
<security_standards>
  - Authentication requirements
  - Authorization patterns
  - Data encryption rules
  - API security standards
  - Environment variable handling
  - Secret management
  - Security testing requirements
</security_standards>

<compliance_requirements>
  - Code compliance rules
  - Accessibility requirements
  - Data privacy standards
  - Performance requirements
  - Browser compatibility
  - Mobile responsiveness
</compliance_requirements>
```

### 7. Testing and Validation
```
<testing_requirements>
  - Unit test structure
  - Integration test patterns
  - E2E test requirements
  - Test naming conventions
  - Mock data standards
  - Test coverage rules
  - Performance test criteria
</testing_requirements>

<validation_rules>
  - Input validation patterns
  - Data validation rules
  - Form validation requirements
  - API response validation
  - Error handling validation
  - Security validation
</validation_rules>
```

### 8. Environment and Deployment
```
<environment_configuration>
  - Development setup
  - Staging requirements
  - Production rules
  - Environment variables
  - Configuration management
  - Feature flags
  - Deployment procedures
</environment_configuration>

<build_deployment>
  - Build process rules
  - Deployment checklist
  - CI/CD requirements
  - Release procedures
  - Rollback procedures
  - Monitoring setup
  - Performance tracking
</build_deployment>
```

### 9. Error Handling and Logging
```
<error_handling>
  - Error types and categories
  - Error response formats
  - Recovery procedures
  - Fallback implementations
  - Retry strategies
  - Circuit breaker patterns
</error_handling>

<logging_monitoring>
  - Log level definitions
  - Log format requirements
  - Monitoring rules
  - Alert configurations
  - Performance tracking
  - Usage analytics
</logging_monitoring>
```

### 10. Package Management
```
<dependency_management>
  - Package version rules
  - Dependency update process
  - Security audit requirements
  - Version compatibility
  - Package lockfile rules
  - Monorepo guidelines
</dependency_management>
```

## Implementation Process

1. Initial Analysis
   - Review development documentation
   - Extract all technical requirements
   - Identify architectural patterns
   - List security requirements
   - Define performance criteria
   - Map testing requirements
   - Document deployment needs

2. Rule Generation
   - Create exhaustive rules for each section
   - Include specific examples
   - Define validation criteria
   - Specify error handling
   - Document edge cases
   - Provide troubleshooting guides

3. Validation Process
   - Cross-reference with development docs
   - Verify technical accuracy
   - Ensure completeness
   - Validate formatting
   - Test rule clarity
   - Check for conflicts

4. Final Documentation
   - Complete .cursorrules file
   - Include all sections
   - Provide examples
   - Add cross-references
   - Include index
   - Add version history

## Template Format

Each rule section should follow this format:
```
<section_name>
  Description: [Detailed description of the section]
  
  Rules:
    - [Specific rule with explanation]
    - [Implementation requirements]
    - [Validation criteria]
  
  Examples:
    [Concrete examples with code]
    
  Validation:
    - [Validation steps]
    - [Success criteria]
    - [Error handling]
    
  References:
    - [Related documentation]
    - [External resources]
    
  Notes:
    - [Additional considerations]
    - [Edge cases]
    - [Known limitations]
</section_name>
```

## Component Templates

```
<component_templates>
  Description: Standard templates for different types of React components
  
  Base Component Template:
    ```typescript
    import React from 'react';
    import type { FC } from 'react';
    
    interface ComponentProps {
      // Props interface
    }
    
    export const Component: FC<ComponentProps> = ({ prop1, prop2 }) => {
      // Component logic
      return (
        <div>
          {/* Component JSX */}
        </div>
      );
    };
    ```
  
  Rules:
    - All components must use TypeScript
    - Props must have explicit interfaces
    - Use functional components with FC type
    - Include JSDoc documentation
    - Implement error boundaries where needed
    
  Variations:
    - Page Components
    - Form Components
    - List Components
    - Modal Components
    - Layout Components
    
  Examples:
    [Provide specific examples for each variation]
</component_templates>

<custom_hooks>
  Description: Templates for custom React hooks
  
  Base Hook Template:
    ```typescript
    import { useState, useEffect } from 'react';
    
    export const useCustomHook = <T>(param: T) => {
      // Hook logic
      return {
        // Hook return values
      };
    };
    ```
  
  Rules:
    - Start with 'use' prefix
    - Include TypeScript generics
    - Document parameters and return types
    - Implement cleanup when needed
    - Handle loading and error states
    
  Examples:
    [Provide common hook patterns]
</custom_hooks>
```

## Validation Patterns

```
<validation_patterns>
  Description: Standard validation patterns for different data types
  
  Form Validation:
    ```typescript
    const validateForm = (data: FormData): ValidationResult => {
      const errors: ValidationErrors = {};
      
      // Validation logic
      
      return {
        isValid: Object.keys(errors).length === 0,
        errors
      };
    };
    ```
  
  Rules:
    - Type all validation functions
    - Return standardized error objects
    - Include field-level validation
    - Implement async validation
    - Handle all edge cases
    
  Examples:
    - Email validation
    - Password validation
    - Date validation
    - Number validation
    - Custom field validation
</validation_patterns>
```

## Error Handling Scenarios

```
<error_scenarios>
  Description: Comprehensive error handling patterns
  
  API Error Handling:
    ```typescript
    const handleApiError = async (error: unknown): Promise<ErrorResponse> => {
      if (error instanceof NetworkError) {
        // Network error handling
      } else if (error instanceof ValidationError) {
        // Validation error handling
      } else {
        // Generic error handling
      }
    };
    ```
  
  Rules:
    - Type all errors
    - Implement error boundaries
    - Log errors appropriately
    - Provide user feedback
    - Include recovery strategies
    
  Examples:
    - Network errors
    - Validation errors
    - Authentication errors
    - Authorization errors
    - Server errors
</error_scenarios>
```

## Security Implementation Details

```
<security_implementation>
  Description: Comprehensive security patterns and implementations
  
  Authentication Flow:
    ```typescript
    interface AuthConfig {
      supabaseUrl: string;
      supabaseKey: string;
      authRedirect: string;
    }
    
    class AuthService {
      private supabase: SupabaseClient;
      
      constructor(config: AuthConfig) {
        this.supabase = createClient(config.supabaseUrl, config.supabaseKey);
      }
      
      async signIn(credentials: AuthCredentials): Promise<AuthResponse> {
        try {
          const { user, error } = await this.supabase.auth.signIn(credentials);
          if (error) throw new AuthError(error.message);
          return { user, success: true };
        } catch (error) {
          this.handleAuthError(error);
          return { success: false, error };
        }
      }
    }
    ```
  
  Rules:
    - Implement proper token handling
    - Use secure session management
    - Implement CSRF protection
    - Handle OAuth flows securely
    - Implement rate limiting
    - Use proper password hashing
    
  Validation:
    - Test auth flows thoroughly
    - Validate token management
    - Check for security headers
    - Verify CORS settings
    - Test rate limiting
</security_implementation>

## API Security Patterns

```
<api_security>
  Description: Secure API integration patterns
  
  API Client:
    ```typescript
    class SecureApiClient {
      private baseUrl: string;
      private headers: Headers;
      
      constructor(config: ApiConfig) {
        this.baseUrl = config.baseUrl;
        this.headers = this.buildSecureHeaders(config);
      }
      
      private buildSecureHeaders(config: ApiConfig): Headers {
        return {
          'Authorization': `Bearer ${config.token}`,
          'Content-Type': 'application/json',
          'X-CSRF-Token': config.csrfToken,
        };
      }
      
      async request<T>(endpoint: string, options: RequestOptions): Promise<T> {
        try {
          const response = await this.makeRequest(endpoint, options);
          return this.handleResponse<T>(response);
        } catch (error) {
          this.handleError(error);
        }
      }
    }
    ```
  
  Rules:
    - Implement request signing
    - Use proper error handling
    - Implement retry logic
    - Handle rate limiting
    - Secure credential storage
    - Implement request logging
</api_security>
```

## Code Patterns and Best Practices

```
<code_patterns>
  Description: Standard coding patterns and best practices
  
  State Management:
    ```typescript
    interface State {
      data: DataType;
      loading: boolean;
      error: Error | null;
    }
    
    const useDataFetching = <T>(
      fetchFn: () => Promise<T>
    ): State<T> => {
      const [state, setState] = useState<State<T>>({
        data: null,
        loading: false,
        error: null,
      });
      
      useEffect(() => {
        const fetchData = async () => {
          setState(prev => ({ ...prev, loading: true }));
          try {
            const data = await fetchFn();
            setState({ data, loading: false, error: null });
          } catch (error) {
            setState({ data: null, loading: false, error });
          }
        };
        
        fetchData();
      }, [fetchFn]);
      
      return state;
    };
    ```
  
  Rules:
    - Implement proper type safety
    - Handle loading states
    - Implement error states
    - Use proper cleanup
    - Handle race conditions
    
  Patterns:
    - Repository Pattern
    - Observer Pattern
    - Factory Pattern
    - Singleton Pattern
    - Command Pattern
</code_patterns>

## Validation Criteria

```
<validation_criteria>
  Description: Detailed validation requirements for different aspects of the application
  
  Code Quality:
    - Lint rules compliance
    - Type safety
    - Test coverage (minimum 80%)
    - Performance metrics
    - Accessibility standards
    
  Security:
    - Authentication checks
    - Authorization validation
    - Input sanitization
    - XSS prevention
    - CSRF protection
    
  Performance:
    - Load time metrics
    - Bundle size limits
    - Memory usage
    - API response times
    - Animation performance
    
  Accessibility:
    - WCAG compliance
    - Keyboard navigation
    - Screen reader compatibility
    - Color contrast
    - Focus management
</validation_criteria>

## Error Handling Scenarios

```
<error_handling_scenarios>
  Description: Comprehensive error handling patterns for different scenarios
  
  API Errors:
    ```typescript
    class ApiError extends Error {
      constructor(
        public status: number,
        public code: string,
        message: string
      ) {
        super(message);
        this.name = 'ApiError';
      }
    }
    
    const handleApiError = (error: unknown) => {
      if (error instanceof ApiError) {
        switch (error.status) {
          case 401:
            // Handle unauthorized
            break;
          case 403:
            // Handle forbidden
            break;
          case 404:
            // Handle not found
            break;
          default:
            // Handle generic error
        }
      } else {
        // Handle unknown error
      }
    };
    ```
  
  Scenarios:
    - Network failures
    - Authentication errors
    - Authorization errors
    - Validation errors
    - Server errors
    - Timeout errors
    
  Recovery Strategies:
    - Retry logic
    - Fallback content
    - Offline support
    - Error boundaries
    - User feedback
</error_handling_scenarios>
```

## Development Workflow Patterns

```
<development_workflow>
  Description: Standardized development workflow and commit practices
  
  Git Workflow:
    ```bash
    # Branch Naming Convention
    feature/[ticket-number]-brief-description
    bugfix/[ticket-number]-brief-description
    hotfix/[ticket-number]-brief-description
    release/v[version-number]
    
    # Commit Message Format
    type(scope): [ticket-number] description
    
    # Example Commits
    feat(auth): [TASK-123] implement OAuth login flow
    fix(api): [BUG-456] handle timeout errors
    chore(deps): [MAINT-789] update dependencies
    docs(api): [DOC-012] update API documentation
    ```
  
  Rules:
    - Commit frequently (at least every completed unit of work)
    - Use descriptive commit messages
    - Reference ticket numbers in all commits
    - Keep commits focused and atomic
    - Push changes daily
    - Create PRs early (draft if needed)
    
  Commit Types:
    - feat: New features
    - fix: Bug fixes
    - docs: Documentation
    - style: Code style changes
    - refactor: Code refactoring
    - test: Test additions/updates
    - chore: Maintenance tasks
    
  Branch Strategy:
    - main: Production code
    - develop: Development code
    - feature/*: New features
    - bugfix/*: Bug fixes
    - release/*: Release preparation
    
  PR Requirements:
    - Descriptive title with ticket number
    - Complete description of changes
    - Updated tests
    - Passing CI checks
    - Code review approval
</development_workflow>

## Continuous Integration and Deployment

```
<ci_cd_specifications>
  Description: CI/CD pipeline configuration and deployment processes
  
  GitHub Actions Workflow:
    ```yaml
    name: CI/CD Pipeline
    
    on:
      push:
        branches: [ main, develop ]
      pull_request:
        branches: [ main, develop ]
    
    jobs:
      build-and-test:
        runs-on: ubuntu-latest
        
        steps:
          - uses: actions/checkout@v2
          
          - name: Setup Node.js
            uses: actions/setup-node@v2
            with:
              node-version: '18'
              
          - name: Install Dependencies
            run: npm ci
            
          - name: Lint
            run: npm run lint
            
          - name: Type Check
            run: npm run type-check
            
          - name: Test
            run: npm run test:coverage
            
          - name: Build
            run: npm run build
            
      deploy:
        needs: build-and-test
        if: github.ref == 'refs/heads/main'
        runs-on: ubuntu-latest
        
        steps:
          - name: Deploy to Production
            # Add deployment steps
    ```
  
  Deployment Stages:
    - Development (automatic on develop branch)
    - Staging (manual trigger)
    - Production (manual trigger with approval)
    
  Pre-deployment Checklist:
    - All tests passing
    - Code review completed
    - Documentation updated
    - Environment variables verified
    - Database migrations ready
    - Rollback plan prepared
    
  Post-deployment Checklist:
    - Smoke tests
    - Monitor error rates
    - Check performance metrics
    - Verify logging
    - Update status page
</ci_cd_specifications>

## Regular Commit Reminders

```
<commit_reminders>
  Description: Automated reminders and checks for proper commit practices
  
  Frequency Guidelines:
    - Commit after each logical change
    - Push at least daily
    - Create PR after feature completion
    
  Commit Message Template:
    ```
    <type>(<scope>): [<ticket-number>] <description>
    
    [optional body]
    
    [optional footer]
    ```
    
  Example Workflow:
    ```bash
    # Start new feature
    git checkout -b feature/TASK-123-user-authentication
    
    # Regular commits
    git add .
    git commit -m "feat(auth): [TASK-123] implement login form"
    
    # Push changes
    git push origin feature/TASK-123-user-authentication
    ```
    
  Daily Checklist:
    - Review uncommitted changes
    - Verify commit messages
    - Push to remote repository
    - Update PR if exists
    - Review CI/CD status
    
  Code Review Process:
    - Self-review changes
    - Request peer review
    - Address feedback
    - Update documentation
    - Verify CI/CD pipeline
</commit_reminders>

## Quality Gates

```
<quality_gates>
  Description: Required checks and validations for each stage
  
  Pre-commit:
    - Lint checks
    - Type checking
    - Unit tests
    - Format verification
    
  Pre-push:
    - Integration tests
    - Build verification
    - Bundle size check
    - Security scan
    
  Pre-deployment:
    - E2E tests
    - Performance tests
    - Security audit
    - Documentation review
    
  Monitoring:
    - Error tracking
    - Performance metrics
    - User analytics
    - System health
</quality_gates>
```

## Implementation Notes

As you implement these workflows:
1. Set up pre-commit hooks for automated checks
2. Configure IDE to show commit template
3. Implement automated PR templates
4. Set up branch protection rules
5. Configure automated code review assignments
6. Establish deployment approval process

## Validation Requirements

Each commit and deployment must:
1. Follow naming conventions
2. Include proper documentation
3. Pass all quality gates
4. Have appropriate approvals
5. Be properly logged and tracked

Remember: Consistent, well-documented commits and proper workflow adherence are crucial for maintainable code and successful deployments. Regular commits with proper documentation create a clear history of changes and make troubleshooting easier.
