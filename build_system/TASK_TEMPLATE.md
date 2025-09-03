---
id: TASK_TEMPLATE
aliases:
  - TASK TEMPLATE
  - TASK-TEMPLATE
tags: []
created: '2025-08-26'
modified: '2025-08-26'
---

# Task: [N_Task_Name]

> **Task Number**: N (where N indicates execution order) **Parallel Execution**:
> [Yes/No - if yes, list other tasks with same number] **Dependencies**: [List
> any tasks that must complete before this one]

## Objective

[Clear description of what needs to be accomplished]

## Rules Compliance

Before starting this task, review FESTIVAL_RULES.md, particularly:

- [Relevant section 1]
- [Relevant section 2]
- [Relevant section 3]

## Context

[Why this task is needed, dependencies, background information]

## Requirements

- [ ] [Specific requirement 1]
- [ ] [Specific requirement 2]
- [ ] [Specific requirement 3]

## Deliverables

- [What will be produced]
- [Expected outputs]
- [Documentation required]

## Definition of Done

- [ ] [Completion criteria 1]
- [ ] [Quality criteria 1]
- [ ] [Acceptance criteria 1]

## Pre-Task Checklist

- [ ] Read FESTIVAL_RULES.md completely
- [ ] Understand task requirements
- [ ] Review existing code/content and patterns
- [ ] Identify dependencies based on task numbering
- [ ] Verify all lower-numbered tasks in sequence are complete
- [ ] Plan approach

## Technical Notes

[Any technical considerations, constraints, or important information]

## Resources

- [Helpful links or documentation]
- [Related files or examples]
- [Reference materials]

## Estimated Effort

[Rough estimate in ideal hours/days]

## Completion Checklist

- [ ] All requirements met
- [ ] Tests pass (if applicable)
- [ ] Documentation updated
- [ ] Quality standards met
- [ ] Security considered (if applicable)
- [ ] Performance assessed (if applicable)
- [ ] Rules compliance verified
- [ ] Self-review completed

## Notes

[Any additional information, assumptions, or considerations]

## For Verification Tasks (testing_and_verify, code_review)

### Testing Results Location

- Place all testing results in: `./results/testing_results_[timestamp].md`

### Code Review Results Location

- Place all review documents in: `./results/code_review_[timestamp].md`

### Iteration Tasks

- When creating `review_results_update_tasks_iterate_if_needed.md`:
  - Review all documents in `./results/` directory
  - Create new numbered tasks if iteration is needed
  - Document decision to proceed or iterate
