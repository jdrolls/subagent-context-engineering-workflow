# Subagent Context Engineering Workflow

## Project Overview

This is the **Subagent Context Engineering Workflow** - a systematic approach to building web applications using Claude Code's subagent capabilities combined with context engineering principles. The workflow transforms Product Requirements Documents (PRDs) into actionable development plans through specialized AI agents and human-in-the-loop testing.

## Current Project Status

**Workflow State:** Initial Setup  
**Active Phase:** Workflow Development  
**Next Milestone:** Complete Core Agent Implementation

## Core Workflow Philosophy

1. **Human-in-the-Loop Prototyping**: Build incrementally with testing gates
2. **Adaptive Agent Creation**: Generate project-specific agents based on PRD analysis  
3. **Clean Code Focus**: Prioritize simplicity and maintainability from start
4. **Parallel Intelligence**: Use multiple specialized agents simultaneously
5. **Context-Aware Development**: Maintain specialized context while sharing project understanding
6. **Progressive Enhancement**: PRD → PRP → Agents → Build → Test → Deploy

## Development Rules & Conventions

### Code Standards
- Use clear, descriptive variable names
- Write inline documentation for complex logic
- Maintain consistent patterns across components
- Implement accessibility from the start
- Prioritize testability in design decisions
- Follow framework-specific best practices

### Agent Collaboration
- Each agent maintains single responsibility
- Agents communicate through shared context files
- Use `task` tool for parallel agent execution
- Update context files after major changes
- Validate context accuracy regularly

### Testing Philosophy
- Test early and often
- Human testing at natural breakpoints
- Document all test results
- Fix issues before continuing development
- Build comprehensive test scenarios

### Context Management
- Keep context files current and accurate
- Archive outdated decisions appropriately
- Maintain single source of truth
- Use context-keeper agent for validation
- Review context weekly for cleanup

## File Structure & Organization

```
.claude/
├── claude.md                    # This file - Master context
├── subagents.md                # Agent registry and capabilities
├── commands/                   # Workflow orchestration commands
├── agents/core/               # Always-present core agents
├── agents/project/            # Project-specific agents (auto-generated)
└── context/                   # Project state and decisions
```

## Active Agents

### Core Agents (Always Available)
- **prd-analyzer**: Converts PRDs to Project Requirement Plans (PRPs)
- **architect**: System design and technical decisions  
- **prototype-lead**: Rapid clean prototyping coordination
- **test-coordinator**: Human testing workflow management
- **context-keeper**: Real-time context maintenance and validation
- **deploy-manager**: Multi-platform deployment orchestration

### Project Agents (Generated Based on Requirements)
*Auto-generated based on PRD analysis. Examples include:*
- websocket-specialist, payment-integration, ai-integration, email-automation, etc.

## Workflow Commands

### Primary Commands
- `/init-from-prd [prd-file]` - Initialize new project from PRD
- `/prototype-feature "[name]"` - Rapid feature prototyping with checkpoints
- `/test-checkpoint` - Human testing coordination
- `/refactor-clean "[target]"` - Code cleanup while maintaining functionality
- `/deploy-check [platforms]` - Pre-deployment validation and execution

### Utility Commands
- `/add-feature "[description]"` - Add features to existing projects
- `/migrate-to-workflow` - Adopt workflow in existing codebases

## Current Session Context

### Recently Completed
- Initial workflow research and planning
- Directory structure creation
- Master context file setup

### In Progress
- Core agent implementation
- Command system development
- Context template creation

### Next Steps
1. Complete all core agents with YAML frontmatter
2. Implement workflow command system
3. Create context file templates
4. Generate documentation and examples

## Technical Decisions

### Context Window Optimization
- Use focused subagents to preserve main context
- Implement token-efficient communication patterns
- Leverage extended thinking for complex decisions
- Maintain context accuracy through automated updates

### Agent Design Principles
- Single responsibility per agent
- Clear tool access boundaries
- Detailed system prompts with specific instructions
- Version control for team collaboration
- YAML frontmatter for configuration

## Known Issues & Limitations

### Current Limitations
- Workflow still in development phase
- No production usage examples yet
- Documentation incomplete

### Planned Improvements
- Add comprehensive examples
- Create migration scripts
- Implement advanced deployment strategies
- Add performance monitoring

## Project Dependencies

### Required Tools
- Claude Code (latest version)
- Node.js 18+ (for web projects)
- Git for version control

### Recommended Tools
- Modern IDE with Claude Code integration
- Testing frameworks (project-specific)
- Deployment platforms (Railway, Vercel, etc.)

## Inspiration & Credits

This workflow is inspired by context engineering patterns from [coleam00/context-engineering-intro](https://github.com/coleam00/context-engineering-intro) and builds upon those concepts with Claude Code's subagent capabilities for modern web development.

## Quick Reference

### Essential Commands
```bash
/init-from-prd [prd.md]          # Start new project
/prototype-feature "[name]"       # Build feature
/test-checkpoint                  # Test with human
/refactor-clean "[area]"         # Clean up code
/deploy-check [platforms]         # Deploy app
```

### Key Files
- `context/prp.md` - Project Requirements Plan
- `context/current-state.md` - Development status
- `context/test-results.md` - Testing history
- `context/tech-decisions.md` - Architecture choices

---

*This file is automatically maintained by the context-keeper agent and should reflect the current state of the workflow development.*