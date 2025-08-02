# Add Feature to Existing Project

You will add a new feature to an existing project using the Subagent Context Engineering Workflow approach, leveraging established architecture patterns and existing codebase context.

## Usage
```
/add-feature "[feature-description]"
```

## Feature Integration Philosophy

Adding features to existing projects requires different considerations than greenfield development:

1. **Architecture Consistency**: New features must align with existing patterns and decisions
2. **Integration Points**: Identify and leverage existing components and services
3. **Minimal Disruption**: Add functionality without breaking existing features
4. **Context Preservation**: Maintain project understanding while expanding capabilities
5. **Quality Maintenance**: Keep existing code quality standards throughout integration

## Core Integration Rules

1. **30-45 Minute Integration Chunks**: Break features into manageable pieces that work with existing code
2. **Existing Pattern Analysis**: Study current codebase patterns before implementing
3. **Incremental Integration**: Build on existing components rather than creating parallel systems
4. **Continuous Context Updates**: Keep project state current with new additions
5. **Regression Prevention**: Ensure new features don't break existing functionality

## Step-by-Step Process

### Step 1: Existing Codebase Analysis
```
task "Analyze existing codebase for feature integration" architect

Instructions for architect:
1. Review current-state.md and tech-decisions.md for existing patterns
2. Examine current codebase structure and architecture
3. Identify existing components that can be extended or reused
4. Assess integration points and potential conflicts
5. Document existing API patterns and data models
6. Identify any architectural adjustments needed
7. Plan integration strategy that minimizes disruption
```

### Step 2: Feature Decomposition and Planning
```
task "Decompose feature and plan integration approach" prototype-lead

Instructions for prototype-lead:
1. Break feature into components that align with existing architecture
2. Identify which existing components can be extended vs new ones needed
3. Plan development sequence that leverages existing patterns
4. Determine integration points with current features
5. Assess impact on existing user flows and interfaces
6. Plan backward compatibility considerations
7. Prepare development approach that maintains code quality
```

### Step 3: Impact Assessment and Risk Analysis
```
task "Assess feature impact on existing systems" context-keeper

Instructions for context-keeper:
1. Analyze potential impact on existing features
2. Identify dependencies and integration risks
3. Review current technical debt that might affect integration
4. Assess testing requirements for regression prevention
5. Document any necessary refactoring of existing code
6. Flag potential performance impacts
7. Update current-state.md with planned changes
```

### Step 4: Specialized Agent Assignment
Based on feature requirements and existing project agents, assign work appropriately:

```bash
# Example: Adding real-time notifications to existing app
task "Extend existing user interface for notifications" prototype-lead
task "Integrate with existing WebSocket infrastructure" websocket-specialist
task "Extend existing API with notification endpoints" architect
task "Update existing database schema for notifications" architect

# Example: Adding payment features to existing e-commerce
task "Integrate payment forms with existing checkout" prototype-lead
task "Extend existing order processing with payment flow" payment-integration
task "Update existing user account for payment methods" architect
task "Extend existing email system with payment confirmations" email-automation

# Example: Adding AI features to existing content platform
task "Integrate AI generation into existing content editor" prototype-lead
task "Extend existing API with AI processing endpoints" ai-integration
task "Update existing content models for AI metadata" architect
task "Extend existing user permissions for AI features" architect
```

### Step 5: Parallel Integration Development
Execute development with careful coordination to existing systems:

```markdown
## Integration Development Coordination

### Frontend Integration (prototype-lead)
- Extend existing UI components rather than creating new ones
- Follow established design patterns and styling
- Integrate with existing state management systems
- Maintain existing navigation and user flow patterns
- Ensure accessibility standards match existing implementation

### Backend Integration (architect or specialists)
- Extend existing API patterns and conventions
- Reuse existing authentication and authorization systems
- Follow established error handling and logging patterns
- Integrate with existing database connections and ORM
- Maintain existing API versioning and documentation

### Database Integration (architect)
- Extend existing schema using established migration patterns
- Reuse existing relationships and constraint patterns
- Follow existing naming conventions and indexing strategies
- Plan migrations that don't disrupt existing data
- Consider existing backup and recovery procedures

### Service Integration (specialists)
- Leverage existing service configurations and patterns
- Reuse existing external API integrations where possible
- Follow established environment variable and secret patterns
- Integrate with existing monitoring and logging systems
- Maintain existing deployment and scaling strategies
```

