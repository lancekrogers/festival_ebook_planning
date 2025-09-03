# Festival Methodology - AI Agent Build System

Festival methodology is a goal-oriented project management system designed specifically for AI agent development workflows. It organizes work into sequential phases (festivals) with parallel tasks that build systematically toward concrete objectives.

## Quick Start Guide

### 1. Set Up Your Project Workspace

Create a festival directory in your project workspace:
```
your_project_workspace/
├── your_repos/           # Your existing repositories
└── festivals/            # Festival planning directory
```

### 2. Copy the Template Files

Copy these 4 files from `build_system/` to your `festivals/` directory:
- `FESTIVAL_SOFTWARE_PROJECT_MANAGEMENT.md` - Core methodology documentation
- `COMMON_INTERFACES_TEMPLATE.md` - Template for defining system interfaces
- `TASK_TEMPLATE.md` - Template for individual tasks
- `FESTIVAL_RULES_TEMPLATE.md` - Template for project standards

### 3. Create Your Festival

Tell your AI agent:
> "Please fully review the 4 markdown files to understand the festival methodology, then create a festival for [your project goal]"

### 4. Review and Iterate

- Review the generated festival structure
- Adjust requirements and task ordering as needed
- Experiment with parallel vs sequential task organization
- Assign specialized agents to specific tasks if desired

### 5. Execute

Once satisfied with the plan:
> "Get started working on the festival"

## Core Components

### FESTIVAL_SOFTWARE_PROJECT_MANAGEMENT.md
The complete methodology guide covering:
- Core principles (goal-first planning, flexible timeframes)
- Interface-first planning approach for parallel development
- Festival structure and directory organization  
- Planning process and best practices
- Sequential dependencies and parallel execution
- Quality verification requirements

### COMMON_INTERFACES_TEMPLATE.md
Template for defining system interfaces before implementation:
- API endpoints and data contracts
- Database schemas and relationships
- Component interfaces and props
- Service contracts and dependencies
- Event/message formats
- Review and finalization workflow

### TASK_TEMPLATE.md
Template for individual task files with:
- Clear objective and requirements
- Rules compliance sections
- Pre-task and completion checklists
- Technical notes and resources
- Quality gates and verification steps

### FESTIVAL_RULES_TEMPLATE.md
Template for project-specific standards:
- Engineering excellence principles
- Code quality requirements
- Testing and documentation standards
- Security and performance guidelines
- Compliance checklists for every task

## Key Process Flow

```
1. AI Agent Reviews Templates → Understands Methodology
                                ↓
2. Agent Creates Festival → Generates Three-Phase Structure
                           ↓
3. Phase 1: Plan → Requirements & Architecture Planning
                   ↓
4. Phase 2: Define Interfaces → Lock System Contracts
                               ↓
5. Developer Reviews → Iterates on Plan & Interfaces
                      ↓
6. Finalize Interfaces → Enable Parallel Development
                        ↓
7. Phase 3: Implement → Parallel Implementation Sequences
                       ↓
8. Built-in Verification → Testing, Review, Iteration
```

## Example Festival Structure

