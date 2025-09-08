# Festival Methodology - AI Agent Build System

Festival methodology is a goal-oriented project management system designed specifically for AI agent development workflows. It introduces **phases** as a NEW organizational layer above the existing sequences and tasks structure, providing a three-level hierarchy: **Phases → Sequences → Tasks**.

## Quick Start Guide

### 1. Set Up Your Project Workspace

Create a festival directory in your project workspace:

```
your_project_workspace/
├── your_repos/           # Your existing repositories
└── festivals/            # Festival planning directory
```

### 2. Copy the Template Files

Copy these 6 files from `build_system/templates/` to your `festivals/` directory:

- `FESTIVAL_SOFTWARE_PROJECT_MANAGEMENT.md` - Core methodology documentation
- `COMMON_INTERFACES_TEMPLATE.md` - Template for defining system interfaces
- `TASK_TEMPLATE.md` - Template for individual tasks
- `TASK_EXAMPLES.md` - Concrete examples of well-written tasks
- `FESTIVAL_RULES_TEMPLATE.md` - Template for project standards
- `FESTIVAL_OVERVIEW_TEMPLATE.md` - Template for project overview and goals

### 3. Create Your Festival

Tell your AI agent:
> "Please fully review the 6 template files to understand the festival methodology, then create a festival for [your project goal]"

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

- System architecture overview with component tables
- Communication protocol selection (REST/gRPC/GraphQL/Message Queues/Custom)
- Data architecture and consistency requirements
- Interface contracts using tables and diagrams
- Security and performance specifications
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
2. Agent Creates Festival → Generates Phase→Sequence→Task Structure
                           ↓
3. Phase 001: PLAN → Requirements & Architecture Planning
                     ↓
4. Phase 002: DEFINE_INTERFACES → Lock System Contracts
                                  ↓
5. Developer Reviews → Iterates on Plan & Interfaces
                      ↓
6. Finalize Interfaces → Enable Parallel Development
                        ↓
7. Phase 003: IMPLEMENT → Parallel Implementation with Automated Testing
                         ↓
8. Phase 004: REVIEW_AND_UAT → User Acceptance & Stakeholder Validation
                              ↓
9. Built-in Verification → Testing, Review, Iteration at Each Level
```

## Example Festival Structure

**Three-Level Hierarchy: PHASES → SEQUENCES → TASKS**

```
festivals/
└── festival_user_authentication/
    ├── FESTIVAL_OVERVIEW.md          # High-level goal and success criteria
    ├── COMMON_INTERFACES.md          # Master interface definitions
    ├── FESTIVAL_RULES.md             # Project-specific standards
    ├── 001_PLAN/                     # PHASE: Requirements & Planning (3-digit)
    │   ├── docs/                     # Phase-specific documentation
    │   ├── 01_requirements_analysis/ # SEQUENCE: Requirements work (2-digit)
    │   │   ├── 01_user_research.md        # TASK (2-digit)
    │   │   ├── 01_security_requirements.md # TASK (parallel)
    │   │   ├── 02_requirements_spec.md    # TASK (after 01_ tasks)
    │   │   ├── 03_testing_and_verify.md   # TASK
    │   │   ├── 04_code_review.md          # TASK
    │   │   ├── 05_review_results_iterate.md # TASK
    │   │   └── results/                   # Sequence results
    │   ├── 02_architecture_design/   # SEQUENCE: Architecture work
    │   │   ├── 01_system_architecture.md  # TASK
    │   │   ├── 01_technology_selection.md # TASK (parallel)
    │   │   ├── 02_security_architecture.md # TASK (after 01_ tasks)
    │   │   ├── 03_testing_and_verify.md   # TASK
    │   │   ├── 04_code_review.md          # TASK
    │   │   ├── 05_review_results_iterate.md # TASK
    │   │   └── results/                   # Sequence results
    │   └── completed/                # Completed sequences in this phase
    ├── 002_DEFINE_INTERFACES/        # PHASE: Interface Definition
    │   ├── docs/                     # Phase-specific documentation
    │   ├── 01_api_contracts/         # SEQUENCE: API contract definition
    │   │   ├── 01_auth_api_spec.md        # TASK
    │   │   ├── 01_user_api_spec.md        # TASK (parallel)
    │   │   ├── 02_error_handling_spec.md  # TASK (after 01_ tasks)
    │   │   ├── 03_testing_and_verify.md   # TASK
    │   │   ├── 04_code_review.md          # TASK
    │   │   ├── 05_review_results_iterate.md # TASK
    │   │   └── results/                   # Sequence results
    │   ├── 02_data_schemas/          # SEQUENCE: Data schema definition
    │   │   ├── 01_user_model_schema.md    # TASK
    │   │   ├── 01_session_schema.md       # TASK (parallel)
    │   │   ├── 02_database_relationships.md # TASK (after 01_ tasks)
    │   │   ├── 03_testing_and_verify.md   # TASK
    │   │   ├── 04_code_review.md          # TASK
    │   │   ├── 05_review_results_iterate.md # TASK
    │   │   └── results/                   # Sequence results
    │   └── completed/                # Completed sequences in this phase
    ├── 003_IMPLEMENT/                # PHASE: Implementation
    │   ├── docs/                     # Phase-specific documentation
    │   ├── 01_backend_foundation/    # SEQUENCE: Backend implementation
    │   │   ├── 01_database_schema.md      # TASK (parallel tasks same number)
    │   │   ├── 01_api_endpoints.md        # TASK (based on finalized interfaces)
    │   │   ├── 01_auth_middleware.md      # TASK (can work simultaneously)
    │   │   ├── 02_automated_testing.md    # TASK (after 01_ tasks)
    │   │   ├── 03_code_review.md          # TASK
    │   │   ├── 04_review_results_iterate.md # TASK
    │   │   └── results/                   # Sequence results
    │   ├── 02_frontend_integration/  # SEQUENCE: Frontend implementation
    │   │   ├── 01_login_components.md     # TASK
    │   │   ├── 01_auth_context.md         # TASK (parallel)
    │   │   ├── 02_error_handling.md       # TASK (after 01_ tasks)
    │   │   ├── 03_automated_testing.md    # TASK
    │   │   ├── 04_code_review.md          # TASK
    │   │   ├── 05_review_results_iterate.md # TASK
    │   │   └── results/                   # Sequence results
    │   └── completed/                # Completed sequences in this phase
    ├── 004_REVIEW_AND_UAT/           # PHASE: User Review & UAT
    │   ├── docs/                     # Phase-specific documentation
    │   ├── 01_user_acceptance_testing/ # SEQUENCE: User acceptance testing
    │   │   ├── 01_uat_planning.md         # TASK
    │   │   ├── 01_test_scenarios.md       # TASK (parallel)
    │   │   ├── 02_user_testing_execution.md # TASK (after 01_ tasks)
    │   │   ├── 03_feedback_analysis.md    # TASK (after 02_ task)
    │   │   ├── 04_testing_and_verify.md   # TASK
    │   │   ├── 05_code_review.md          # TASK
    │   │   ├── 06_review_results_iterate.md # TASK
    │   │   └── results/                   # Sequence results
    │   ├── 02_stakeholder_review/    # SEQUENCE: Stakeholder validation
    │   │   ├── 01_business_validation.md  # TASK
    │   │   ├── 01_stakeholder_demos.md    # TASK (parallel)
    │   │   ├── 02_requirements_sign_off.md # TASK (after 01_ tasks)
    │   │   ├── 03_testing_and_verify.md   # TASK
    │   │   ├── 04_code_review.md          # TASK
    │   │   ├── 05_review_results_iterate.md # TASK
    │   │   └── results/                   # Sequence results
    │   └── completed/                # Completed sequences in this phase
    ├── completed/                    # Completed phases
    ├── canceled/                     # Abandoned work
    └── archived/                     # Deprioritized work
