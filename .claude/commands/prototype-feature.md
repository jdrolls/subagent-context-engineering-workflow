# Rapid Feature Prototyping

You will rapidly prototype a feature with human testing gates using the Subagent Context Engineering Workflow approach.

## Usage
```
/prototype-feature "[feature-name]"
```

## Prototyping Philosophy

Build the **simplest working version first**, then enhance incrementally. Each prototype cycle should result in demonstrable functionality that can be tested by humans before proceeding to the next iteration.

## Core Prototyping Rules

1. **30-45 Minute Development Chunks**: Break features into manageable pieces
2. **Stop at Natural Testing Points**: Maximum 2-3 components/endpoints per cycle
3. **Clean Code from Start**: Maintain quality while moving fast
4. **Visual/Functional Tests**: Generate clear test scenarios for human review
5. **Continuous Context Updates**: Keep project state current throughout

## Step-by-Step Process

### Step 1: Feature Analysis and Decomposition
```
task "Analyze feature requirements and plan implementation" prototype-lead

Instructions for prototype-lead:
1. Review feature requirements from PRP and current context
2. Break feature into 30-45 minute implementable chunks
3. Identify dependencies and integration points
4. Plan development sequence (UI → API → Database → Integration)
5. Determine checkpoint frequency based on complexity
6. Prepare initial implementation approach
```

### Step 2: Parallel Development Assignment
Based on feature complexity, assign specialized agents to work in parallel:

```bash
# Example: User Authentication Feature
task "Build authentication UI components" prototype-lead
task "Create authentication API endpoints" architect  
task "Design user database schema" architect
task "Prepare authentication test scenarios" test-coordinator

# Example: Real-time Chat Feature (if websocket-specialist exists)
task "Build chat UI with message display" prototype-lead
task "Implement WebSocket server logic" websocket-specialist
task "Design message persistence schema" architect
task "Create real-time testing scenarios" test-coordinator

# Example: Payment Integration (if payment-integration exists)
task "Build payment form components" prototype-lead
task "Integrate Stripe payment processing" payment-integration
task "Design subscription data models" architect
task "Prepare payment testing workflows" test-coordinator
```

### Step 3: Coordinated Implementation
Execute implementation with proper coordination:

```markdown
## Implementation Coordination

### Frontend Development (prototype-lead)
- Build core UI components first
- Implement basic state management
- Add form validation and error handling
- Create loading states and user feedback
- Ensure accessibility from start

### Backend Development (architect or specialists)
- Create API endpoints with proper validation
- Implement business logic and data processing
- Add authentication and authorization
- Include error handling and logging
- Design for testability

### Database Changes (architect)
- Design efficient schema changes
- Create migration scripts
- Plan indexes and constraints
- Consider data integrity and relationships
- Prepare rollback strategies

### Integration Work (prototype-lead)
- Connect frontend to backend APIs
- Implement error handling between layers
- Add loading states and user feedback
- Test integration points thoroughly
- Document any temporary workarounds
```

### Step 4: Quality Checkpoint During Development
Ensure quality standards throughout development:

```markdown
## Quality Standards Checkpoint

### ✅ Code Quality
- [ ] Clear, descriptive variable and function names
- [ ] Consistent code patterns with existing codebase
- [ ] Proper error handling and validation
- [ ] Inline comments for complex business logic
- [ ] No obvious security vulnerabilities

### ✅ User Experience
- [ ] Intuitive user interface
- [ ] Clear feedback for all user actions
- [ ] Proper loading states and error messages
- [ ] Accessible design (keyboard navigation, ARIA labels)
- [ ] Responsive design for different screen sizes

### ✅ Technical Implementation
- [ ] Follows architectural decisions
- [ ] Integrates cleanly with existing code
- [ ] Handles edge cases and error conditions
- [ ] Performance considerations addressed
- [ ] Database queries optimized

### ✅ Testing Readiness
- [ ] Feature is demonstrable end-to-end
- [ ] Clear test scenarios can be defined
- [ ] Both happy path and error cases work
- [ ] Known limitations are documented
- [ ] Rollback plan exists if needed
```

### Step 5: Context Updates
```
task "Update project context with development progress" context-keeper

Instructions for context-keeper:
1. Update current-state.md with completed feature components
2. Document any architectural changes made
3. Note any technical debt incurred during rapid development
4. Update feature completion status
5. Record any new dependencies or integration points
6. Flag any areas needing future refactoring
```

### Step 6: Test Preparation and Handoff
```
task "Prepare comprehensive test scenarios for human validation" test-coordinator

Instructions for test-coordinator:
1. Analyze what was built and create specific test scenarios
2. Generate step-by-step testing instructions
3. Include both happy path and edge case testing
4. Prepare accessibility and usability checks
5. Document any known limitations or temporary workarounds
6. Create clear success criteria for each test scenario
7. Set up easy run commands and environment
```

## Checkpoint Frequency Based on Complexity

### Low Complexity Projects (PRP Score 5-10)
- **Checkpoint Every**: 3-4 features
- **Development Chunks**: 30-45 minutes each
- **Testing Focus**: Core functionality, basic edge cases

### Medium Complexity Projects (PRP Score 11-15)
- **Checkpoint Every**: 2-3 features  
- **Development Chunks**: 45-60 minutes each
- **Testing Focus**: Integration points, performance, security

### High Complexity Projects (PRP Score 16-25)
- **Checkpoint Every**: 1-2 features
- **Development Chunks**: 60-90 minutes each
- **Testing Focus**: Comprehensive scenarios, stress testing, failover

