# Code Refactoring and Cleanup

You will perform systematic code refactoring and cleanup while maintaining functionality using the Subagent Context Engineering Workflow approach.

## Usage
```
/refactor-clean "[target-area]"
```

Example target areas:
- `"authentication system"` - Focus on auth-related code
- `"database layer"` - Clean up data access and models
- `"user interface components"` - Refactor UI components
- `"api endpoints"` - Clean up backend API code
- `"utility functions"` - Organize helper functions
- `"entire codebase"` - Comprehensive cleanup

## Refactoring Philosophy

**Refactor to improve without breaking.** Every change should make the code more maintainable, readable, or performant while preserving existing functionality. Clean code is easier to test, debug, and extend.

## Core Refactoring Principles

1. **Preserve Functionality**: Maintain exact behavioral compatibility
2. **Improve Incrementally**: Small, focused changes over large rewrites
3. **Test Continuously**: Verify functionality after each change
4. **Document Changes**: Track what was changed and why
5. **Safety First**: Always have rollback procedures ready

## Step-by-Step Refactoring Process

### Step 1: Target Analysis and Scope Definition
```
task "Analyze refactoring target and define scope" architect

Instructions for architect:
1. Review the specified target area code structure
2. Identify specific refactoring opportunities:
   - Code duplication and repetition
   - Complex functions that should be broken down
   - Unclear variable/function names
   - Inconsistent patterns and conventions
   - Performance bottlenecks
   - Security vulnerabilities
3. Assess refactoring complexity and time requirements
4. Define clear scope boundaries to prevent scope creep
5. Identify potential risks and breaking changes
6. Create refactoring priority matrix (high impact, low risk first)
```

### Step 2: Pre-Refactoring Safety Setup
Before any changes, establish safety measures:

```bash
# Create backup branch
git checkout -b backup/pre-refactor-$(date +%Y%m%d-%H%M%S)
git push -u origin backup/pre-refactor-$(date +%Y%m%d-%H%M%S)

# Return to main branch and create refactoring branch
git checkout main
git checkout -b refactor/[target-area]-cleanup

# Ensure all tests pass before refactoring
npm test || yarn test || python -m pytest

# Document current state
git add -A
git commit -m "Pre-refactor checkpoint: Clean baseline

🤖 Generated with Claude Code

Co-Authored-By: Claude <noreply@anthropic.com>"
```

### Step 3: Parallel Refactoring Assignment
Based on target area, assign specialized agents to work on different aspects:

```bash
# For authentication system refactoring
task "Refactor authentication code structure" prototype-lead
task "Review and optimize authentication security" architect
task "Update authentication test coverage" test-coordinator

# For database layer refactoring
task "Optimize database queries and models" architect
task "Refactor data access patterns" prototype-lead
task "Validate data integrity after changes" test-coordinator

# For UI components refactoring
task "Refactor component structure and reusability" prototype-lead
task "Improve component accessibility and performance" prototype-lead
task "Update component test scenarios" test-coordinator

# For API endpoints refactoring
task "Refactor API endpoint organization" architect
task "Improve error handling and validation" prototype-lead
task "Update API documentation and tests" test-coordinator

# For entire codebase refactoring
task "Refactor code organization and structure" architect
task "Improve naming conventions and patterns" prototype-lead
task "Comprehensive test coverage review" test-coordinator
```

### Step 4: Coordinated Refactoring Execution

#### 4.1 Code Structure Improvements (architect)
```markdown
## Structural Refactoring Tasks

### File Organization
- Group related files into logical directories
- Separate concerns (models, views, controllers, utils)
- Create clear module boundaries
- Eliminate circular dependencies
- Standardize import/export patterns

### Architecture Patterns
- Extract common patterns into reusable abstractions
- Implement consistent error handling
- Standardize data validation approaches
- Improve service layer organization
- Optimize dependency injection

### Database Layer
- Consolidate database access patterns
- Optimize query performance
- Improve data modeling
- Standardize transaction handling
- Enhance error handling
```