```

## Key Benefits

### For AI Agent Development

- **Step-Based Planning**: Think in development steps, not time estimates
- **Three-Level Hierarchy**: New phases layer organizes existing sequences and tasks
- **Interface-First Design**: Define all system contracts before implementation begins
- **Systematic Progress**: Each level builds on previous work with clear deliverables
- **Quality Built-In**: Verification tasks prevent technical debt at every level
- **Context Preservation**: Rules and documentation maintain consistency across context windows
- **Scalable Numbering**: 3-digit phases, 2-digit sequences/tasks support hundreds of items

### For Developers  

- **Clear Phase Separation**: Understand exactly what each phase accomplishes
- **Parallel Efficiency**: Interface definitions enable true parallel development across teams
- **Reduced Integration Issues**: Clear contracts minimize rework and conflicts
- **Logical Organization**: Easy to understand purpose of each directory and sequence
- **User Validation**: Dedicated phase for user acceptance testing separate from automated testing
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

1. **Start Simple**: Begin with FESTIVAL_OVERVIEW.md and basic four-phase structure
2. **Work Through Phases**: Complete 001_PLAN → 002_DEFINE_INTERFACES → 003_IMPLEMENT → 004_REVIEW_AND_UAT in order
3. **Define Interfaces First**: Lock all system contracts before any implementation
4. **Think in Steps**: Plan development steps, not time estimates
5. **Enable Parallel Work**: Use finalized interfaces to allow simultaneous development
6. **Separate Testing Types**: Automated testing in implement phase, user testing in review & UAT phase
7. **Build Systematically**: Complete each phase and sequence before starting the next  
8. **Verify Continuously**: Use built-in testing and review tasks at each phase
9. **Iterate Fearlessly**: Add new requirements and tasks as discovered, repeat phases as needed
10. **Document Decisions**: Use FESTIVAL_RULES.md to capture important standards
11. **Organize Results**: Move completed work to `completed/`, abandoned work to `canceled/`
12. **Use Proper Numbering**: 3-digit phases (001_, 002_), 2-digit sequences/tasks (01_, 02_) for scalability

---

*The festival methodology leverages AI agents' strength in systematic execution while providing the structure needed for complex software development projects.*