### Step 6: Integration Quality Checkpoint
Ensure new feature integrates cleanly with existing systems:

```markdown
## Integration Quality Standards

### ✅ Architecture Consistency
- [ ] New feature follows existing architectural patterns
- [ ] API endpoints match existing conventions
- [ ] Database changes follow established schema patterns
- [ ] Error handling matches existing implementation
- [ ] Logging and monitoring integrate with existing systems

### ✅ Code Integration Quality
- [ ] New code follows existing style and patterns
- [ ] Component structure matches existing organization
- [ ] Dependencies align with existing package management
- [ ] Configuration follows existing environment patterns
- [ ] Documentation follows existing standards

### ✅ User Experience Consistency
- [ ] UI components match existing design system
- [ ] User flows integrate smoothly with existing navigation
- [ ] Loading states and error messages match existing patterns
- [ ] Accessibility standards maintained across all features
- [ ] Performance characteristics consistent with existing features

### ✅ Backward Compatibility
- [ ] Existing features continue to work unchanged
- [ ] API changes are backward compatible or properly versioned
- [ ] Database migrations don't break existing data access
- [ ] Configuration changes don't affect existing deployments
- [ ] User data and preferences are preserved

### ✅ Testing Integration
- [ ] New tests follow existing testing patterns and frameworks
- [ ] Existing tests continue to pass
- [ ] Integration tests cover new feature interactions
- [ ] End-to-end tests include new feature in existing flows
- [ ] Performance tests account for new feature impact
```

### Step 7: Regression Testing Strategy
```
task "Design comprehensive regression testing strategy" test-coordinator

Instructions for test-coordinator:
1. Identify existing functionality that might be affected
2. Create test scenarios that cover existing feature interactions
3. Generate tests for new feature integration points
4. Plan performance testing to ensure no degradation
5. Prepare rollback testing procedures
6. Create test scenarios for existing user workflows
7. Document testing approach for stakeholder review
```

### Step 8: Context Updates and Integration Documentation
```
task "Update project context with feature integration" context-keeper

Instructions for context-keeper:
1. Update current-state.md with new feature details and integration points
2. Document any architectural changes or extensions made
3. Record new dependencies and their integration approach
4. Update tech-decisions.md with new technology choices and rationale
5. Note any refactoring done to existing code during integration
6. Document any technical debt created or resolved
7. Update deployment considerations for new feature
```

## Integration Complexity Considerations

### Low Complexity Integration (extends existing patterns)
- **Development Approach**: Extend existing components and APIs
- **Testing Focus**: Basic integration points, existing workflow preservation
- **Coordination**: Minimal agent coordination needed
- **Checkpoint Frequency**: Every 2-3 components integrated

### Medium Complexity Integration (new service or significant extension)
- **Development Approach**: New components with careful integration
- **Testing Focus**: Cross-service integration, performance impact, security
- **Coordination**: Multiple specialists working on integration points
- **Checkpoint Frequency**: Every 1-2 major components

### High Complexity Integration (architectural changes required)
- **Development Approach**: Phased integration with architectural evolution
- **Testing Focus**: Comprehensive regression, performance, scalability
- **Coordination**: Full team coordination with architecture reviews
- **Checkpoint Frequency**: After each architectural change

## Integration Patterns

### Extending Existing Components
```markdown
## Development Sequence: Add Search to Existing Product Catalog

### Chunk 1: Extend Existing Product API (45 min)
- Add search parameters to existing product endpoints
- Extend existing product queries with search functionality
- Reuse existing product validation and error handling
- Update existing API documentation

### Chunk 2: Extend Product UI Components (45 min)
- Add search input to existing product list component
- Extend existing product filters with search capabilities
- Reuse existing loading states and error handling
- Maintain existing responsive design patterns

### Checkpoint: Test search functionality with existing product workflows
```