#### 4.2 Code Quality Improvements (prototype-lead)
```markdown
## Code Quality Refactoring Tasks

### Function Optimization
- Break down overly complex functions
- Extract pure functions for better testability
- Improve function naming and documentation
- Reduce function parameter counts
- Eliminate side effects where possible

### Variable and Naming
- Use descriptive variable names
- Follow consistent naming conventions
- Eliminate magic numbers and strings
- Improve constant organization
- Clarify boolean variable names

### Code Duplication
- Extract common logic into utility functions
- Create reusable components and modules
- Implement proper inheritance patterns
- Use composition over duplication
- Standardize common operations

### Performance Optimization
- Optimize rendering in UI components
- Improve algorithm efficiency
- Reduce unnecessary computations
- Implement proper caching strategies
- Optimize bundle size and loading
```

#### 4.3 Testing and Validation (test-coordinator)
```markdown
## Testing During Refactoring

### Continuous Validation
- Run automated tests after each change
- Verify functionality preservation
- Test edge cases and error scenarios
- Validate performance improvements
- Check accessibility compliance

### Test Coverage Improvement
- Add tests for previously untested code
- Improve test quality and clarity
- Remove obsolete or redundant tests
- Standardize test organization
- Enhance integration test coverage
```

### Step 5: Incremental Change Process

#### Phase 1: Safe Structural Changes (Low Risk)
```markdown
## Phase 1 Refactoring (30-45 minutes)

### Safe Changes First
1. **Rename variables/functions** for clarity
2. **Extract constants** from magic numbers/strings
3. **Organize imports** and dependencies
4. **Format code** consistently
5. **Add/improve comments** for complex logic

### Validation Steps
- Run full test suite after each change
- Verify application starts and basic functionality works
- Check for any linting or compilation errors
- Review git diff to ensure only intended changes
```

#### Phase 2: Functional Restructuring (Medium Risk)
```markdown
## Phase 2 Refactoring (45-60 minutes)

### Moderate Changes
1. **Extract utility functions** from duplicated code
2. **Reorganize file structure** and modules
3. **Improve error handling** patterns
4. **Optimize database queries** and data access
5. **Refactor component structure** and props

### Validation Steps
- Run comprehensive test suite
- Manual testing of affected functionality
- Performance testing for optimized areas
- Code review of changes for potential issues
```

#### Phase 3: Advanced Optimization (Higher Risk)
```markdown
## Phase 3 Refactoring (60-90 minutes)

### Complex Changes
1. **Architectural pattern improvements**
2. **State management optimization**
3. **API contract improvements**
4. **Database schema optimizations**
5. **Performance critical optimizations**

### Validation Steps
- Full regression testing
- Performance benchmarking
- Security review of changes
- Integration testing with external services
- Load testing if applicable
```

### Step 6: Quality Assurance Checkpoint

```
task "Perform comprehensive quality review" test-coordinator

Instructions for test-coordinator:
1. Execute full test suite and verify all tests pass
2. Perform manual testing of refactored functionality
3. Check for any performance regressions
4. Validate code follows project standards
5. Ensure no functionality has been lost or changed
6. Document any improvements or remaining issues
7. Prepare rollback plan if issues are discovered
```

### Step 7: Context Updates and Documentation

```
task "Update project context with refactoring results" context-keeper

Instructions for context-keeper:
1. Update current-state.md with refactoring improvements
2. Document any architectural changes made
3. Note any technical debt resolved
4. Record any new patterns or conventions established
5. Update code quality metrics if available
6. Flag any areas still needing future refactoring
```

## Refactoring Priorities Matrix

### High Impact, Low Risk (Do First)
- **Code formatting and linting fixes**
- **Variable and function renaming for clarity**
- **Extracting constants from magic numbers**
- **Adding missing documentation**
- **Simple function extraction**

### High Impact, Medium Risk (Do Second)
- **Eliminating code duplication**
- **Improving error handling patterns**
- **Optimizing database queries**
- **Restructuring component hierarchies**
- **Improving state management**

### High Impact, High Risk (Do Carefully)
- **Major architectural changes**
- **API contract modifications**
- **Database schema changes**
- **Third-party integration updates**
- **Performance critical optimizations**

### Low Impact, Any Risk (Consider Deferring)
- **Minor style preferences**
- **Premature optimizations**
- **Unnecessary abstractions**
- **Over-engineering solutions**
- **Cosmetic improvements only**

## Safety Rules and Rollback Procedures

