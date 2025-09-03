---
id: FESTIVAL_SOFTWARE_PROJECT_MANAGEMENT
aliases: []
tags: []
---

# Festival Planning Methodology

## Overview

Festival methodology is a goal-oriented, flexible planning approach that
prioritizes concrete objectives over process overhead. Unlike traditional agile
methodologies, festivals focus on achieving specific goals rather than adhering
to rigid ceremonies and timeboxes.

## Core Principles

1. **Goal-First Planning**: Every festival starts with a clear, high-level
   objective
2. **Concrete Requirements**: Goals are broken down into tangible, achievable
   requirements
3. **Flexible Timeframes**: No artificial sprints or deadlines - festivals
   complete when the goal is achieved
4. **Single Initial Planner**: One person with deep understanding plans the
   festival initially, acting as a benevolent dictator to ensure coherent vision
   and avoid design-by-committee
5. **Adaptive Execution**: New requirements can be added as discovered during
   development
6. **Sequential Dependencies**: Work is organized in numbered sequences that
   must complete in order
7. **Parallel Work Within Sequences**: Tasks within each sequence can be
   distributed across the team
8. **Mandatory Verification**: Every sequence includes testing, code review, and
   results iteration tasks
9. **Numbered Task Execution**: Tasks and sequences use number prefixes to
   indicate execution order

## Festival Structure

The festival directory structure is organized into three logical phases that provide clear purpose and workflow progression. Here's the recommended structure:

````text
festivals/
├── completed/                  # Optional: Successfully completed festivals
├── canceled/                   # Optional: Abandoned festivals
├── archived/                   # Optional: Deprioritized festivals (backlog)
└── festival_<id>/
    ├── FESTIVAL_OVERVIEW.md    # High-level goal, systems, and features overview
    ├── COMMON_INTERFACES.md    # Master interface definitions (updated throughout phases)
    ├── FESTIVAL_RULES.md       # Rules and principles to follow throughout the festival
    ├── 1_Plan/                 # Phase 1: Requirements and Planning
    │   ├── docs/              # Planning documentation and research
    │   ├── 1_requirements_gathering/
    │   │   ├── 1_stakeholder_interviews.md
    │   │   ├── 1_user_research.md
    │   │   ├── 2_requirements_analysis.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/
    │   ├── 2_architecture_planning/
    │   │   ├── 1_system_design.md
    │   │   ├── 1_technology_selection.md
    │   │   ├── 2_feasibility_study.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/
    │   └── completed/         # Completed planning sequences
    ├── 2_Define_Interfaces/    # Phase 2: Interface Definition and Finalization
    │   ├── docs/              # Interface documentation and specifications
    │   ├── 1_identify_interfaces/
    │   │   ├── 1_api_inventory.md
    │   │   ├── 1_data_flow_analysis.md
    │   │   ├── 2_interface_mapping.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/
    │   ├── 2_define_contracts/
    │   │   ├── 1_api_specifications.md
    │   │   ├── 1_data_schemas.md
    │   │   ├── 1_component_interfaces.md
    │   │   ├── 2_validation_rules.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/
    │   ├── 3_finalize_interfaces/
    │   │   ├── 1_stakeholder_review.md
    │   │   ├── 2_interface_approval.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/
    │   └── completed/         # Completed interface definition sequences
    ├── 3_Implement/            # Phase 3: Implementation
    │   ├── docs/              # Implementation documentation
    │   ├── 1_backend_foundation/
    │   │   ├── 1_database_setup.md       # Parallel tasks (same number)
    │   │   ├── 1_api_endpoints.md        # Can work simultaneously
    │   │   ├── 1_auth_middleware.md      # Based on finalized interfaces
    │   │   ├── 2_integration_layer.md    # Must complete after 1_* tasks
    │   │   ├── 3_testing_and_verify.md   # Testing verification task
    │   │   ├── 4_code_review.md          # Code review task
    │   │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/                  # Testing results and code review documents
    │   ├── 2_frontend_implementation/
    │   │   ├── 1_component_library.md
    │   │   ├── 1_user_interface.md
    │   │   ├── 2_state_management.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/
    │   ├── 3_integration_testing/
    │   │   ├── 1_end_to_end_tests.md
    │   │   ├── 2_performance_testing.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/
    │   └── completed/         # Completed implementation sequences
    ├── completed/              # Optional: Completed phases moved here
    ├── canceled/               # Optional: Abandoned phases or sequences
    └── archived/               # Optional: Deprioritized work (backlog)