### Adding New Service Layer
```markdown
## Development Sequence: Add Real-time Notifications

### Chunk 1: Extend Existing WebSocket Infrastructure (60 min)
- Add notification channels to existing WebSocket server
- Extend existing authentication for notification subscriptions
- Reuse existing connection management patterns
- Add notification event types to existing event system

### Chunk 2: Integrate Notification UI (60 min)
- Add notification components using existing UI patterns
- Integrate with existing header/navigation components
- Reuse existing modal and overlay systems
- Follow existing state management patterns

### Chunk 3: Connect with Existing Data Models (45 min)
- Extend existing user preferences for notifications
- Add notification history to existing user data
- Integrate with existing API error handling
- Update existing database models with notification support

### Checkpoint: Test notifications with existing user workflows
```

### Complex Feature Integration
```markdown
## Development Sequence: Add AI Content Generation to CMS

### Chunk 1: Extend Content Editor Interface (90 min)
- Add AI generation buttons to existing content editor
- Integrate AI controls with existing editor toolbar
- Extend existing content preview with AI indicators
- Maintain existing autosave and draft functionality

### Chunk 2: Integrate AI Processing Pipeline (120 min)
- Create AI service that integrates with existing content API
- Extend existing content validation with AI output handling
- Integrate with existing user permissions and rate limiting
- Add AI processing to existing background job system

### Chunk 3: Extend Content Management Workflows (90 min)
- Add AI metadata to existing content models
- Integrate AI versioning with existing content history
- Extend existing content approval workflows
- Update existing content analytics with AI metrics

### Checkpoint: Test AI features within existing content workflows
```

## Parallel Development Coordination for Integration

### Safe Integration Tasks (Can Run in Parallel)
```bash
# These integrate with different areas safely
task "Extend user interface components" prototype-lead
task "Update database schema with new tables" architect
task "Create new API endpoints following existing patterns" architect
task "Prepare deployment configuration updates" deploy-manager
```

### Sequential Integration Tasks (Must Coordinate)
```bash
# These must integrate in order
task "Extend existing API endpoints" architect
# Wait for API changes, then:
task "Update frontend to use extended API" prototype-lead
# Wait for frontend updates, then:
task "Test integration with existing workflows" test-coordinator
```

### Mixed Integration Dependencies
```bash
# Start these in parallel
task "Extend existing authentication system" architect
task "Create new UI components using existing patterns" prototype-lead

# Then coordinate integration
task "Integrate new UI with extended authentication" prototype-lead
task "Test authentication flow with new and existing features" test-coordinator
```

## Error Handling During Integration

### Integration Conflicts
If new feature conflicts with existing functionality:
1. **Document the Conflict**: Clear description of what's conflicting
2. **Analyze Root Cause**: Whether it's architectural, data, or business logic
3. **Design Resolution Strategy**: How to resolve without breaking existing features
4. **Implement Gradual Transition**: Phase integration to minimize disruption
5. **Update Documentation**: Record conflict resolution for future reference

### Performance Degradation
If new feature impacts existing performance:
1. **Measure Impact**: Quantify performance change on existing features
2. **Identify Bottlenecks**: Specific areas where new feature creates overhead
3. **Optimize Integration**: Improve integration approach or optimize existing code
4. **Consider Feature Flags**: Allow gradual rollout to manage performance impact
5. **Plan Performance Improvements**: Schedule optimization work if needed

### Breaking Changes Required
If integration requires breaking existing functionality:
1. **Document Breaking Changes**: What existing functionality will change
2. **Design Migration Path**: How existing users/data will transition
3. **Implement Versioning Strategy**: Support old and new patterns temporarily
4. **Plan Communication**: How to inform stakeholders of changes
5. **Create Rollback Plan**: How to revert if integration causes problems

## Quality Gates for Feature Integration

