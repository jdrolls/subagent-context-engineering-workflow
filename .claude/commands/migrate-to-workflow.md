# Migrate Existing Project to Workflow

You will adopt the Subagent Context Engineering Workflow in an existing codebase, transforming it into a workflow-managed project with proper context engineering and agent orchestration.

## Usage
```
/migrate-to-workflow [project-root-path]
```

## Migration Philosophy

Transform existing projects **gradually and safely**, preserving working functionality while introducing workflow benefits. The migration process respects existing code, development practices, and team workflows while adding structured context management and agent-based development.

## Core Migration Principles

1. **Preserve Existing Functionality**: Never break working features during migration
2. **Incremental Adoption**: Introduce workflow components gradually
3. **Respect Existing Patterns**: Adapt workflow to project conventions, not vice versa
4. **Context Extraction**: Generate accurate context from existing codebase
5. **Risk Mitigation**: Identify and address potential migration risks early
6. **Team Integration**: Work with existing development processes

## Step-by-Step Migration Process

### Step 1: Project Analysis and Risk Assessment
```
task "Analyze existing project structure and assess migration risks" architect

Instructions for architect:
1. Analyze project structure, technology stack, and complexity
2. Identify existing development workflows and tools
3. Assess codebase quality and technical debt
4. Evaluate team processes and integration points
5. Identify potential migration risks and blockers
6. Recommend migration strategy based on project characteristics
7. Document findings in migration-analysis.md
8. Create risk mitigation plan
```

### Step 2: Codebase Documentation and Context Extraction
```
task "Extract project context from existing codebase" context-keeper

Instructions for context-keeper:
1. Analyze existing documentation (README, docs, comments)
2. Examine package.json/requirements.txt for dependencies
3. Identify existing features by analyzing routes/components
4. Map current architecture and data models
5. Extract business logic and domain concepts
6. Document existing integrations and external services
7. Create current-state.md with comprehensive project overview
8. Generate tech-decisions.md from existing architectural choices
```

### Step 3: Reverse-Engineer Project Requirements Plan
```
task "Generate PRP from existing codebase analysis" prd-analyzer

Instructions for prd-analyzer:
1. Review codebase analysis and existing documentation
2. Infer original project requirements from implemented features
3. Assess current project complexity and scope
4. Identify missing features or incomplete implementations
5. Generate comprehensive PRP that reflects current reality
6. Include technical debt and improvement opportunities
7. Create realistic project timeline based on existing work
8. Update context/prp.md with reverse-engineered requirements
```

### Step 4: Identify Required Specialized Agents
Based on codebase analysis, determine which project-specific agents are needed:

```bash
# Analysis of existing integrations and features

# For existing payment processing
if [Stripe/PayPal/payment code detected]; then
  create agents/project/payment-integration.md
fi

# For existing real-time features
if [WebSocket/Socket.io/real-time code detected]; then
  create agents/project/websocket-specialist.md
fi

# For existing AI/ML features
if [OpenAI/AI integration detected]; then
  create agents/project/ai-integration.md
fi

# For existing email functionality
if [SendGrid/Mailgun/email code detected]; then
  create agents/project/email-automation.md
fi

# For complex database operations
if [complex queries/migrations detected]; then
  create agents/project/database-migration.md
fi

# For performance-critical sections
if [performance bottlenecks identified]; then
  create agents/project/performance-optimizer.md
fi

# For security-sensitive applications
if [authentication/security patterns detected]; then
  create agents/project/security-auditor.md
fi

# For existing mobile/responsive features
if [mobile-specific code detected]; then
  create agents/project/mobile-specialist.md
fi

# For existing API integrations
if [third-party APIs detected]; then
  create agents/project/api-integration.md
fi

# For existing testing infrastructure
if [comprehensive test suite detected]; then
  create agents/project/test-automation.md
fi
```

### Step 5: Workflow Infrastructure Setup
Create workflow infrastructure without disrupting existing project:

```bash
# Create .claude directory structure
mkdir -p .claude/{agents/core,agents/project,commands,context}

# Copy core workflow files (preserving existing .claude if it exists)
# Initialize context files based on extracted information
# Set up agent registry with identified specialized agents
# Configure workflow commands for this project's structure

# Create backup of any existing .claude configuration
if [ -d .claude ]; then
  cp -r .claude .claude.backup.$(date +%Y%m%d_%H%M%S)
fi
```

