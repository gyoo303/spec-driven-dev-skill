# Requirements Template

## Document Structure

```markdown
# {Project Name} - Requirements Document

> **Version**: 1.0  
> **Last Updated**: {DATE}  
> **Status**: Draft | Review | Approved

---

## 1. Product Overview

### 1.1 Product Name
**{Name}**

### 1.2 Vision Statement
{One-line description of what the product does}

### 1.3 Background
{Why this product is being built}

### 1.4 Core Values
| Value | Description |
|-------|-------------|
| {Value1} | {Description} |

### 1.5 Target User
- **Primary**: {Who}
- **Usage Pattern**: {How they will use it}

### 1.6 Constraints
| ID | Constraint |
|----|------------|
| C1 | {Technical/business constraint} |

---

## 2. User Stories

### 2.1 Epic: {Epic Name} ({Epic Code})

#### US-{Code}-001: {Story Title}
**As a** {role}  
**I want to** {goal}  
**So that** {benefit}

**Acceptance Criteria (EARS):**
| ID | Type | Criterion |
|----|------|-----------|
| AC-001-1 | Ubiquitous | The system SHALL {requirement} |
| AC-001-2 | Event-Driven | WHEN {trigger}, THEN {response} |
| AC-001-3 | State-Driven | WHILE {state}, the system SHALL {behavior} |
| AC-001-4 | Optional | IF {condition}, THEN {behavior} |
| AC-001-5 | Unwanted | IF {condition}, THEN system SHALL NOT {behavior} |

---

## 3. Non-Functional Requirements

### 3.1 Performance
| ID | Requirement | Target |
|----|-------------|--------|
| NFR-PERF-001 | {Metric} | {Value} |

### 3.2 Security
| ID | Requirement | Implementation |
|----|-------------|----------------|
| NFR-SEC-001 | {Requirement} | {How} |

### 3.3 Reliability
| ID | Requirement | Target |
|----|-------------|--------|
| NFR-REL-001 | {Requirement} | {Value} |

### 3.4 Usability
| ID | Requirement | Implementation |
|----|-------------|----------------|
| NFR-USA-001 | {Requirement} | {How} |

### 3.5 Cost (if applicable)
| ID | Requirement | Target |
|----|-------------|--------|
| NFR-COST-001 | {Constraint} | {Value} |

---

## 4. Out of Scope (v1.0)

| Feature | Reason | Future Version |
|---------|--------|----------------|
| {Feature} | {Why excluded} | {vX} |

---

## 5. Glossary

| Term | Definition |
|------|------------|
| {Term} | {Definition} |

---

## 6. Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | {Date} | - | Initial draft |
```

## EARS Notation Details

### Ubiquitous Requirements
Always active, no precondition needed.

```
The system SHALL {action}
```

Examples:
- The system SHALL encrypt all passwords using bcrypt
- The system SHALL log all API requests

### Event-Driven Requirements
Triggered by specific events.

```
WHEN {trigger event}, THEN the system SHALL {response}
```

Examples:
- WHEN user submits form, THEN system SHALL validate all fields
- WHEN payment fails, THEN system SHALL notify user within 5 seconds

### State-Driven Requirements
Active only in specific states.

```
WHILE {system state}, the system SHALL {behavior}
```

Examples:
- WHILE in maintenance mode, the system SHALL reject new connections
- WHILE user is authenticated, the system SHALL display personalized content

### Optional Requirements
Conditional behavior based on feature flags or user attributes.

```
IF {condition}, THEN the system SHALL {behavior}
```

Examples:
- IF user has admin role, THEN system SHALL display admin panel
- IF premium subscription active, THEN system SHALL enable HD streaming

### Unwanted Behavior (Negative Requirements)
Explicitly state what should NOT happen.

```
IF {condition}, THEN the system SHALL NOT {behavior}
```

Examples:
- IF session expired, THEN system SHALL NOT process requests
- IF input contains SQL keywords, THEN system SHALL NOT execute query

## Best Practices

1. **One requirement per criterion** - Don't combine multiple requirements
2. **Testable** - Each criterion must be verifiable
3. **Unambiguous** - Avoid words like "should", "may", "might"
4. **Traceable** - Every criterion gets unique ID (AC-XXX-Y)
5. **Complete** - Cover happy path, edge cases, and error scenarios