### Before Integration Testing
- [ ] **Feature Works Independently**: New functionality operates correctly in isolation
- [ ] **Integration Points Identified**: Clear understanding of how feature connects to existing code
- [ ] **Backward Compatibility Ensured**: Existing features continue to work unchanged
- [ ] **Code Quality Maintained**: New code follows existing patterns and standards
- [ ] **Documentation Updated**: Integration approach and new functionality documented

### Before Deployment to Production
- [ ] **Regression Testing Complete**: All existing functionality validated
- [ ] **Integration Testing Passed**: New feature works correctly with existing systems
- [ ] **Performance Impact Assessed**: No significant degradation of existing features
- [ ] **Security Review Complete**: Integration doesn't introduce security vulnerabilities
- [ ] **Rollback Plan Ready**: Clear plan for reverting if issues arise

## Communication Protocols for Integration

### Agent Coordination During Integration
- **architect**: Ensures integration follows established patterns and makes necessary architectural adjustments
- **prototype-lead**: Maintains code quality while integrating new functionality with existing components
- **context-keeper**: Tracks integration progress and maintains accurate project state
- **test-coordinator**: Ensures integration doesn't break existing functionality
- **specialists**: Apply domain expertise while respecting existing integrations

### Stakeholder Communication for Feature Addition
- **Integration Progress**: Regular updates on how new feature integrates with existing functionality
- **Impact Assessment**: Communication about any changes to existing user experience
- **Risk Mitigation**: Proactive communication about integration challenges and solutions
- **Testing Requirements**: Clear expectations for stakeholder testing of integrated functionality

## Success Metrics for Feature Integration

A successful feature integration produces:
- **Seamless User Experience**: New functionality feels natural within existing application
- **Code Quality Maintenance**: Integration doesn't compromise existing code standards
- **Performance Preservation**: New feature doesn't degrade existing functionality performance
- **Architectural Consistency**: Integration follows and extends established patterns
- **Comprehensive Testing**: Both new feature and existing functionality validated
- **Clear Documentation**: Integration approach and impact clearly documented

## Feature Integration Anti-Patterns to Avoid

### Parallel System Creation
❌ **Don't**: Create entirely new systems that duplicate existing functionality
✅ **Do**: Extend existing systems with new capabilities

### Pattern Breaking
❌ **Don't**: Introduce new patterns that conflict with existing codebase conventions
✅ **Do**: Follow established patterns and extend them thoughtfully

### Silent Breaking Changes
❌ **Don't**: Make changes that break existing functionality without documentation
✅ **Do**: Document all changes and ensure backward compatibility

### Integration Shortcuts
❌ **Don't**: Take shortcuts in integration that create technical debt
✅ **Do**: Invest in proper integration that maintains long-term code quality

### Testing Negligence
❌ **Don't**: Skip regression testing because feature "shouldn't affect existing code"
✅ **Do**: Comprehensive testing of both new functionality and existing features

## Advanced Integration Scenarios

### Feature Flags for Gradual Rollout
```markdown
## Implementation Strategy: Feature Flags for New Feature
1. Implement feature behind configurable flag
2. Deploy feature in disabled state
3. Enable for limited user base
4. Monitor integration impact
5. Gradually expand rollout
6. Remove flag once stable
```

### Database Migration for Existing Data
```markdown
## Migration Strategy: Extending User Model
1. Create migration script that handles existing data
2. Add new columns with appropriate defaults
3. Backfill existing records with sensible values
4. Update application code to handle both old and new data patterns
5. Validate migration with production-like data set
6. Plan rollback migration if needed
```

### API Versioning for Backward Compatibility
```markdown
## Versioning Strategy: Extending API Endpoints
1. Create new API version alongside existing
2. Implement new functionality in new version
3. Maintain existing version during transition
4. Provide migration guide for API consumers
5. Set deprecation timeline for old version
6. Monitor usage to plan sunset of old version
```

---

**Remember**: The goal is sustainable feature growth. Integrate thoughtfully, test comprehensively, and maintain the quality and patterns that make existing code successful. Each feature addition should make the codebase stronger, not more complex.