### Step 6: Integration with Existing Development Process
```
task "Integrate workflow with existing development practices" deploy-manager

Instructions for deploy-manager:
1. Analyze existing CI/CD pipelines and deployment processes
2. Identify existing development scripts and build processes
3. Map existing testing frameworks and quality gates
4. Document existing environment management (dev/staging/prod)
5. Plan workflow integration that preserves existing processes
6. Update deployment-status.md with current deployment setup
7. Recommend workflow enhancements that complement existing tools
8. Create migration timeline that minimizes disruption
```

### Step 7: Gradual Feature Migration Planning
```
task "Plan gradual feature migration to workflow management" prototype-lead

Instructions for prototype-lead:
1. Prioritize features for workflow adoption based on:
   - Development frequency (most changed features first)
   - Complexity (start with simpler features)
   - Risk level (lower risk features first)
   - Team familiarity (areas team knows well)
2. Create feature migration roadmap
3. Identify which features can be enhanced using workflow
4. Plan integration testing strategy for migrated features
5. Document rollback procedures for each migration phase
6. Update current-state.md with migration roadmap
```

## Risk Assessment and Mitigation

### Technical Risks

#### Risk: Breaking Existing Functionality
**Mitigation Strategy:**
- Comprehensive backup before any changes
- Incremental migration with testing gates
- Rollback procedures for each migration step
- Preservation of existing build and deployment processes

#### Risk: Conflicting Development Patterns
**Mitigation Strategy:**
- Adapt workflow to existing code patterns
- Document pattern conflicts and resolution approaches
- Gradual introduction of workflow patterns
- Team training on workflow adoption

#### Risk: Performance Degradation
**Mitigation Strategy:**
- Baseline performance measurements before migration
- Performance testing at each migration checkpoint
- Optimization planning for identified bottlenecks
- Monitoring setup to detect performance issues

#### Risk: Team Resistance or Confusion
**Mitigation Strategy:**
- Clear documentation of workflow benefits
- Gradual introduction with training
- Demonstration of workflow value through pilot features
- Preservation of familiar development patterns where possible

### Business Risks

#### Risk: Development Velocity Reduction
**Mitigation Strategy:**
- Migrate during lower-priority development periods
- Start with enhancement features rather than critical fixes
- Measure and communicate velocity improvements
- Fallback to existing processes if needed

#### Risk: Quality Regression
**Mitigation Strategy:**
- Enhanced testing during migration period
- Code review processes for workflow adoption
- Quality metrics tracking throughout migration
- Rollback triggers based on quality thresholds

## Migration Validation Checklist

### ✅ Pre-Migration Validation
- [ ] Complete project backup created
- [ ] Existing functionality documented and tested
- [ ] Team informed and migration timeline agreed
- [ ] Rollback procedures tested and verified
- [ ] Development environment replicated for testing

### ✅ Context Extraction Validation
- [ ] Current project state accurately captured
- [ ] All existing features documented in PRP
- [ ] Technical decisions properly recorded
- [ ] Integration points and dependencies mapped
- [ ] Performance baselines established

### ✅ Agent Configuration Validation
- [ ] Required specialized agents identified and created
- [ ] Agent responsibilities aligned with project needs
- [ ] No capability gaps between agents and project needs
- [ ] Agent coordination patterns established
- [ ] Testing procedures for agent-generated code

### ✅ Workflow Integration Validation
- [ ] Existing development processes preserved
- [ ] Workflow commands adapted to project structure
- [ ] CI/CD integration working correctly
- [ ] Team can use workflow commands effectively
- [ ] Rollback procedures verified

### ✅ Feature Migration Validation
- [ ] Pilot feature successfully migrated
- [ ] No regression in existing functionality
- [ ] Workflow benefits demonstrated
- [ ] Team comfortable with workflow approach
- [ ] Performance maintained or improved

## Migration Strategies by Project Type

### Legacy Web Application
```markdown
## Migration Strategy: Legacy Web App

### Phase 1: Context Establishment (Week 1)
- Extract existing architecture and feature documentation
- Create PRP from existing functionality
- Set up workflow infrastructure
- Identify technical debt and improvement opportunities

### Phase 2: Enhancement Features (Weeks 2-3)
- Start with new feature development using workflow
- Demonstrate workflow benefits on non-critical features
- Build team familiarity with agent coordination
- Establish testing patterns for workflow-generated code

### Phase 3: Existing Feature Enhancement (Weeks 4-6)
- Migrate high-frequency development areas to workflow
- Apply workflow to bug fixes and improvements
- Refactor problematic areas using specialized agents
- Optimize performance bottlenecks identified during analysis

### Phase 4: Full Workflow Adoption (Weeks 7-8)
- All new development uses workflow
- Existing features migrated on maintenance schedule
- Team fully trained on workflow processes
- Metrics showing improved development velocity
```

