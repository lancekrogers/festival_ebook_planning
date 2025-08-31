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

The festival directory structure is flexible and should be adapted to your
needs. Here's a typical example:

````text
festivals/
├── completed/                  # Optional: Successfully completed festivals
├── canceled/                   # Optional: Abandoned festivals
├── archived/                   # Optional: Deprioritized festivals (backlog)
└── festival_<id>/
    ├── FESTIVAL_OVERVIEW.md    # High-level goal, systems, and features overview
    ├── FESTIVAL_RULES.md       # Rules and principles to follow throughout the festival
    ├── specs/                  # Optional: Requirements, analysis, research, and planning notes
    ├── docs/                   # Optional: Documentation related to the festival's goal
    ├── systems/                # Optional: System-level documentation for complex festivals
    ├── features/               # Optional: Feature-level documentation for complex festivals
    ├── 1_<sequence_name>/      # First sequence of tasks
    │   ├── 1_task_a.md        # Tasks with same number can be worked in parallel
    │   ├── 1_task_b.md        # Parallel execution
    │   ├── 2_task_c.md        # Must complete after tasks 1_*
    │   ├── 3_testing_and_verify.md     # Testing verification task
    │   ├── 4_code_review.md            # Code review task
    │   ├── 5_review_results_update_tasks_iterate_if_needed.md  # Final review and iteration
    │   └── results/           # Testing results and code review documents
    ├── 2_<sequence_name>/      # Second sequence (depends on 1 completion)
    │   ├── 1_task_d.md
    │   ├── 2_task_e.md
    │   ├── 3_testing_and_verify.md
    │   ├── 4_code_review.md
    │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   └── results/
    ├── 3_<sequence_name>/      # Third sequence (depends on 2 completion)
    │   ├── 1_task_f.md
    │   ├── 2_testing_and_verify.md
    │   ├── 3_code_review.md
    │   ├── 4_review_results_update_tasks_iterate_if_needed.md
    │   └── results/
    ├── completed/              # Optional: Completed sequences moved here
    ├── canceled/               # Optional: Abandoned sequences
    └── archived/               # Optional: Deprioritized sequences (backlog)
```text

Note: This structure is a guideline, not a rigid requirement. Adapt it to fit your festival's specific needs.

## Planning Process

### 1. Define the Goal

Start with a clear, concrete objective. This should be outcome-focused, not activity-focused. Goals can range from simple (a single Jira ticket) to complex (a company-wide vision). Anyone with a goal and understanding of what needs to be done can be a festival planner.

### 2. Break Down into Systems and Features

- **Systems**: Major components or areas of work
- **Features**: Specific functionality within systems

### 3. Create FESTIVAL_OVERVIEW.md

Document:

- The high-level goal
- Systems breakdown (if applicable)
- Features breakdown (if applicable)
- Success criteria

### 4. Define FESTIVAL_RULES.md

Establish the principles and quality standards that all workers must follow throughout the festival. This ensures consistent quality and reminds workers of best practices at each step. Rules should cover:

- Engineering excellence principles
- Quality standards and gates
- Development process requirements
- Decision-making guidelines

### 5. Organize Sequential Work

- Create numbered directories (1_*, 2_*, etc.) for work that must happen in order
- Within each sequence, prepend task files with numbers to indicate execution order
- Tasks with the same number can be executed in parallel (e.g., 1_task_a.md, 1_task_b.md)
- Each task gets its own markdown file with clear requirements
- Every sequence must include these verification tasks:
  - `N_testing_and_verify.md` - Testing and verification (where N follows implementation tasks)
  - `N+1_code_review.md` - Code review
  - `N+2_review_results_update_tasks_iterate_if_needed.md` - Review results and iterate if needed
- Create a `results/` subdirectory in each sequence for testing results and code review documents

## Flexibility and Scaling

Festivals scale from simple to complex:

- **Simple Festival**: Just FESTIVAL_OVERVIEW.md and a few task files
- **Medium Festival**: Includes features/ directory with detailed breakdowns
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
- The work has natural dependencies
- You need flexibility in scope and timeline
- Team members can work independently on well-defined tasks
- You're working solo or collaboratively - festivals adapt to both modes

## Example Festival

```text
festivals/
└── festival_user_onboarding/
    ├── FESTIVAL_OVERVIEW.md
    ├── FESTIVAL_RULES.md
    ├── features/
    │   ├── email_verification.md
    │   └── kyc_integration.md
    ├── 1_backend_foundation/
    │   ├── 1_user_model_updates.md      # Can be done in parallel
    │   ├── 1_api_endpoints.md           # Can be done in parallel
    │   ├── 1_database_migrations.md     # Can be done in parallel
    │   ├── 2_testing_and_verify.md      # Testing verification
    │   ├── 3_code_review.md             # Code review
    │   ├── 4_review_results_update_tasks_iterate_if_needed.md
    │   └── results/                      # Test results and review docs
    ├── 2_frontend_implementation/
    │   ├── 1_registration_flow.md       # Can be done in parallel
    │   ├── 1_verification_ui.md         # Can be done in parallel
    │   ├── 2_error_handling.md          # Depends on 1_* tasks
    │   ├── 3_testing_and_verify.md
    │   ├── 4_code_review.md
    │   ├── 5_review_results_update_tasks_iterate_if_needed.md
    │   └── results/
    └── 3_integration_testing/
        ├── 1_e2e_tests.md
        ├── 1_performance_validation.md
        ├── 2_testing_and_verify.md
        ├── 3_code_review.md
        ├── 4_review_results_update_tasks_iterate_if_needed.md
        └── results/
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