### Pre-Change Safety Checklist
- [ ] **All tests passing** before starting refactoring
- [ ] **Backup branch created** with current state
- [ ] **Refactoring scope clearly defined** and documented
- [ ] **Rollback plan prepared** for each phase
- [ ] **Stakeholders notified** if affecting critical functionality

### During Refactoring Safety Rules
- [ ] **Make one change at a time** and test immediately
- [ ] **Commit frequently** with descriptive messages
- [ ] **Never change functionality** without explicit approval
- [ ] **Document any unexpected discoveries** immediately
- [ ] **Stop if tests fail** and fix before proceeding

### Rollback Procedures

#### If Tests Fail During Refactoring
```bash
# Immediate rollback to last working state
git reset --hard HEAD~1

# Or rollback to specific commit
git reset --hard [last-working-commit-hash]

# Re-run tests to verify rollback success
npm test || yarn test || python -m pytest
```

#### If Functionality Breaks After Completion
```bash
# Create emergency fix branch
git checkout -b hotfix/rollback-refactor-$(date +%Y%m%d)

# Revert specific problematic commits
git revert [problematic-commit-hash]

# Or complete rollback to pre-refactor state
git checkout backup/pre-refactor-[timestamp]
git checkout -b hotfix/emergency-rollback
```

#### If Performance Degrades
```bash
# Identify performance regression
npm run perf-test || yarn perf-test

# Revert performance-related changes
git revert [performance-commit-hash]

# Test performance restoration
npm run perf-test || yarn perf-test
```

## Refactoring Patterns by Code Area

### Authentication System Refactoring
```markdown
## Authentication Refactoring Checklist

### Security Improvements
- [ ] Review password hashing and validation
- [ ] Audit session management
- [ ] Check JWT token handling
- [ ] Validate input sanitization
- [ ] Review access control patterns

### Code Organization
- [ ] Extract authentication utilities
- [ ] Standardize error responses
- [ ] Improve middleware organization
- [ ] Consolidate validation logic
- [ ] Optimize database queries

### Testing Enhancements
- [ ] Add comprehensive auth tests
- [ ] Test security edge cases
- [ ] Validate error handling
- [ ] Check session management
- [ ] Test integration points
```

### Database Layer Refactoring
```markdown
## Database Refactoring Checklist

### Query Optimization
- [ ] Review and optimize slow queries
- [ ] Add appropriate indexes
- [ ] Eliminate N+1 query problems
- [ ] Optimize data loading patterns
- [ ] Review connection pooling

### Schema Improvements
- [ ] Normalize database design
- [ ] Add missing constraints
- [ ] Review data types
- [ ] Optimize relationships
- [ ] Plan migration strategies

### Data Access Patterns
- [ ] Standardize repository patterns
- [ ] Improve transaction handling
- [ ] Enhance error handling
- [ ] Add data validation
- [ ] Implement caching strategies
```

### UI Components Refactoring
```markdown
## UI Component Refactoring Checklist

### Component Structure
- [ ] Break down large components
- [ ] Extract reusable components
- [ ] Improve prop interfaces
- [ ] Optimize component rendering
- [ ] Enhance component composition

### User Experience
- [ ] Improve accessibility
- [ ] Optimize loading states
- [ ] Enhance error handling
- [ ] Improve responsive design
- [ ] Add proper feedback

### Performance
- [ ] Implement proper memoization
- [ ] Optimize bundle size
- [ ] Reduce unnecessary re-renders
- [ ] Lazy load components
- [ ] Optimize asset loading
```

### API Endpoints Refactoring
```markdown
## API Refactoring Checklist

### Endpoint Organization
- [ ] Group related endpoints
- [ ] Standardize URL patterns
- [ ] Improve route organization
- [ ] Optimize middleware usage
- [ ] Enhance documentation

### Data Validation
- [ ] Standardize input validation
- [ ] Improve error responses
- [ ] Add comprehensive logging
- [ ] Optimize serialization
- [ ] Enhance security

### Performance
- [ ] Optimize response times
- [ ] Implement proper caching
- [ ] Reduce payload sizes
- [ ] Optimize database queries
- [ ] Add rate limiting
```

## Integration with Other Commands