### Modern SPA with API
```markdown
## Migration Strategy: Modern SPA

### Phase 1: API Documentation and Context (Week 1)
- Extract API specifications and frontend component structure
- Map state management and data flow patterns
- Document existing component hierarchy and patterns
- Create specialized agents for API and frontend development

### Phase 2: Component Enhancement (Week 2)
- Start with new component development using workflow
- Enhance existing components using prototype-lead agent
- Establish testing patterns for component development
- Document reusable patterns and component libraries

### Phase 3: Feature Module Migration (Weeks 3-4)
- Migrate complete feature modules to workflow management
- Integrate with existing state management
- Enhance API endpoints using architect agent
- Apply workflow to complex user interactions

### Phase 4: Performance and Polish (Week 5)
- Use performance-optimizer agent for identified bottlenecks
- Apply workflow to user experience improvements
- Optimize bundle size and loading performance
- Complete transition to workflow-based development
```

### Microservices Architecture
```markdown
## Migration Strategy: Microservices

### Phase 1: Service Mapping and Analysis (Week 1-2)
- Map service dependencies and communication patterns
- Document deployment and orchestration setup
- Identify service-specific development patterns
- Create specialized agents for each service type

### Phase 2: Single Service Migration (Week 3)
- Choose least critical service for pilot migration
- Apply workflow to service development and deployment
- Test inter-service communication with workflow changes
- Document service-specific workflow adaptations

### Phase 3: Service-by-Service Migration (Weeks 4-8)
- Migrate services based on development frequency
- Coordinate cross-service feature development
- Use deploy-manager for complex deployment orchestration
- Establish workflow patterns for service integration

### Phase 4: Cross-Service Feature Development (Weeks 9-10)
- Use workflow for features spanning multiple services
- Coordinate parallel service development with agents
- Optimize inter-service communication patterns
- Complete migration with full orchestration capabilities
```

## Integration with Existing Tools

### Version Control Integration
```bash
# Preserve existing Git workflows
# Add workflow-specific branch naming conventions
# Integrate workflow context updates with commit messages
# Set up automated context validation on merges

# Example Git integration
git add .claude/
git commit -m "Migrate to Subagent Context Engineering Workflow

Initial migration including:
- Extracted project context from existing codebase
- Generated PRP from implemented features  
- Created specialized agents for project needs
- Preserved existing development processes

🤖 Generated with Claude Code

Co-Authored-By: Claude <noreply@anthropic.com>"
```

### CI/CD Integration
```yaml
# Example CI pipeline enhancement
name: Build and Test with Workflow

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
      
      # Existing test steps preserved
      - run: npm install
      - run: npm test
      
      # Add workflow context validation
      - name: Validate Workflow Context
        run: |
          # Check context file consistency
          # Validate agent configurations
          # Ensure PRP is up-to-date
```

### Development Environment Integration
```json
// package.json additions (preserve existing scripts)
{
  "scripts": {
    // Existing scripts preserved
    "dev": "existing-dev-command",
    "test": "existing-test-command",
    "build": "existing-build-command",
    
    // Add workflow commands
    "workflow:feature": "claude chat -c 'task \"prototype-feature [feature-name]\"'",
    "workflow:test": "claude chat -c 'task \"test-checkpoint\"'",
    "workflow:deploy": "claude chat -c 'task \"deploy-check\"'"
  }
}
```

## Communication and Change Management

### Team Communication Strategy
```markdown
## Migration Communication Plan

### Week Before Migration
- Present workflow benefits and migration plan
- Address team concerns and questions
- Provide workflow overview and training materials
- Set expectations for migration timeline and process

### During Migration
- Daily standups include migration status updates
- Document workflow successes and challenges
- Provide just-in-time training on workflow commands
- Collect feedback on workflow effectiveness

### Post-Migration
- Measure and communicate development velocity improvements
- Document lessons learned and workflow optimizations
- Share success stories and best practices
- Plan advanced workflow feature adoption
```

### Training and Onboarding
```markdown
## Team Training Roadmap

### Phase 1: Workflow Concepts (1 day)
- Overview of context engineering principles
- Introduction to agent specialization
- Understanding workflow command structure
- Hands-on practice with basic commands

### Phase 2: Project-Specific Usage (2 days)
- Using project's specialized agents
- Understanding project context structure
- Practice with feature development workflow
- Integration with existing development tools

### Phase 3: Advanced Workflow (1 week)
- Parallel agent coordination
- Complex feature development patterns
- Troubleshooting workflow issues
- Optimizing workflow for team productivity
```

