# Initialize Project from PRD

You will initialize a new project from a Product Requirements Document using the Subagent Context Engineering Workflow.

## Usage
```
/init-from-prd [path-to-prd.md]
```

## Process Overview

This command orchestrates the complete project initialization process, transforming a business-focused PRD into a fully configured development environment with specialized agents and clear technical direction.

## Step-by-Step Process

### Step 1: PRD Analysis and PRP Generation
Invoke the prd-analyzer agent to perform comprehensive analysis:

```
task "Analyze PRD and generate Project Requirement Plan" prd-analyzer

Instructions for prd-analyzer:
1. Read and thoroughly analyze the provided PRD
2. Extract all functional and non-functional requirements
3. Assess project complexity across all dimensions
4. Identify required specialized agents for this project
5. Generate comprehensive PRP with technical specifications
6. Create testable milestones based on complexity assessment
7. Update context/prp.md with complete analysis
8. Update subagents.md with required project-specific agents
```

### Step 2: Architecture Planning
Invoke the architect agent to establish technical foundation:

```
task "Design system architecture based on PRP" architect

Instructions for architect:
1. Review the generated PRP for technical requirements
2. Design overall system architecture and component structure
3. Select appropriate technology stack based on requirements
4. Define API contracts and database schemas
5. Plan integration strategies for external services
6. Document all decisions with clear rationale
7. Update context/tech-decisions.md with architectural choices
8. Create initial API specification if applicable
```

### Step 3: Project-Specific Agent Creation
Based on PRP analysis, create specialized agents for project needs:

```bash
# Example agent creation based on common requirements

# For real-time features
if [real-time features required]; then
  create agents/project/websocket-specialist.md
fi

# For payment processing
if [payment features required]; then
  create agents/project/payment-integration.md
fi

# For AI/LLM features
if [AI features required]; then
  create agents/project/ai-integration.md
fi

# For email automation
if [email features required]; then
  create agents/project/email-automation.md
fi

# For complex database operations
if [complex data operations]; then
  create agents/project/database-migration.md
fi

# For performance-critical applications
if [high performance requirements]; then
  create agents/project/performance-optimizer.md
fi

# For security-sensitive applications
if [security/compliance requirements]; then
  create agents/project/security-auditor.md
fi
```

### Step 4: Context File Initialization
Create and populate all necessary context files:

```
task "Initialize project context files" context-keeper

Instructions for context-keeper:
1. Create context/current-state.md with initial project status
2. Create context/test-results.md with testing framework
3. Initialize context/deployment-status.md with target platforms
4. Set up tracking for all identified milestones
5. Establish baseline for context validation
6. Create initial development roadmap
```

### Step 5: Project Structure Setup
Create initial project structure based on technical decisions:

```bash
# Create basic project structure
mkdir -p src/{components,pages,utils,services}
mkdir -p docs/{api,deployment}
mkdir -p tests/{unit,integration,e2e}

# Initialize package.json or equivalent based on tech stack
# Set up development environment configuration
# Create initial configuration files
```

### Step 6: Development Environment Setup
Configure development tools and processes:

```bash
# Initialize version control
git init
git add .
git commit -m "Initial commit: Project setup from PRD analysis

🤖 Generated with Claude Code

Co-Authored-By: Claude <noreply@anthropic.com>"

# Set up development scripts based on tech stack
# Configure linting and formatting tools
# Set up testing framework
# Configure CI/CD pipelines if specified
```

### Step 7: First Milestone Planning
Prepare for immediate development start:

```
task "Plan first development milestone" prototype-lead

Instructions for prototype-lead:
1. Review PRP milestones and select first development target
2. Break first milestone into implementable chunks
3. Identify any dependencies or prerequisites
4. Plan development sequence for first features
5. Prepare for first prototype-feature command
6. Update current-state.md with immediate next steps
```

## Template Files Creation

### .env.example Template
Create environment variable template:
```bash
# .env.example
# Copy to .env and fill in actual values

# Database
DATABASE_URL=postgresql://localhost:5432/myapp_dev

# Authentication
JWT_SECRET=your-jwt-secret-here

# External Services
# (Generated based on PRP requirements)

# Development
NODE_ENV=development
PORT=3000
```

### Basic README Template
Create initial project README:
```markdown
# [Project Name]

[Brief description from PRD]

## Development Setup

1. Clone the repository
2. Copy `.env.example` to `.env` and configure
3. Install dependencies: `npm install`
4. Start development server: `npm run dev`

## Project Structure

Generated using Subagent Context Engineering Workflow from PRD analysis.

See `.claude/context/prp.md` for complete project requirements and technical specifications.

## Available Commands

- `/prototype-feature "[name]"` - Build new features
- `/test-checkpoint` - Human testing workflow
- `/refactor-clean "[area]"` - Code cleanup
- `/deploy-check` - Deployment preparation

## Architecture

See `.claude/context/tech-decisions.md` for architectural decisions and rationale.
```

## Validation Checks

Before completing initialization, verify:

### ✅ PRP Quality Check
- [ ] All PRD requirements captured in PRP
- [ ] Complexity assessment completed
- [ ] Technology stack selected with rationale
- [ ] Milestones are testable and specific
- [ ] Success criteria are measurable

### ✅ Agent Configuration Check
- [ ] All required core agents available
- [ ] Project-specific agents created based on needs
- [ ] Agent responsibilities clearly defined
- [ ] No capability gaps identified

### ✅ Context File Setup Check
- [ ] All context files created and initialized
- [ ] Cross-references between files established
- [ ] Single source of truth maintained
- [ ] Context validation baseline established

### ✅ Development Environment Check
- [ ] Project structure follows architectural decisions
- [ ] Development tools configured
- [ ] Version control initialized
- [ ] Environment variables templated
- [ ] Documentation scaffolding in place

### ✅ Readiness Assessment
- [ ] First milestone clearly defined
- [ ] Development sequence planned
- [ ] Testing strategy established
- [ ] Deployment targets identified
- [ ] Ready for first `/prototype-feature` command

## Expected Outputs

Upon successful completion:

1. **Complete PRP** in `context/prp.md`
2. **Technical Architecture** in `context/tech-decisions.md`
3. **Specialized Agents** in `agents/project/` (as needed)
4. **Initial Context** in all context files
5. **Project Structure** with development environment
6. **Documentation** with clear next steps

## Error Handling

### If PRD is incomplete or unclear:
1. Document specific areas needing clarification
2. Make reasonable assumptions and flag them
3. Create PRP with explicit assumptions section
4. Recommend PRD improvements for future projects

### If technology constraints conflict with requirements:
1. Document the conflicts clearly
2. Propose alternative approaches
3. Flag risks and trade-offs
4. Recommend requirement adjustments if needed

### If project complexity exceeds recommended limits:
1. Suggest project scope reduction
2. Recommend phased delivery approach
3. Identify high-risk areas requiring special attention
4. Plan additional checkpoints and validation

## Communication Pattern

This command coordinates multiple agents in sequence:
1. prd-analyzer → architect (PRP provides architecture input)
2. architect → context-keeper (Technical decisions inform context)
3. context-keeper → prototype-lead (Context enables development planning)

Each agent updates shared context files, enabling the next agent to build upon previous work.

## Success Metrics

Project initialization is successful when:
- All agents can access needed context information
- Development can begin immediately with `/prototype-feature`
- Clear testing and deployment pathway established
- Human stakeholder has clear understanding of scope and timeline
- Technical team has actionable implementation plan

---

**Note**: This initialization process typically takes 15-30 minutes depending on project complexity. The investment in thorough setup enables much faster, higher-quality development throughout the project lifecycle.