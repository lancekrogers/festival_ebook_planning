---
id: COMMON_INTERFACES_TEMPLATE
aliases:
  - COMMON INTERFACES TEMPLATE
  - COMMON-INTERFACES-TEMPLATE
tags: []
created: '2025-09-03'
modified: '2025-09-03'
---

# Common Interfaces: [Festival Name]

## Purpose

This document defines all system interfaces that must be established and finalized during **Phase 2: Define Interfaces** before **Phase 3: Implementation** begins. Defining interfaces first is the most critical step for enabling parallel development and minimizing iterations throughout the festival.

**Location in Festival Structure**: This file lives at the root of the festival directory and is updated throughout the interface definition phase based on work completed in `2_Define_Interfaces/`.

## Interface Definition Status

**Current Status**: [DRAFT | UNDER_REVIEW | FINALIZED]

**Review Deadline**: [Date when interfaces must be finalized]

**Stakeholder Sign-off Required**: [List of roles/people who must approve]

---

## API Interfaces

### [Service/Component Name] API

**Status**: [DRAFT | UNDER_REVIEW | FINALIZED]

**Base URL**: `[base-url]`

#### Authentication
```
[Authentication method, headers, tokens, etc.]
```

#### Endpoints

##### [HTTP Method] [Endpoint Path]
**Purpose**: [What this endpoint does]

**Request Format**:
```json
{
  "field1": "string - description",
  "field2": "number - description", 
  "field3": {
    "nested": "object structure"
  }
}
```

**Response Format**:
```json
{
  "success": true,
  "data": {
    "result_field": "string - description"
  },
  "errors": []
}
```

**Error Responses**:
- `400 Bad Request`: Invalid input parameters
- `401 Unauthorized`: Authentication required
- `404 Not Found`: Resource not found
- `500 Internal Error`: Server error

**Example Usage**:
```bash
curl -X POST [base-url]/[endpoint] \
  -H "Content-Type: application/json" \
  -d '{"example": "data"}'
```

---

## Database Schemas

### [Table/Collection Name]

**Status**: [DRAFT | UNDER_REVIEW | FINALIZED]

**Schema Definition**:
```sql
CREATE TABLE [table_name] (
  id SERIAL PRIMARY KEY,
  field1 VARCHAR(255) NOT NULL,
  field2 INTEGER DEFAULT 0,
  field3 TIMESTAMP DEFAULT NOW(),
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);
```

**Indexes**:
- `idx_field1` on `field1` for lookups
- `idx_field2_field3` on `(field2, field3)` for compound queries

**Relationships**:
- Foreign key to `[other_table]` via `[field_name]`
- One-to-many with `[related_table]`

---

## Component Interfaces

### [Component Name]

**Status**: [DRAFT | UNDER_REVIEW | FINALIZED]

**Props Interface**:
```typescript
interface [ComponentName]Props {
  required_prop: string;
  optional_prop?: number;
  callback_prop: (data: DataType) => void;
  children?: React.ReactNode;
}
```

**State Interface**:
```typescript
interface [ComponentName]State {
  loading: boolean;
  data: DataType | null;
  error: string | null;
}
```

**Events Emitted**:
- `onDataLoaded(data: DataType)`: When data is successfully loaded
- `onError(error: Error)`: When an error occurs

---

## Service Interfaces

### [Service Name]

**Status**: [DRAFT | UNDER_REVIEW | FINALIZED]

**Interface Definition**:
```typescript
interface [ServiceName] {
  method1(param1: Type1, param2: Type2): Promise<ReturnType>;
  method2(config: ConfigType): Observable<DataType>;
  method3(): boolean;
}
```

**Configuration**:
```typescript
interface [ServiceName]Config {
  setting1: string;
  setting2: number;
  optional_setting?: boolean;
}
```

**Dependencies**:
- Requires: `[OtherService]`, `[ThirdService]`
- Provides: `[ExposedInterface]`

---

## Event/Message Interfaces

### [Event System Name]

**Status**: [DRAFT | UNDER_REVIEW | FINALIZED]

#### [Event Name] Event
```typescript
interface [EventName]Event {
  type: '[EVENT_NAME]';
  timestamp: string;
  payload: {
    field1: string;
    field2: number;
  };
  metadata?: {
    source: string;
    correlation_id: string;
  };
}
```