```text

Note: This structure is a guideline, not a rigid requirement. Adapt it to fit your festival's specific needs.

## Planning Process

### 1. Define the Goal

Start with a clear, concrete objective. This should be outcome-focused, not activity-focused. Goals can range from simple (a single Jira ticket) to complex (a company-wide vision). Anyone with a goal and understanding of what needs to be done can be a festival planner.

### 2. Break Down into Systems and Features

- **Systems**: Major components or areas of work
- **Features**: Specific functionality within systems

### 3. Define Common Interfaces

**This is the most critical step for enabling parallel development and reducing iterations.**

Before any implementation begins:

1. **Identify All System Interfaces**: APIs, database schemas, service contracts, component props, function signatures, event structures, etc.
2. **Document Interface Specifications**: Create detailed interface definitions with:
   - Input/output parameters and types
   - Expected behavior and constraints
   - Error handling specifications
   - Example usage scenarios
3. **Review and Iterate**: Have stakeholders and technical leads review all interfaces
4. **Finalize Interfaces**: Mark interfaces as finalized before beginning implementation sequences

**Benefits of Interface-First Approach:**
- Enables true parallel development across teams and agents
- Reduces integration issues and rework
- Provides clear contracts for all system boundaries
- Allows accurate festival planning with minimal iterations

### 4. Create FESTIVAL_OVERVIEW.md

Document:

- The high-level goal
- Systems breakdown (if applicable)
- Features breakdown (if applicable)
- Success criteria

### 5. Define FESTIVAL_RULES.md

Establish the principles and quality standards that all workers must follow throughout the festival. This ensures consistent quality and reminds workers of best practices at each step. Rules should cover:

- Engineering excellence principles
- Quality standards and gates
- Development process requirements
- Decision-making guidelines

### 6. Organize Work into Three Phases

**Festival work is organized into three logical phases that must be completed in order:**

#### Phase 1: Plan (1_Plan/)
**Purpose**: Requirements gathering, analysis, and architectural planning

- Requirements gathering and stakeholder interviews
- User research and needs analysis  
- System architecture and design planning
- Technology selection and feasibility studies
- Risk assessment and mitigation planning

#### Phase 2: Define Interfaces (2_Define_Interfaces/)
**Purpose**: Interface definition and finalization - **most critical for parallel development**

- Identify all system interfaces and integration points
- Define API contracts, data schemas, and component interfaces
- Create detailed specifications with examples
- Stakeholder review and approval process
- Interface finalization and lock-down

#### Phase 3: Implement (3_Implement/)
**Purpose**: All implementation work based on finalized interfaces

- Backend development with parallel teams
- Frontend implementation using defined interfaces
- Integration and testing
- Deployment and verification

**Within Each Phase:**
- Create numbered sequence directories (1_*, 2_*, etc.) for work that must happen in order
- Within each sequence, prepend task files with numbers to indicate execution order
- Tasks with the same number can be executed in parallel (e.g., 1_task_a.md, 1_task_b.md)
- Each task gets its own markdown file with clear requirements
- Every sequence must include these verification tasks:
  - `N_testing_and_verify.md` - Testing and verification (where N follows implementation tasks)
  - `N+1_code_review.md` - Code review
  - `N+2_review_results_update_tasks_iterate_if_needed.md` - Review results and iterate if needed
- Create a `results/` subdirectory in each sequence for testing results and code review documents
- Include a `docs/` directory in each phase for phase-specific documentation

## Three-Phase Benefits

The three-phase structure provides significant advantages:

**Clear Separation of Concerns**: Each phase has a distinct purpose and deliverable
- Phase 1 (Plan): Complete understanding of requirements and architecture
- Phase 2 (Define Interfaces): Finalized contracts enabling parallel development
- Phase 3 (Implement): Systematic implementation based on solid foundations

**Reduced Risk**: Issues are caught early in planning and interface definition phases
**Parallel Development**: Once interfaces are locked, teams can work simultaneously
**Better Communication**: Clear phase boundaries help stakeholders understand progress
**Quality Built-In**: Each phase includes verification and iteration cycles

## Flexibility and Scaling

Festivals scale from simple to complex:

- **Simple Festival**: Just FESTIVAL_OVERVIEW.md, COMMON_INTERFACES.md, and implementation tasks in 3_Implement/
- **Medium Festival**: All three phases with multiple sequences in each phase
- **Complex Festival**: Full systems/ and features/ directories with extensive documentation

The optional directories serve specific purposes:

- **specs/**: Store requirements documents, analysis notes, research findings, and planning artifacts
- **docs/**: House documentation directly related to the festival's goal
- **completed/**: Move successfully finished festivals or sequences here to keep the active workspace clean
- **canceled/**: Store abandoned festivals or sequences that were planned but won't be executed
- **archived/**: Like a backlog - deprioritized work that may be valuable later but isn't needed for the current goal

These directories can be included at any complexity level as needed and are only created when necessary.

## Key Advantages

1. **No Process Overhead**: No daily standups, sprint planning, or retrospectives unless actually needed
2. **Clear Dependencies**: Sequential directories make dependencies obvious
3. **Flexible Scope**: Add requirements as you discover them
4. **Goal Achievement**: Success is measured by goal completion, not velocity metrics
5. **Deep Understanding**: Requires and encourages thorough problem understanding upfront

## When to Use Festival Methodology

Festival methodology works best when:

- You have a clear goal to achieve (from a simple bug fix to a major product launch)
- You want to minimize process overhead
- The work has natural dependencies and multiple system interfaces
- You need flexibility in scope and timeline
- Team members can work independently on well-defined tasks with clear interface contracts
- You're working solo or collaboratively - festivals adapt to both modes
- You can define system interfaces upfront to enable parallel development

## Example Festival

```text
festivals/
└── festival_user_onboarding/
    ├── FESTIVAL_OVERVIEW.md
    ├── COMMON_INTERFACES.md
    ├── FESTIVAL_RULES.md
    ├── 1_Plan/
    │   ├── docs/                         # Planning documentation
    │   ├── 1_requirements_analysis/
    │   │   ├── 1_user_journey_mapping.md
    │   │   ├── 1_stakeholder_interviews.md
    │   │   ├── 2_requirements_specification.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/
    │   ├── 2_system_design/
    │   │   ├── 1_architecture_planning.md
    │   │   ├── 1_technology_evaluation.md
    │   │   ├── 2_security_considerations.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/
    │   └── completed/
    ├── 2_Define_Interfaces/
    │   ├── docs/                         # Interface specifications
    │   ├── 1_api_contracts/
    │   │   ├── 1_user_registration_api.md
    │   │   ├── 1_email_verification_api.md
    │   │   ├── 1_kyc_integration_api.md
    │   │   ├── 2_error_response_standards.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/
    │   ├── 2_data_schemas/
    │   │   ├── 1_user_model_schema.md
    │   │   ├── 1_verification_schema.md
    │   │   ├── 2_database_relationships.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/
    │   ├── 3_component_interfaces/
    │   │   ├── 1_registration_components.md
    │   │   ├── 1_verification_ui_props.md
    │   │   ├── 2_state_management_contracts.md
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/
    │   └── completed/
    ├── 3_Implement/
    │   ├── docs/                         # Implementation documentation
    │   ├── 1_backend_foundation/
    │   │   ├── 1_user_model_updates.md   # Can be done in parallel
    │   │   ├── 1_api_endpoints.md        # Based on finalized interfaces
    │   │   ├── 1_database_migrations.md  # Can be done in parallel
    │   │   ├── 2_testing_and_verify.md   # Testing verification
    │   │   ├── 3_code_review.md          # Code review
    │   │   ├── 4_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/                  # Test results and review docs
    │   ├── 2_frontend_implementation/
    │   │   ├── 1_registration_flow.md    # Can be done in parallel
    │   │   ├── 1_verification_ui.md      # Based on component interfaces
    │   │   ├── 2_error_handling.md       # Depends on 1_* tasks
    │   │   ├── 3_testing_and_verify.md
    │   │   ├── 4_code_review.md
    │   │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/
    │   ├── 3_integration_testing/
    │   │   ├── 1_e2e_tests.md
    │   │   ├── 1_performance_validation.md
    │   │   ├── 2_testing_and_verify.md
    │   │   ├── 3_code_review.md
    │   │   ├── 4_review_results_update_tasks_iterate_if_needed.md
    │   │   └── results/
    │   └── completed/
    ├── completed/                        # Completed phases
    ├── canceled/                         # Abandoned work
    └── archived/                         # Deprioritized work