```
festivals/
└── festival_user_authentication/
    ├── FESTIVAL_OVERVIEW.md          # High-level goal and success criteria
    ├── COMMON_INTERFACES.md          # Master interface definitions
    ├── FESTIVAL_RULES.md             # Project-specific standards
    ├── 1_Plan/                       # Phase 1: Requirements & Planning
    │   ├── docs/                     # Planning documentation
    │   ├── 1_requirements_analysis/
    │   │   ├── 1_user_research.md
    │   │   ├── 1_security_requirements.md
    │   │   ├── 2_requirements_specification.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_iterate.md
    │   │   └── results/
    │   ├── 2_architecture_design/
    │   │   ├── 1_system_architecture.md
    │   │   ├── 1_technology_selection.md
    │   │   ├── 2_security_architecture.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_iterate.md
    │   │   └── results/
    │   └── completed/
    ├── 2_Define_Interfaces/          # Phase 2: Interface Definition
    │   ├── docs/                     # Interface specifications
    │   ├── 1_api_contracts/
    │   │   ├── 1_auth_api_spec.md
    │   │   ├── 1_user_api_spec.md
    │   │   ├── 2_error_handling_spec.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_iterate.md
    │   │   └── results/
    │   ├── 2_data_schemas/
    │   │   ├── 1_user_model_schema.md
    │   │   ├── 1_session_schema.md
    │   │   ├── 2_database_relationships.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_iterate.md
    │   │   └── results/
    │   └── completed/
    ├── 3_Implement/                  # Phase 3: Implementation
    │   ├── docs/                     # Implementation documentation
    │   ├── 1_backend_foundation/
    │   │   ├── 1_database_schema.md      # Parallel tasks (same number)
    │   │   ├── 1_api_endpoints.md        # Based on finalized interfaces
    │   │   ├── 1_auth_middleware.md      # Can work simultaneously
    │   │   ├── 2_testing_and_verify.md   # Must complete after 1_* tasks
    │   │   ├── 3_code_review.md          # Sequential verification
    │   │   ├── 4_review_results_iterate.md
    │   │   └── results/                  # Testing and review outputs
    │   ├── 2_frontend_integration/
    │   │   ├── 1_login_components.md
    │   │   ├── 1_auth_context.md
    │   │   ├── 2_error_handling.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_iterate.md
    │   │   └── results/
    │   ├── 3_deployment/
    │   │   ├── 1_security_review.md
    │   │   ├── 2_testing_and_verify.md
    │   │   ├── 3_code_review.md
    │   │   ├── 4_review_results_iterate.md
    │   │   └── results/
    │   └── completed/
    ├── completed/                    # Completed phases
    ├── canceled/                     # Abandoned work
    └── archived/                     # Deprioritized work
```

## Key Benefits

### For AI Agent Development
- **Step-Based Planning**: Think in development steps, not time estimates
- **Three-Phase Structure**: Logical progression from planning to interfaces to implementation
- **Interface-First Design**: Define all system contracts before implementation begins
- **Systematic Progress**: Each phase builds on previous work with clear deliverables
- **Quality Built-In**: Verification tasks prevent technical debt
- **Context Preservation**: Rules and documentation maintain consistency across context windows

### For Developers  
- **Clear Phase Separation**: Understand exactly what each phase accomplishes
- **Parallel Efficiency**: Interface definitions enable true parallel development across teams
- **Reduced Integration Issues**: Clear contracts minimize rework and conflicts
- **Logical Organization**: Easy to understand purpose of each directory and sequence
- **Flexible Scope**: Add requirements as discovered during development
- **Goal Achievement**: Success measured by concrete outcomes, not velocity metrics

### For Project Management
- **Minimal Overhead**: No daily standups or sprint ceremonies unless needed
- **Deep Understanding**: Requires thorough problem analysis upfront
- **Adaptive Execution**: Can pivot and iterate based on learnings
- **Scalable Complexity**: Works for simple bugs to complex product launches

## Advanced Features

### Specialized Agent Assignment
Document in task files which specialized agents should handle specific work:
```markdown
## Agent Assignment
This task should be handled by the database-specialist agent due to complex schema requirements.
```

### Task Ordering and Dependencies
- **Sequential**: `1_task.md`, `2_task.md`, `3_task.md` (must complete in order)
- **Parallel**: `1_task_a.md`, `1_task_b.md`, `1_task_c.md` (can work simultaneously)
- **Mixed**: `1_setup.md`, `2_parallel_a.md`, `2_parallel_b.md`, `3_integration.md`

### Quality Verification Pattern
Every sequence includes mandatory verification tasks:
- `N_testing_and_verify.md` - Test all implementation
- `N+1_code_review.md` - Review code quality  
- `N+2_review_results_iterate.md` - Decide whether to iterate or proceed

## Best Practices

1. **Start Simple**: Begin with FESTIVAL_OVERVIEW.md and basic three-phase structure
2. **Work Through Phases**: Complete 1_Plan → 2_Define_Interfaces → 3_Implement in order
3. **Define Interfaces First**: Lock all system contracts before any implementation
4. **Think in Steps**: Plan development steps, not time estimates
5. **Enable Parallel Work**: Use finalized interfaces to allow simultaneous development
6. **Build Systematically**: Complete each phase and sequence before starting the next  
7. **Verify Continuously**: Use built-in testing and review tasks
8. **Iterate Fearlessly**: Add new requirements and tasks as discovered
9. **Document Decisions**: Use FESTIVAL_RULES.md to capture important standards
10. **Organize Results**: Move completed work to `completed/`, abandoned work to `canceled/`

---

*The festival methodology leverages AI agents' strength in systematic execution while providing the structure needed for complex software development projects.*