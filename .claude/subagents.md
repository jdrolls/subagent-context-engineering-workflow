# Subagent Registry

This file maintains a registry of all available subagents in the Subagent Context Engineering Workflow. Agents are organized by category and include their capabilities, responsibilities, and current status.

## Core Agents (Always Available)

### prd-analyzer
**File:** `agents/core/prd-analyzer.md`  
**Status:** ✅ Available  
**Complexity Scoring:** ⭐⭐⭐⭐⭐ (Expert Level)

**Responsibilities:**
- Convert Product Requirements Documents to Project Requirement Plans (PRPs)
- Extract technical requirements from business language
- Identify required specialized agents for project
- Define testable milestones and success criteria
- Suggest optimal tech stack based on requirements
- Score project complexity across multiple dimensions

**Context Access:**
- Reads: PRD files, existing project structure
- Updates: `context/prp.md`, `subagents.md`

**Key Capabilities:**
- Business-to-technical translation
- Agent requirement analysis
- Complexity assessment
- Milestone definition

---

### architect
**File:** `agents/core/architect.md`  
**Status:** ✅ Available  
**Complexity Scoring:** ⭐⭐⭐⭐⭐ (Expert Level)

**Responsibilities:**
- Design system architecture and patterns
- Define API contracts and data models
- Ensure consistency across application
- Make technology and framework decisions
- Review and approve integration points

**Context Access:**
- Reads: `context/prp.md`, `context/current-state.md`
- Updates: `context/tech-decisions.md`, API specifications

**Key Capabilities:**
- System design
- API specification
- Technology selection
- Pattern consistency
- Integration planning

---

### prototype-lead
**File:** `agents/core/prototype-lead.md`  
**Status:** ✅ Available  
**Complexity Scoring:** ⭐⭐⭐⭐ (Advanced)

**Responsibilities:**
- Coordinate rapid feature prototyping
- Implement clean, testable code quickly
- Break features into manageable chunks
- Maintain code quality during rapid development
- Prepare clear checkpoint scenarios

**Context Access:**
- Reads: `context/prp.md`, `context/current-state.md`, `context/tech-decisions.md`
- Updates: `context/current-state.md`, project source files

**Key Capabilities:**
- Rapid prototyping
- Clean code implementation
- Feature decomposition
- Development coordination
- Quality maintenance

---

### test-coordinator
**File:** `agents/core/test-coordinator.md`  
**Status:** ✅ Available  
**Complexity Scoring:** ⭐⭐⭐ (Intermediate)

**Responsibilities:**
- Coordinate human testing at checkpoints
- Generate comprehensive test scenarios
- Create visual testing guides
- Process human feedback into actionable tasks
- Maintain testing history and patterns

**Context Access:**
- Reads: `context/current-state.md`, `context/test-results.md`
- Updates: `context/test-results.md`

**Key Capabilities:**
- Test scenario generation
- Human-AI testing coordination
- Feedback processing
- Testing documentation
- Quality assurance

---

### context-keeper
**File:** `agents/core/context-keeper.md`  
**Status:** ✅ Available  
**Complexity Scoring:** ⭐⭐⭐⭐ (Advanced)

**Responsibilities:**
- Maintain accuracy of all context files
- Validate information consistency
- Archive outdated decisions
- Flag contradictions and conflicts
- Ensure single source of truth

**Context Access:**
- Reads: All context files
- Updates: All context files

**Key Capabilities:**
- Context validation
- Information accuracy
- Conflict detection
- Data archival
- Truth maintenance

---

### deploy-manager
**File:** `agents/core/deploy-manager.md`  
**Status:** ✅ Available  
**Complexity Scoring:** ⭐⭐⭐⭐⭐ (Expert Level)

**Responsibilities:**
- Orchestrate deployments across platforms
- Manage environment variables and secrets
- Coordinate multi-service deployments
- Handle migration sequences
- Provide rollback capabilities

**Context Access:**
- Reads: `context/deployment-status.md`, `context/tech-decisions.md`
- Updates: `context/deployment-status.md`

**Key Capabilities:**
- Multi-platform deployment
- Environment management
- Service coordination
- Migration handling
- Rollback planning

## Project-Specific Agents (Auto-Generated)

*These agents are automatically generated based on PRD analysis. Examples include:*

### Common Project Agent Types

**websocket-specialist**
- Real-time communication features
- WebSocket server management
- Live data synchronization

**payment-integration**
- Stripe/payment processing
- Subscription management
- Financial compliance

**ai-integration**
- LLM API integration
- Prompt engineering
- AI workflow coordination

**email-automation**
- Email sequence management
- Template systems
- Delivery optimization

**database-migration**
- Schema evolution
- Data migration scripts
- Database optimization

**performance-optimizer**
- Application performance tuning
- Bundle optimization
- Caching strategies

**security-auditor**
- Security vulnerability assessment
- Authentication systems
- Data protection compliance

## Agent Capability Matrix

| Agent | Code Generation | System Design | Testing | Deployment | Context Management |
|-------|----------------|---------------|---------|------------|------------------|
| prd-analyzer | ⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐ | ⭐⭐⭐⭐ |
| architect | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐ | ⭐⭐ | ⭐⭐⭐ |
| prototype-lead | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐ | ⭐⭐⭐ |
| test-coordinator | ⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐ | ⭐⭐⭐ |
| context-keeper | ⭐ | ⭐⭐ | ⭐⭐ | ⭐ | ⭐⭐⭐⭐⭐ |
| deploy-manager | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ |

## Agent Invocation Patterns

### Automatic Delegation
Agents are automatically invoked based on task context and current workflow phase.

### Explicit Invocation
Use agent names directly in tasks:
```bash
task "Analyze requirements" prd-analyzer
task "Design database schema" architect
task "Build user interface" prototype-lead
```

### Parallel Execution
Multiple agents can work simultaneously on independent tasks:
```bash
task "Frontend: Build UI components" prototype-lead
task "Backend: Create API endpoints" architect
task "Database: Update schema" architect
task "Tests: Generate scenarios" test-coordinator
```

### Sequential Workflows
Some agents must work in sequence:
1. prd-analyzer → architect → prototype-lead
2. prototype-lead → test-coordinator → context-keeper
3. architect → deploy-manager

## Agent Communication

### Shared Context Files
Agents communicate through shared context files in the `context/` directory.

### Update Protocols
- Agents update context files after completing major tasks
- context-keeper validates all updates for consistency
- Conflicts are flagged for human resolution

### Status Reporting
Each agent maintains its current status and recent activities in the relevant context files.

## Agent Management

### Adding New Project Agents
1. Identify need through PRD analysis
2. Create agent file with YAML frontmatter
3. Define responsibilities and context access
4. Update this registry
5. Test agent integration

### Updating Core Agents
1. Modify agent file
2. Update capabilities in this registry
3. Test with existing workflows
4. Document changes

### Deprecating Agents
1. Mark as deprecated in registry
2. Archive agent file
3. Update documentation
4. Migrate responsibilities if needed

---

*This registry is automatically maintained by the context-keeper agent and reflects the current state of all available subagents.*