## Success Metrics and Monitoring

### Migration Success Indicators
```markdown
## Key Performance Indicators

### Development Velocity
- Time from feature conception to deployment
- Defect rate in newly developed features
- Code review cycle time
- Developer satisfaction with development process

### Code Quality
- Automated test coverage
- Code complexity metrics
- Technical debt accumulation rate
- Consistent code pattern adoption

### Team Productivity
- Feature delivery predictability
- Cross-team collaboration effectiveness
- Knowledge sharing and documentation quality
- Developer onboarding time for new features

### Workflow Adoption
- Percentage of development using workflow
- Agent utilization rates
- Context accuracy and usefulness
- Command usage patterns and effectiveness
```

### Monitoring and Optimization
```bash
# Set up workflow metrics collection
# Monitor agent performance and effectiveness
# Track context accuracy and maintenance overhead
# Measure development velocity before and after migration

# Example monitoring setup
echo "Workflow Migration Metrics Dashboard
- Features developed using workflow: 85%
- Average feature development time: 40% reduction
- Code review feedback cycles: 60% reduction  
- Developer satisfaction: 4.2/5 (up from 3.1/5)
- Context accuracy: 94% (validated weekly)
"
```

## Rollback Procedures

### Emergency Rollback
If critical issues arise during migration:

```bash
# 1. Immediate rollback to pre-migration state
git checkout pre-migration-backup-branch

# 2. Restore original development processes
# 3. Document rollback reasons and issues
# 4. Plan resolution approach for identified problems
# 5. Communicate rollback to team with timeline for retry
```

### Partial Rollback
If specific workflow components cause issues:

```bash
# 1. Identify problematic workflow components
# 2. Disable specific agents or commands
# 3. Preserve working workflow elements
# 4. Continue with hybrid approach while resolving issues
# 5. Gradual re-introduction of fixed components
```

## Expected Outcomes

Upon successful migration completion:

### Technical Outcomes
1. **Enhanced Context Management**: Complete project understanding accessible to all team members
2. **Specialized Agent Network**: Project-specific agents handling domain expertise
3. **Improved Development Velocity**: Faster feature development with maintained quality
4. **Better Code Consistency**: Workflow-enforced patterns and standards
5. **Streamlined Testing**: Human-in-the-loop testing with clear scenarios

### Process Outcomes
1. **Predictable Development**: Clear patterns for feature development and deployment
2. **Reduced Context Switching**: Agents maintain specialized context between sessions
3. **Enhanced Collaboration**: Shared understanding through documented context
4. **Risk Mitigation**: Structured approach to complex feature development
5. **Scalable Architecture**: Foundation for handling increasing project complexity

### Business Outcomes
1. **Faster Time to Market**: Reduced development cycles for new features
2. **Higher Quality Deliverables**: Workflow-enforced quality gates and testing
3. **Reduced Technical Debt**: Proactive code quality management
4. **Improved Team Productivity**: Developers can focus on business logic
5. **Better Project Predictability**: Clear visibility into development progress

## Troubleshooting Common Migration Issues

### Context Extraction Problems
**Issue**: Existing codebase context is unclear or incomplete
**Solution**: 
- Use multiple analysis passes with different agents
- Interview team members about business logic
- Review commit history for feature evolution
- Create initial context with explicit unknowns

### Agent Configuration Conflicts
**Issue**: Multiple agents trying to handle overlapping responsibilities
**Solution**:
- Clearly define agent boundaries in subagents.md
- Create coordination protocols between related agents
- Use task sequencing to prevent conflicts
- Document agent interaction patterns

### Integration Resistance
**Issue**: Existing tools or processes conflict with workflow
**Solution**:
- Adapt workflow to existing patterns rather than forcing change
- Create hybrid approaches during transition period
- Document integration points and compromises
- Plan gradual convergence to optimal workflow

### Performance Concerns
**Issue**: Workflow introduces development overhead
**Solution**:
- Optimize agent coordination patterns
- Cache frequently used context information
- Streamline workflow commands for common operations
- Measure and optimize workflow efficiency

---

**Note**: Migration typically takes 2-4 weeks depending on project complexity and team size. The investment in proper migration enables significantly enhanced development velocity and code quality throughout the project's future development lifecycle.