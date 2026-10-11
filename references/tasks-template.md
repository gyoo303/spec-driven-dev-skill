# Tasks Template

## Document Structure

```markdown
# {Project Name} - Implementation Tasks

> **Version**: 1.0  
> **Last Updated**: {DATE}  
> **Status**: Planning | In Progress | Complete  
> **Related**: [requirements.md](./requirements.md), [design.md](./design.md)

---

## Overview

{Brief description of task organization}

**Legend**:
- 🔴 Not Started
- 🟡 In Progress
- 🟢 Completed
- 🔵 Blocked

---

## Phase 1: {Phase Name}

**Duration**: {Timeframe}  
**Goal**: {Phase objective}

### 1.1 {Task Group}

| ID | Task | Status | Req | Est |
|----|------|--------|-----|-----|
| T-1.1.1 | {Task description} | 🔴 | {AC-XXX} | {Xh} |
| T-1.1.2 | {Task description} | 🔴 | {AC-XXX} | {Xh} |

<details>
<summary>📋 T-1.1.1: {Task title}</summary>

{Detailed implementation notes, code snippets, or specifications}

```typescript
// Example code or configuration
```

</details>

---

## Phase 2: {Phase Name}

{Repeat structure...}

---

## Summary

### Task Statistics

| Phase | Tasks | Estimated Hours |
|-------|-------|-----------------|
| Phase 1 | {N} | {Xh} |
| Phase 2 | {N} | {Xh} |
| **Total** | **{N}** | **{Xh}** |

### Critical Path

```
T-1.1.1 → T-1.1.2 → T-2.1.1 → T-2.1.2 → ...
```

### Dependencies

- **Blocked by T-X.X.X**: {Dependent tasks}
- **Blocked by T-Y.Y.Y**: {Dependent tasks}

---

## Revision History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | {Date} | Initial task breakdown |
```

## Task Breakdown Guidelines

### Task Granularity

**Good task size**: 1-4 hours of work
- Too small: "Add semicolon to line 42"
- Too large: "Build entire frontend"
- Just right: "Implement user login form with validation"

### Task Naming

Use action verbs:
- ✅ "Create", "Implement", "Configure", "Setup", "Add", "Fix", "Update"
- ❌ "User authentication", "Database", "Frontend stuff"

Examples:
- "Create DynamoDB table for articles"
- "Implement JWT token validation middleware"
- "Configure CloudWatch alarms for Lambda errors"

### Linking to Requirements

Every implementation task should link to:
- **Acceptance Criteria** (AC-XXX-Y) for feature tasks
- **NFR-XXX** for non-functional tasks
- No link needed for pure setup/infrastructure tasks

### Estimating Time

| Task Type | Typical Range |
|-----------|---------------|
| Boilerplate setup | 30min - 1h |
| Simple CRUD endpoint | 1-2h |
| Complex business logic | 2-4h |
| Integration with external API | 2-4h |
| UI component (simple) | 1-2h |
| UI component (complex) | 3-4h |
| Testing | 50% of implementation time |
| Documentation | 1-2h per major feature |

### Phase Organization

Typical phases for web projects:

1. **Foundation** (Week 1-2)
   - Project setup
   - Infrastructure provisioning
   - Basic authentication

2. **Core Backend** (Week 2-4)
   - Data models
   - Business logic
   - API endpoints

3. **Frontend** (Week 4-6)
   - UI components
   - State management
   - API integration

4. **Integration & Polish** (Week 6-7)
   - End-to-end testing
   - Error handling
   - Performance optimization

5. **Deployment & Launch** (Week 7-8)
   - CI/CD pipeline
   - Monitoring setup
   - Documentation

### Dependency Mapping

Use arrows to show dependencies:

```
T-1.1.1 (Setup DB)
    ↓
T-1.1.2 (Create tables) ──────┐
    ↓                         │
T-2.1.1 (CRUD Lambda) ←───────┘
    ↓
T-3.1.1 (API endpoints)
    ↓
T-4.1.1 (Frontend integration)
```

### Status Updates

Update status as work progresses:

| Status | When to Use |
|--------|-------------|
| 🔴 Not Started | Task not yet begun |
| 🟡 In Progress | Actively working on task |
| 🟢 Completed | Task done and verified |
| 🔵 Blocked | Cannot proceed due to dependency |

### Details Section

Use `<details>` for implementation notes:

```markdown
<details>
<summary>📋 T-1.2.3: Configure DynamoDB table</summary>

**Table Schema:**
```typescript
{
  TableName: 'articles',
  KeySchema: [
    { AttributeName: 'articleId', KeyType: 'HASH' }
  ],
  // ...
}
```

**Notes:**
- Enable PITR for backup
- Use on-demand billing for unpredictable workload

</details>
```

This keeps the main task list scannable while preserving detailed information.
