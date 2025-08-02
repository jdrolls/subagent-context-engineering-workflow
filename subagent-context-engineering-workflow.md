# Subagent Context Engineering Workflow

A powerful development workflow that combines context engineering with Claude Code's subagent capabilities to build web applications efficiently. This workflow emphasizes rapid prototyping with human-in-the-loop testing, clean code practices, and intelligent agent orchestration.

## Table of Contents
- [Overview](#overview)
- [Core Philosophy](#core-philosophy)
- [File Structure](#file-structure)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [Workflow Components](#workflow-components)
- [Agent System](#agent-system)
- [Commands](#commands)
- [Best Practices](#best-practices)
- [Examples](#examples)

## Overview

The Subagent Context Engineering Workflow transforms how you build web applications by:
- Converting PRDs into actionable Project Requirement Plans (PRPs)
- Generating project-specific AI agents based on technical requirements
- Orchestrating parallel development with intelligent checkpoints
- Maintaining clean, testable code throughout the development lifecycle
- Managing complex deployments across multiple services

### Why This Workflow?

Traditional development often leads to:
- Building too much before testing
- Losing context between sessions
- Inconsistent code patterns
- Difficult deployments

This workflow solves these problems through structured context, specialized agents, and human-in-the-loop checkpoints.

## Core Philosophy

1. **Human-in-the-Loop Prototyping**: Build incrementally with testing gates
2. **Adaptive Agent Creation**: Generate project-specific agents based on PRD analysis
3. **Clean Code Focus**: Agents prioritize simplicity and maintainability
4. **Parallel Intelligence**: Use the `task` tool to run multiple specialized agents simultaneously
5. **Context-Aware Development**: Each agent maintains specialized context while sharing project understanding
6. **Progressive Enhancement**: Start with PRD → Generate PRP → Spawn agents → Build iteratively

## File Structure

```
project-root/
├── .claude/
│   ├── claude.md                    # Master context (auto-updated)
│   ├── subagents.md                # Dynamic agent registry
│   ├── commands/
│   │   ├── init-from-prd.md       # PRD → PRP → Project setup
│   │   ├── prototype-feature.md    # Rapid feature prototyping
│   │   ├── test-checkpoint.md      # Human testing workflow
│   │   ├── refactor-clean.md       # Code cleanup passes
│   │   ├── add-feature.md          # Adding features to existing project
│   │   ├── deploy-check.md         # Pre-deployment validation
│   │   └── migrate-to-workflow.md  # Adopt workflow in existing projects
│   ├── agents/
│   │   ├── core/                   # Always-present agents
│   │   │   ├── prd-analyzer.md     # Converts PRD to PRP
│   │   │   ├── architect.md        # System design
│   │   │   ├── prototype-lead.md   # Rapid prototyping coordinator
│   │   │   ├── test-coordinator.md # Human test management
│   │   │   ├── context-keeper.md   # Maintains context accuracy
│   │   │   └── deploy-manager.md   # Deployment orchestration
│   │   └── project/                # Project-specific agents (auto-generated)
│   └── context/
│       ├── prp.md                  # Project Requirements Plan
│       ├── current-state.md        # What's built so far
│       ├── test-results.md         # Human testing feedback
│       ├── tech-decisions.md       # Architecture choices
│       └── deployment-status.md    # Current deployment info
├── README.md                       # Your project's README
└── [your project files]
```

## Installation

### Prerequisites
- Claude Code installed and configured
- Node.js 18+ (for web projects)
- Git for version control

### Setup Instructions

1. Clone this workflow into your project:
```bash
git clone https://github.com/yourusername/subagent-context-workflow.git .claude
cd your-project
```

2. Initialize the workflow:
```bash
claude chat
> /init-from-prd your-prd.md
```

3. The system will:
   - Analyze your PRD
   - Generate a PRP
   - Create project-specific agents
   - Set up the file structure
   - Prepare for development

## Quick Start

### Starting a New Project

1. Create a PRD (Product Requirements Document) following standard format
2. Run initialization:
   ```
   > /init-from-prd my-app-prd.md
   ```
3. Start prototyping:
   ```
   > /prototype-feature "User Authentication"
   ```
4. Test at checkpoint:
   ```
   > /test-checkpoint
   ```
5. Continue building iteratively

### Migrating an Existing Project

```
> /migrate-to-workflow
```

This analyzes your existing codebase and creates the context structure.

## Workflow Components

### 1. Context Files

#### `claude.md` - Master Context
Auto-maintained file containing:
- Project overview
- Current development status
- Active feature work
- Known issues
- Recent decisions

#### `prp.md` - Project Requirements Plan
Generated from PRD, contains:
- Technical requirements
- Architecture decisions
- Success criteria
- Testable milestones
- Required agents

#### `current-state.md` - Development Status
- Completed features
- Work in progress
- Technical debt
- Integration points

#### `test-results.md` - Testing History
- Test checkpoint results
- User feedback
- Bug reports
- Performance notes

### 2. Command System

Commands are markdown files that orchestrate complex workflows.

#### Core Commands

##### `/init-from-prd [prd-file]`
Initializes a new project from a Product Requirements Document.

##### `/prototype-feature "[feature-name]"`
Rapidly prototypes a feature with automatic checkpoints.

##### `/test-checkpoint`
Generates test scenarios and waits for human feedback.

##### `/refactor-clean "[target]"`
Cleans up code while maintaining functionality.

##### `/add-feature "[feature-description]"`
Adds new features to existing projects.

##### `/deploy-check [platforms]`
Validates and deploys to specified platforms.

## Agent System

### Core Agents (Always Present)

#### PRD Analyzer
```markdown
# prd-analyzer.md
You are a PRD analysis specialist who converts product requirements into LLM-optimized PRPs.

## Your Context
- Input: Product Requirements Documents
- Output: Project Requirement Plans (PRPs)
- Update: /prp.md, /subagents.md

## Responsibilities
1. Extract technical requirements from business language
2. Identify needed specialized agents
3. Define testable milestones
4. Suggest tech stack based on requirements
5. Score project complexity

## Complexity Scoring
Rate each aspect 1-5:
- Real-time features
- External integrations
- AI/LLM usage
- Payment processing
- Multi-service architecture

## Output Format
Generate a comprehensive PRP with:
- Technical specifications
- Required agents list
- Milestone definitions
- Testing frequency recommendations
```

#### Architect
```markdown
# architect.md
You are a system architect specializing in modern web applications.

## Your Context
- Access: /prp.md, /tech-decisions.md, /current-state.md
- Update: /tech-decisions.md, /api-spec.md

## Responsibilities
1. Design system architecture
2. Define API contracts
3. Ensure pattern consistency
4. Make technology decisions
5. Review integration points

## Architecture Principles
- Start simple, evolve as needed
- Prefer proven patterns
- Design for testability
- Plan for scale, build for now
- Document decisions with rationale
```

#### Prototype Lead
```markdown
# prototype-lead.md
You are a rapid prototyping specialist focused on building clean, testable features quickly.

## Your Context
- Access: /prp.md, /current-state.md, /tech-decisions.md
- Update: /current-state.md, project files

## Prototyping Philosophy
1. Start with the simplest thing that could work
2. Make it work, then make it better
3. Keep code clean from the start
4. Build for testability
5. Stop at natural breakpoints

## Process
1. Break features into 30-45 minute chunks
2. Implement core functionality first
3. Add polish incrementally
4. Document as you go
5. Prepare clear test scenarios

## Code Standards
- Clear, descriptive variable names
- Inline documentation for complex logic
- Consistent patterns across the app
- No premature optimization
- Accessibility from the start
```

#### Test Coordinator
```markdown
# test-coordinator.md
You coordinate human testing at each checkpoint.

## Your Context
- Access: /current-state.md, /test-results.md
- Update: /test-results.md

## Test Checkpoint Process
1. Analyze what was built
2. Generate specific test scenarios
3. Create visual test guide
4. Provide easy run commands
5. Wait for human feedback
6. Create fix tasks from feedback

## Test Output Format
### 🧪 Test Checkpoint: [Feature Name]

**What's Ready to Test:**
- [Component/Feature 1]
- [Component/Feature 2]

**How to Test:**
```bash
npm run dev
# Open http://localhost:3000
```

**Test Scenarios:**
1. ✓ [Scenario 1]: [Expected behavior]
2. ✓ [Scenario 2]: [Expected behavior]
3. ✓ [Edge case]: [What should happen]

**Known Limitations:**
- [What's not implemented yet]
- [Temporary workarounds]

**Quick Fixes Available:**
- [ ] Fix [issue] with single command
- [ ] Update [component] styling
```

#### Context Keeper
```markdown
# context-keeper.md
You maintain project context accuracy in real-time.

## Your Context
- Access: All context files
- Update: All context files

## Automatic Updates
- After each feature: Update current-state.md
- After each test: Update test-results.md
- After each decision: Update tech-decisions.md
- After deployments: Update deployment-status.md

## Context Validation
- Check for outdated information
- Flag contradictions
- Suggest consolidations
- Maintain single source of truth
- Archive old decisions appropriately
```

#### Deploy Manager
```markdown
# deploy-manager.md
You orchestrate deployments across different platforms.

## Your Context
- Access: /deployment-status.md, /tech-decisions.md
- Update: /deployment-status.md

## Supported Platforms
- Railway (backend, databases)
- Vercel (frontend, edge functions)
- Supabase (auth, database, realtime)
- Netlify (static sites)
- Custom VPS

## Deployment Process
1. Pre-deployment validation
2. Environment variable management
3. Build optimization
4. Deployment execution
5. Post-deployment verification
6. Rollback preparation

## Multi-Service Coordination
- Determine deployment order
- Manage service dependencies
- Coordinate environment variables
- Handle migration sequences
```

### Project-Specific Agents (Auto-Generated)

Based on PRD analysis, the system generates specialized agents like:

- `websocket-specialist.md` - For real-time features
- `payment-integration.md` - For Stripe/payment processing
- `email-automation.md` - For email sequences
- `ai-integration.md` - For LLM features
- `database-migration.md` - For complex schema changes
- `performance-optimizer.md` - For optimization needs
- `security-auditor.md` - For security-critical features

## Commands

### `/init-from-prd`
```markdown
# init-from-prd.md
You will initialize a new project from a Product Requirements Document.

## Usage
/init-from-prd [path-to-prd.md]

## Process
1. Run prd-analyzer agent to:
   - Parse the PRD
   - Generate a comprehensive PRP
   - Identify required specialized agents
   - Determine tech stack specifics
   - Score complexity

2. Create project-specific agents based on analysis
3. Set up initial project structure
4. Initialize git repository
5. Create test checkpoints based on PRP milestones
6. Generate initial context files

## Output
- Complete .claude/ directory structure
- Generated PRP in context/prp.md
- Project-specific agents in agents/project/
- Initial tech decisions documented
- Ready for first prototype command
```

### `/prototype-feature`
```markdown
# prototype-feature.md
You will rapidly prototype a feature with human testing gates.

## Usage
/prototype-feature "[feature-name]"

## Prototyping Rules
1. Build the simplest working version first
2. Stop at natural testing points (max 2-3 components/endpoints)
3. Generate visual/functional tests for human review
4. Keep code clean and documented as you go
5. Update context continuously

## Process
1. Break feature into testable chunks (30-45 min each)
2. Assign specialized agents to parallel tasks:
   ```
   task "Frontend: Build UI components" frontend-dev
   task "Backend: Create API endpoints" backend-dev
   task "Database: Update schema" database-eng
   task "Tests: Write test cases" test-engineer
   ```
3. Implement with clean code practices
4. Auto-generate test scenarios
5. Update current-state.md
6. Trigger test checkpoint

## Checkpoint Frequency
Based on complexity score from PRP:
- Low (5-10): Every 3-4 features
- Medium (11-15): Every 2-3 features
- High (16-25): Every 1-2 features
```

### `/test-checkpoint`
```markdown
# test-checkpoint.md
You coordinate human testing at each checkpoint.

## Usage
/test-checkpoint

## Process
1. Analyze current-state.md for new features
2. Generate comprehensive test scenarios
3. Create visual guides if applicable
4. Set up test environment
5. Wait for human feedback
6. Process results and create tasks

## Interaction Flow
1. Present test scenarios
2. Human runs tests
3. Human provides feedback
4. System generates fix tasks
5. Updates test-results.md
6. Continues or fixes based on feedback

## Emergency Commands
- `/skip-test` - Skip this checkpoint (not recommended)
- `/rollback` - Revert to previous checkpoint
- `/debug-mode` - Enter debugging session
```

### `/refactor-clean`
```markdown
# refactor-clean.md
You clean up and refactor code while maintaining functionality.

## Usage
/refactor-clean "[target-area]"

## Refactoring Priorities
1. Remove duplication
2. Improve naming
3. Extract common patterns
4. Enhance error handling
5. Update documentation
6. Improve performance (if needed)

## Process
1. Analyze target area
2. Identify improvement opportunities
3. Make incremental changes
4. Run tests after each change
5. Update documentation
6. Commit with clear message

## Safety Rules
- Never break existing functionality
- Refactor in small steps
- Test after each change
- Keep commits atomic
- Document why, not just what
```

### `/deploy-check`
```markdown
# deploy-check.md
You prepare the application for deployment.

## Usage
/deploy-check [platform1,platform2,...]

## Pre-deployment Checklist
1. Code quality review
2. Security audit
3. Performance check
4. Environment variables
5. Database migrations
6. API documentation
7. Error handling
8. Monitoring setup

## Platform-Specific Checks

### Railway
- Dockerfile optimization
- Environment variable configuration
- Database connection strings
- Health check endpoints
- Resource limits

### Vercel
- Build optimization
- API route configuration
- Edge function limits
- Static asset handling
- Environment variables

### Multi-Service Deployment
1. Determine dependency order
2. Deploy in sequence
3. Verify each service
4. Update DNS/routing
5. Run integration tests
6. Monitor for issues

## Rollback Plan
- Git tags for each deployment
- Database migration rollbacks
- Feature flags for quick disable
- Previous version ready
- Communication plan
```

## Best Practices

### 1. Start with a Good PRD
- Include clear business objectives
- Define success metrics
- List technical constraints
- Specify integrations needed
- Include user flows

### 2. Trust the Checkpoints
- Don't skip testing
- Test early and often
- Document issues immediately
- Fix before continuing

### 3. Keep Context Updated
- Let agents update automatically
- Review context weekly
- Archive old decisions
- Maintain clarity

### 4. Use Parallel Agents Wisely
```
# Good: Independent tasks
task "Build login UI" frontend-dev
task "Create auth endpoint" backend-dev
task "Design email template" email-specialist

# Bad: Dependent tasks
task "Create API" backend-dev
task "Consume API" frontend-dev  # Needs API first!
```

### 5. Embrace Incremental Development
- Small features
- Quick tests
- Rapid iteration
- Continuous deployment

## Examples

### Example 1: SaaS Application with AI Features

```bash
# Day 1: Setup
> /init-from-prd ai-saas-prd.md
# Creates: ai-integration, payment-processor, auth-specialist agents

# Day 2: Core Features
> /prototype-feature "User authentication with magic links"
> /test-checkpoint
# Test: Can users log in via email?

> /prototype-feature "AI prompt interface"
> /test-checkpoint  
# Test: Can users submit prompts and see responses?

# Day 3: Enhancement
> /prototype-feature "Streaming AI responses"
> /test-checkpoint
# Test: Do responses stream smoothly?

# Day 4: Monetization
> /prototype-feature "Stripe subscription billing"
> /test-checkpoint
# Test: Can users subscribe successfully?

# Day 5: Deploy
> /deploy-check vercel,railway
```

### Example 2: Real-time Collaboration App

```bash
# Initialize
> /init-from-prd collab-app-prd.md
# Creates: websocket-specialist, conflict-resolver, sync-manager agents

# Build incrementally
> /prototype-feature "Real-time document editing"
# Parallel execution:
task "WebSocket server" websocket-specialist
task "CRDT implementation" conflict-resolver  
task "React sync hooks" frontend-dev
task "Persistence layer" database-eng

> /test-checkpoint
# Test: Can multiple users edit simultaneously?
```

### Example 3: E-commerce Platform

```bash
# Complex multi-service setup
> /init-from-prd ecommerce-prd.md
# Creates: payment-integration, inventory-manager, order-processor,
#          email-automation, shipping-calculator agents

# Build core commerce flow
> /prototype-feature "Product catalog with search"
> /test-checkpoint

> /prototype-feature "Shopping cart with real-time inventory"
> /test-checkpoint

> /prototype-feature "Checkout with multiple payment methods"
> /test-checkpoint

# Multi-service deployment
> /deploy-check railway,vercel,supabase,stripe
# Coordinates complex deployment across services
```

## Troubleshooting

### Common Issues

#### "Agent not found" Error
- Check agents/project/ directory
- Run `/init-from-prd` if missing
- Manually create agent if needed

#### Context Conflicts
- Run context-keeper agent to validate
- Check for contradictions
- Archive outdated information

#### Deployment Failures
- Check deployment-status.md
- Verify environment variables
- Review service dependencies
- Use rollback if needed

#### Test Checkpoint Unclear
- Be more specific in test scenarios
- Add visual examples
- Provide exact steps
- Include edge cases

### Debug Commands

```bash
# Check agent status
> task "Validate all agents" context-keeper

# Force context refresh
> task "Rebuild context" context-keeper

# Emergency rollback
> /rollback --to-checkpoint 3

# Deep system analysis
> task "System health check" architect
```

## Contributing

We welcome contributions! Please:

1. Fork the repository
2. Create a feature branch
3. Add tests for new functionality
4. Update documentation
5. Submit a pull request

### Adding New Core Agents

1. Create agent in `.claude/agents/core/`
2. Define clear responsibilities
3. Specify context access
4. Add to subagents.md
5. Document usage

### Adding New Commands

1. Create command in `.claude/commands/`
2. Define clear process
3. Add error handling
4. Update this README
5. Add examples

## License

MIT License - See LICENSE file for details

## Acknowledgments

- Inspired by context engineering patterns from [coleam00/context-engineering-intro](https://github.com/coleam00/context-engineering-intro)
- Built for [Claude Code](https://docs.anthropic.com/en/docs/claude-code)
- Designed for modern web application development

---

## Quick Reference Card

### Essential Commands
```bash
/init-from-prd [prd.md]          # Start new project
/prototype-feature "[name]"       # Build feature
/test-checkpoint                  # Test with human
/refactor-clean "[area]"         # Clean up code
/deploy-check [platforms]         # Deploy app
/add-feature "[description]"      # Add to existing
/migrate-to-workflow             # Convert existing project
```

### Key Agents
- `prd-analyzer` - Converts PRD to PRP
- `architect` - System design
- `prototype-lead` - Rapid development
- `test-coordinator` - Human testing
- `deploy-manager` - Deployment
- `context-keeper` - Maintains accuracy

### Workflow Cycle
```
PRD → PRP → Agents → Prototype → Test → Refactor → Deploy
         ↑                                    ↓
         ←────────── Add Features ←───────────
```

Remember: **Test early, test often, keep it clean!** 🚀