````

## Festival Rules

Festival Rules are a critical component that ensures quality and consistency
throughout the festival. Every festival should include a FESTIVAL_RULES.md file
that workers reference before and during task execution.

### Purpose of Festival Rules

- **Maintain Quality Standards**: Establish clear quality gates and acceptance
  criteria
- **Ensure Consistency**: All workers follow the same principles and practices
- **Reduce Rework**: Prevent common mistakes by providing clear guidelines
  upfront
- **Promote Excellence**: Embed staff-level engineering principles into every
  task

### Common Rules for Software Festivals

1. **Engineering Excellence**
   - Prefer refactoring existing code over rewriting from scratch
   - Follow established patterns and conventions in the codebase
   - Apply SOLID principles and avoid over-engineering (YAGNI)
   - Keep functions under 50 lines, files under 500 lines

2. **Quality Standards**
   - Write tests for all new functionality
   - Maintain or improve code coverage
   - Run linters and type checkers before marking tasks complete
   - Document architectural decisions and breaking changes

3. **Development Process**
   - Create small, focused pull requests (one logical change)
   - Update documentation alongside code changes
   - Consider security implications in all changes
   - Maintain backward compatibility unless explicitly approved

### Task Integration

Each task should include a "Rules Compliance" section that:

- References relevant rules from FESTIVAL_RULES.md
- Includes a pre-task checklist
- Provides a completion checklist for verification

## Best Practices

1. **Keep Goals Concrete**: Vague goals lead to scope creep
2. **Document Clearly**: Each task file should be self-contained
3. **Sequence Thoughtfully**: Consider dependencies when creating sequences
4. **Stay Flexible**: Add new sequences or tasks as needed
5. **Complete Before Proceeding**: Finish each sequence before starting the next
6. **Organize Finished Work**: Move completed sequences to completed/, canceled
   work to canceled/, and deprioritized work to archived/
7. **Follow Festival Rules**: Reference and adhere to FESTIVAL_RULES.md
   throughout execution