## Feature Implementation Patterns

### Simple CRUD Feature
```markdown
## Development Sequence: User Profile Management

### Chunk 1: Basic Profile Display (45 min)
- Create profile component with read-only display
- Add API endpoint to fetch user profile
- Basic error handling and loading states

### Chunk 2: Profile Editing (45 min)  
- Add edit form with validation
- Create update API endpoint
- Handle form submission and success feedback

### Checkpoint: Test profile view and edit functionality
```

### Complex Integration Feature
```markdown
## Development Sequence: Email Campaign System

### Chunk 1: Campaign Creation UI (60 min)
- Build campaign creation form
- Add template selection interface
- Basic validation and preview

### Chunk 2: Email Service Integration (90 min)
- Integrate with email service provider API
- Implement sending logic with error handling
- Add sending status tracking

### Chunk 3: Campaign Analytics (60 min)
- Build analytics dashboard
- Track open rates and click-through
- Display campaign performance metrics

### Checkpoint: Test complete email campaign workflow
```

### Real-time Feature
```markdown
## Development Sequence: Live Chat System

### Chunk 1: Chat UI Foundation (45 min)
- Build message display component
- Add message input form
- Basic local state management

### Chunk 2: WebSocket Integration (90 min)
- Implement WebSocket connection
- Handle real-time message sending/receiving
- Add connection status indicators

### Chunk 3: Message Persistence (60 min)
- Add message history loading
- Implement message storage
- Handle offline/reconnection scenarios

### Checkpoint: Test real-time messaging with multiple users
```

## Parallel Development Coordination

### Independent Tasks (Safe for Parallel Execution)
```bash
# These can run simultaneously
task "Build user interface components" prototype-lead
task "Design database schema" architect
task "Create email templates" email-automation
task "Prepare deployment configuration" deploy-manager
```

### Dependent Tasks (Must Run in Sequence)
```bash
# These must run in order
task "Create API endpoints" architect
# Wait for completion, then:
task "Integrate frontend with API" prototype-lead
# Wait for completion, then:
task "Add comprehensive error handling" prototype-lead
```

### Mixed Dependencies (Partial Parallel)
```bash
# Start these in parallel
task "Build authentication UI" prototype-lead
task "Set up authentication database tables" architect

# Then coordinate integration
task "Connect UI to authentication API" prototype-lead
task "Test authentication flow end-to-end" test-coordinator
```

## Error Handling During Prototyping

### Technical Blockers
If development encounters technical issues:
1. **Document the Problem**: Clear description of what's blocking progress
2. **Identify Workarounds**: Temporary solutions to continue development
3. **Flag for Resolution**: Mark areas needing proper fixes
4. **Update Context**: Record technical debt and future tasks
5. **Communicate Impact**: How this affects feature functionality

### Integration Failures
If components don't integrate cleanly:
1. **Isolate the Issue**: Identify specific integration points failing
2. **Create Minimal Reproduction**: Simplest case that demonstrates problem
3. **Design Alternative Approach**: Different integration strategy
4. **Implement Temporary Bridge**: Allow continued development
5. **Plan Proper Resolution**: Schedule time for clean integration

### Performance Issues
If feature performs poorly:
1. **Measure Baseline**: Quantify current performance
2. **Identify Bottlenecks**: Where specifically is performance poor
3. **Implement Quick Wins**: Easy optimizations
4. **Document Optimization Plan**: Future performance work needed
5. **Set Performance Targets**: Acceptable performance criteria

## Quality Gates

### Before Proceeding to Test Checkpoint
- [ ] **Functionality Complete**: Core feature works end-to-end
- [ ] **Error Handling**: Graceful handling of common error conditions
- [ ] **User Experience**: Intuitive interface with proper feedback
- [ ] **Integration**: Works with existing system components
- [ ] **Documentation**: Clear testing instructions prepared
- [ ] **Accessibility**: Basic accessibility requirements met
- [ ] **Performance**: Acceptable response times for core operations

### Before Continuing to Next Feature
- [ ] **Human Testing Complete**: All test scenarios validated
- [ ] **Critical Issues Resolved**: No blocking bugs remain
- [ ] **Context Updated**: Project status reflects reality
- [ ] **Technical Debt Documented**: Future work requirements noted
- [ ] **Team Alignment**: Stakeholders approve direction

## Communication Protocols

### Agent Coordination
- **prototype-lead**: Maintains development momentum and code quality
- **architect**: Ensures implementation follows design decisions
- **test-coordinator**: Prepares validation scenarios throughout development
- **context-keeper**: Tracks progress and maintains accurate project state

### Stakeholder Communication
- **Progress Updates**: Regular updates on development status
- **Decision Points**: Flag choices requiring human input
- **Risk Identification**: Communicate potential issues early
- **Success Celebration**: Highlight completed functionality

## Success Metrics

A successful prototype cycle produces:
- **Working Functionality**: Feature operates as intended
- **Clean Implementation**: Code follows project standards
- **Comprehensive Testing**: Human can validate all aspects
- **Updated Context**: Project state accurately reflects reality
- **Clear Next Steps**: Obvious path forward for continued development

---

**Remember**: The goal is sustainable rapid development. Build quickly but cleanly, test frequently, and maintain quality throughout the process. Each prototype cycle should move the project meaningfully closer to completion while preserving the ability to pivot based on feedback.