### After Prototype Development
```markdown
After `/prototype-feature`, use `/refactor-clean` to:
- Clean up rapid prototype code
- Improve naming and organization
- Add proper error handling
- Optimize performance
- Enhance test coverage
```

### Before Deployment
```markdown
Before `/deploy-check`, use `/refactor-clean` to:
- Ensure code quality standards
- Optimize performance
- Remove debug code
- Improve security
- Enhance maintainability
```

### During Development Cycles
```markdown
Regular refactoring helps:
- Prevent technical debt accumulation
- Maintain development velocity
- Improve code understanding
- Reduce bug introduction
- Enhance team productivity
```

## Quality Metrics and Success Criteria

### Code Quality Improvements
- [ ] **Reduced code duplication** by X%
- [ ] **Improved test coverage** to Y%
- [ ] **Eliminated linting errors** completely
- [ ] **Standardized naming conventions** throughout
- [ ] **Improved function complexity scores**

### Performance Improvements
- [ ] **Faster page load times** by X%
- [ ] **Reduced bundle size** by Y%
- [ ] **Optimized database queries** (reduced by Z%)
- [ ] **Improved memory usage**
- [ ] **Better rendering performance**

### Maintainability Improvements
- [ ] **Clearer code organization** and structure
- [ ] **Better documentation** and comments
- [ ] **Reduced complexity** in critical functions
- [ ] **Improved error handling** patterns
- [ ] **Enhanced debugging capabilities**

## Error Handling During Refactoring

### When Refactoring Breaks Tests
1. **Immediately stop refactoring** and assess the failure
2. **Determine if test needs updating** or code has bug
3. **Fix the issue** before proceeding
4. **Update tests** if functionality intentionally changed
5. **Document the change** and rationale

### When Performance Degrades
1. **Benchmark the degradation** and identify cause
2. **Revert problematic changes** immediately
3. **Analyze alternative approaches** to the refactoring
4. **Implement optimized solution** if possible
5. **Document performance considerations** for future

### When Integration Points Break
1. **Identify broken integrations** immediately
2. **Check if contracts changed** unintentionally
3. **Restore compatibility** with existing systems
4. **Update integration tests** appropriately
5. **Coordinate with dependent systems** if needed

## Communication Protocols

### Agent Coordination
- **architect**: Ensures structural improvements align with system design
- **prototype-lead**: Maintains code quality while preserving functionality
- **test-coordinator**: Validates changes and prevents regressions
- **context-keeper**: Tracks improvements and updates project status

### Stakeholder Communication
- **Progress Updates**: Regular updates on refactoring progress
- **Risk Communication**: Immediate notification of any issues
- **Improvement Reports**: Summary of quality and performance gains
- **Documentation Updates**: Changes to architecture or patterns

## Success Metrics

A successful refactoring cycle produces:
- **Improved Code Quality**: Better organized, readable, and maintainable code
- **Preserved Functionality**: All existing features work exactly as before
- **Enhanced Performance**: Measurable improvements in speed or efficiency
- **Better Test Coverage**: More comprehensive and reliable testing
- **Reduced Technical Debt**: Less problematic code requiring future fixes
- **Team Productivity**: Easier development and debugging for future work

## Template Commit Messages

```bash
# For structural improvements
git commit -m "refactor: improve [component] organization and structure

- Extract reusable utilities
- Improve naming conventions
- Reduce code duplication
- Enhance error handling

🤖 Generated with Claude Code

Co-Authored-By: Claude <noreply@anthropic.com>"

# For performance optimizations
git commit -m "perf: optimize [area] performance

- Reduce database query count
- Improve caching strategy
- Optimize component rendering
- Reduce bundle size

🤖 Generated with Claude Code

Co-Authored-By: Claude <noreply@anthropic.com>"

# For security improvements
git commit -m "security: enhance [area] security and validation

- Improve input validation
- Add security headers
- Enhance authentication
- Fix potential vulnerabilities

🤖 Generated with Claude Code

Co-Authored-By: Claude <noreply@anthropic.com>"
```

---

**Remember**: Refactoring is about improving the internal structure of code without changing its external behavior. Focus on making the code more maintainable, readable, and efficient while ensuring functionality remains intact. Always measure twice, cut once - thorough analysis and testing prevent breaking changes.