**When Triggered**: [Description of trigger conditions]
**Expected Handlers**: [List of systems that should handle this event]

---

## File Format Interfaces

### [File Type] Format

**Status**: [DRAFT | UNDER_REVIEW | FINALIZED]

**Structure**:
```json
{
  "version": "1.0",
  "format": "[format_name]",
  "data": {
    "field1": "value",
    "field2": 123
  }
}
```

**Validation Rules**:
- `version` must be semantic version string
- `data` object is required
- Maximum file size: [limit]

---

## Integration Interfaces

### [External System] Integration

**Status**: [DRAFT | UNDER_REVIEW | FINALIZED]

**Connection Details**:
- Protocol: [HTTP/HTTPS/WebSocket/etc.]
- Authentication: [method]
- Rate Limits: [limits]

**Data Exchange Format**:
```json
{
  "request": {
    "action": "string",
    "parameters": {}
  },
  "response": {
    "status": "success|error",
    "data": {}
  }
}
```

---

## Interface Review Process

### Review Checklist

Before marking any interface as FINALIZED:

- [ ] All required fields are clearly defined
- [ ] Data types are explicit and consistent
- [ ] Error handling patterns are documented
- [ ] Authentication/authorization is specified
- [ ] Performance implications are considered
- [ ] Security implications are reviewed
- [ ] Backward compatibility is addressed
- [ ] Example usage is provided
- [ ] Integration points are validated

### Stakeholder Approval

**Technical Lead**: ☐ Approved ☐ Changes Requested  
**Product Owner**: ☐ Approved ☐ Changes Requested  
**Security Review**: ☐ Approved ☐ Changes Requested  
**Performance Review**: ☐ Approved ☐ Changes Requested  

### Finalization Criteria

Interfaces are considered FINALIZED when:

1. All stakeholders have approved
2. Review checklist is complete
3. No breaking changes are anticipated
4. Implementation teams have confirmed feasibility
5. Integration points have been validated

**Finalization Date**: [Date when all interfaces were locked]

**Change Control**: Once finalized, interface changes require:
- [ ] Impact assessment
- [ ] Stakeholder re-approval  
- [ ] Migration plan (if breaking)
- [ ] Festival planner approval

---

## Implementation Guidelines

### For Development Teams

1. **Wait for Finalization**: Do not begin **Phase 3: Implementation** until interfaces show FINALIZED status
2. **Implement to Contract**: Build exactly to interface specifications
3. **Mock Early**: Use interface definitions to create mocks for parallel development
4. **Validate Continuously**: Ensure implementation matches interface contracts
5. **Report Discrepancies**: Immediately escalate if interfaces prove inadequate during implementation

### For Testing Teams

1. **Contract Testing**: Create tests that validate interface compliance
2. **Mock Services**: Build mocks based on interface definitions
3. **Integration Testing**: Verify actual implementations match interface contracts
4. **Error Scenario Testing**: Test all defined error conditions

---

## Notes

### Interface Design Principles

- **Consistency**: Use consistent patterns across all interfaces
- **Clarity**: Make interfaces self-documenting with clear field names
- **Completeness**: Include all necessary fields and error conditions
- **Future-Proof**: Design for extensibility without breaking changes
- **Security-First**: Consider security implications of all data flows

### Common Pitfalls to Avoid

- Defining interfaces too late in the process
- Making interfaces too complex or trying to solve every future case
- Not getting proper stakeholder review before finalization
- Allowing implementation to begin before interfaces are locked
- Failing to document error conditions and edge cases
- Not considering performance implications of interface design

### Change Management

Once interfaces are finalized, changes should be rare and carefully managed. If changes become necessary:

1. Assess impact on all dependent systems
2. Create migration plan for breaking changes  
3. Get approval from festival planner and affected teams
4. Update this document with new version and change log
5. Communicate changes to all stakeholders

---

## Phase Integration

This document integrates with the three-phase festival structure:

**Phase 1 (1_Plan/)**: Interface requirements are identified during planning
**Phase 2 (2_Define_Interfaces/)**: Detailed interface work happens here - this document is updated based on sequences in this phase
**Phase 3 (3_Implement/)**: Implementation proceeds based on finalized interfaces in this document

**Remember**: The goal is to enable parallel development by providing clear contracts that all teams can build against. Taking time to get interfaces right in Phase 2 saves significant time and iterations in Phase 3.