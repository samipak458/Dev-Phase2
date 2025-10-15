# Contributing to MazikCare

Thank you for your interest in contributing to the MazikCare Dynamics 365 Finance and Operations model! This document provides guidelines and best practices for contributing.

## Table of Contents

1. [Code of Conduct](#code-of-conduct)
2. [Getting Started](#getting-started)
3. [Development Process](#development-process)
4. [Coding Standards](#coding-standards)
5. [Testing Requirements](#testing-requirements)
6. [Pull Request Process](#pull-request-process)
7. [Security](#security)
8. [Documentation](#documentation)

## Code of Conduct

- Be respectful and professional in all interactions
- Focus on constructive feedback
- Help maintain a welcoming environment for all contributors
- Follow your organization's code of conduct policies

## Getting Started

### Prerequisites

1. **Development Environment**
   - Visual Studio with D365FO development tools
   - Access to D365FO development environment
   - Git for version control
   - Understanding of X++ programming language

2. **Access Requirements**
   - Repository access (read/write permissions)
   - D365FO development environment access
   - Appropriate security clearances for healthcare data

3. **Knowledge Requirements**
   - Familiarity with D365FO development
   - Understanding of healthcare domain (claims, billing, RCM)
   - Knowledge of HIPAA and healthcare compliance

### Setting Up Development Environment

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd Dev-Phase2
   ```

2. Copy MazikCare to your PackagesLocalDirectory:
   ```
   Copy to: K:\AosService\PackagesLocalDirectory\MazikCare\
   ```

3. Build the model in Visual Studio:
   - Open Visual Studio
   - Dynamics 365 > Build Models
   - Select MazikCare

## Development Process

### Branching Strategy

We follow a Git Flow-based branching strategy:

- **main**: Production-ready code
- **develop**: Integration branch for features
- **feature/**: Feature branches (e.g., feature/claim-enhancement)
- **bugfix/**: Bug fix branches (e.g., bugfix/claim-calculation-error)
- **hotfix/**: Emergency production fixes

### Creating a Branch

```bash
# For new features
git checkout -b feature/descriptive-feature-name

# For bug fixes
git checkout -b bugfix/issue-number-short-description

# For hotfixes
git checkout -b hotfix/critical-issue-description
```

### Making Changes

1. **Keep Changes Focused**
   - One feature or fix per branch
   - Make small, incremental commits
   - Write clear commit messages

2. **Commit Message Format**
   ```
   <type>: <subject>
   
   <body>
   
   <footer>
   ```
   
   Types:
   - `feat`: New feature
   - `fix`: Bug fix
   - `docs`: Documentation changes
   - `refactor`: Code refactoring
   - `test`: Adding or updating tests
   - `chore`: Maintenance tasks

   Example:
   ```
   feat: Add new claim status validation
   
   - Implement validation for claim status transitions
   - Add error messages for invalid transitions
   - Update unit tests
   
   Closes #123
   ```

## Coding Standards

### X++ Code Standards

1. **Naming Conventions**
   - Classes: `HM` prefix + PascalCase (e.g., `HMClaimProcessor`)
   - Methods: camelCase (e.g., `processClaimData`)
   - Variables: camelCase (e.g., `claimAmount`)
   - Constants: UPPER_CASE (e.g., `MAX_CLAIM_AMOUNT`)
   - Tables: `HM` prefix + PascalCase (e.g., `HMClaimTable`)

2. **Code Structure**
   ```xpp
   /// <summary>
   /// Brief description of the class
   /// </summary>
   class HMClaimProcessor
   {
       // Constants
       const int MAX_RETRY_COUNT = 3;
       
       // Member variables
       private HMClaimTable claimTable;
       
       /// <summary>
       /// Method description
       /// </summary>
       /// <param name="_claimId">Claim identifier</param>
       /// <returns>Processing result</returns>
       public boolean processClaimData(RecId _claimId)
       {
           // Method implementation
       }
   }
   ```

3. **Best Practices**
   - Always run D365FO Best Practice checker before committing
   - Handle exceptions properly with try-catch blocks
   - Use proper transaction management (ttsbegin/ttscommit)
   - Validate input parameters
   - Log errors appropriately
   - Follow the principle of least privilege for database access

4. **Performance Considerations**
   - Use set-based operations when possible
   - Avoid cursor-based operations for large datasets
   - Optimize queries with proper indexes
   - Cache frequently accessed data appropriately

### XML and Metadata

- Maintain consistent formatting
- Use proper indentation (tabs as per D365FO standard)
- Validate XML files before committing
- Don't manually edit generated metadata when possible

### Resource Files (HTML/CSS/JavaScript)

- Follow modern web standards
- Minify resources for production
- Test in supported browsers
- Document external library dependencies

## Testing Requirements

### Before Submitting

1. **Build Validation**
   ```
   - Clean build of MazikCare model
   - No build errors or warnings
   - Database synchronization successful
   ```

2. **Best Practice Checks**
   - Run D365FO Best Practice analyzer
   - Fix all critical and high-priority issues
   - Document any suppressed warnings

3. **Unit Testing**
   - Write unit tests for new functionality
   - Ensure existing tests pass
   - Aim for meaningful test coverage

4. **Integration Testing**
   - Test in development environment
   - Verify no regression in existing functionality
   - Test with realistic data volumes

5. **Security Testing**
   - Verify role-based access controls
   - Test with different security roles
   - Ensure no unauthorized data access

6. **Manual Testing Checklist**
   - [ ] Feature works as expected
   - [ ] No console errors
   - [ ] UI is responsive and user-friendly
   - [ ] Error messages are clear and helpful
   - [ ] Performance is acceptable
   - [ ] No data integrity issues

## Pull Request Process

### Creating a Pull Request

1. **Pre-submission Checklist**
   - [ ] Code follows style guidelines
   - [ ] Best Practice checks passed
   - [ ] All tests pass
   - [ ] Documentation updated
   - [ ] CHANGELOG.md updated (if applicable)
   - [ ] No merge conflicts with target branch

2. **PR Title Format**
   ```
   [Type] Brief description of changes
   ```
   Example: `[Feature] Add claim batch processing capability`

3. **PR Description Template**
   ```markdown
   ## Description
   Brief description of what this PR does
   
   ## Type of Change
   - [ ] Bug fix
   - [ ] New feature
   - [ ] Breaking change
   - [ ] Documentation update
   
   ## Testing Done
   - Describe testing performed
   - List test cases executed
   - Include screenshots if UI changes
   
   ## Related Issues
   Closes #issue_number
   
   ## Checklist
   - [ ] Code follows style guidelines
   - [ ] Best practice checks passed
   - [ ] Tests added/updated
   - [ ] Documentation updated
   - [ ] No breaking changes (or documented if unavoidable)
   ```

### Code Review Process

1. **Review Requirements**
   - Minimum 2 approvals required
   - At least one approval from a code owner
   - All comments resolved
   - CI/CD checks passed

2. **Review Guidelines**
   - Review within 2 business days
   - Provide constructive feedback
   - Test the changes locally if possible
   - Verify documentation accuracy

3. **Addressing Feedback**
   - Respond to all comments
   - Make requested changes promptly
   - Re-request review after changes
   - Don't force-push after reviews start (unless necessary)

### Merging

- Use "Squash and Merge" for feature branches
- Use "Create a merge commit" for important release merges
- Delete branch after merge (if appropriate)
- Update any related issues/tickets

## Security

### Security Best Practices

⚠️ **Critical: Never commit sensitive information**

1. **Prohibited Content**
   - Passwords or credentials
   - API keys or tokens
   - Connection strings with credentials
   - Personal health information (PHI)
   - Personally identifiable information (PII)
   - Customer data

2. **If Sensitive Data is Accidentally Committed**
   - Immediately notify security team
   - Rotate any exposed credentials
   - Follow incident response procedures
   - Remove from Git history (with security team approval)

3. **Healthcare Data Compliance**
   - Follow HIPAA guidelines
   - Use proper data encryption
   - Implement audit logging
   - Maintain access controls
   - Test data must be synthetic/anonymized

4. **Reporting Security Issues**
   - Do NOT create public issues for security vulnerabilities
   - Email security team directly
   - Provide detailed information privately
   - Allow time for responsible disclosure

## Documentation

### Required Documentation Updates

When contributing code, update relevant documentation:

1. **Code Comments**
   - XML documentation for public methods
   - Inline comments for complex logic
   - TODO comments with issue references

2. **README Updates**
   - New features or capabilities
   - Changed dependencies
   - Updated setup instructions

3. **CHANGELOG**
   - Add entry under [Unreleased]
   - Follow Keep a Changelog format
   - Be specific and clear

4. **User Documentation**
   - Update user guides if UI changes
   - Document new features
   - Update screenshots if applicable

### Documentation Style

- Use clear, concise language
- Include examples where helpful
- Keep formatting consistent
- Test instructions by following them
- Use proper grammar and spelling

## Questions or Need Help?

- Check existing documentation first
- Search closed issues for similar questions
- Ask in team channels
- Contact repository maintainers
- See CODEOWNERS for specific area owners

## Recognition

Contributors will be recognized in:
- Release notes
- CONTRIBUTORS.md file (if maintained)
- Project documentation

Thank you for contributing to MazikCare! 🎉

---

**Last Updated:** 2024-10-08
