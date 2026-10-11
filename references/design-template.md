# Design Template

## Document Structure

```markdown
# {Project Name} - Technical Design Document

> **Version**: 1.0  
> **Last Updated**: {DATE}  
> **Status**: Draft | Review | Approved  
> **Related**: [requirements.md](./requirements.md)

---

## 1. System Architecture

### 1.1 Architecture Overview

{ASCII diagram or description of high-level architecture}

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│   Client    │────▶│   Server    │────▶│  Database   │
└─────────────┘     └─────────────┘     └─────────────┘
```

### 1.2 Technology Stack

| Layer | Technology | Rationale |
|-------|------------|-----------|
| Frontend | {Tech} | {Why chosen} |
| Backend | {Tech} | {Why chosen} |
| Database | {Tech} | {Why chosen} |
| Infrastructure | {Tech} | {Why chosen} |

### 1.3 Component Diagram

{Detailed component breakdown}

---

## 2. Data Model

### 2.1 Entity Relationship

{ER diagram or description}

### 2.2 Database Schema

#### Table: {table_name}

| Column | Type | Constraints | Description |
|--------|------|-------------|-------------|
| id | UUID | PK | Unique identifier |
| {column} | {type} | {constraints} | {description} |

**Indexes:**
- `{index_name}`: {columns} - {purpose}

### 2.3 Data Flow

```
{Step-by-step data flow description}
1. User submits request
2. API validates input
3. Service processes logic
4. Database persists data
5. Response returned
```

---

## 3. API Specification

### 3.1 Base Configuration

| Environment | Base URL |
|-------------|----------|
| Production | `https://api.{domain}/v1` |
| Development | `https://api-dev.{domain}/v1` |

### 3.2 Authentication

{Authentication mechanism description}

### 3.3 Endpoints

#### `{METHOD} {path}`

{Brief description}

**Request:**
```http
{METHOD} {path}
Authorization: Bearer {token}
Content-Type: application/json

{request body if applicable}
```

**Parameters:**
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| {param} | {type} | {Yes/No} | {description} |

**Response** `{status code}`:
```json
{
  "field": "value"
}
```

**Error Responses:**
| Status | Description |
|--------|-------------|
| 400 | Bad request |
| 401 | Unauthorized |
| 404 | Not found |
| 500 | Internal server error |

---

## 4. Component Design

### 4.1 {Component Name}

**Purpose**: {What it does}

**Responsibilities**:
- {Responsibility 1}
- {Responsibility 2}

**Dependencies**:
- {Dependency 1}
- {Dependency 2}

**Interface**:
```typescript
interface {ComponentName} {
  method(param: Type): ReturnType;
}
```

---

## 5. Security Design

### 5.1 Authentication Flow

```
{Authentication sequence diagram or description}
```

### 5.2 Authorization Model

| Role | Permissions |
|------|-------------|
| {role} | {permissions} |

### 5.3 Data Protection

| Data Type | Protection Method |
|-----------|-------------------|
| {type} | {method} |

---

## 6. Infrastructure

### 6.1 Deployment Architecture

{Infrastructure diagram}

### 6.2 Environment Configuration

| Variable | Description | Example |
|----------|-------------|---------|
| {VAR_NAME} | {purpose} | {example} |

### 6.3 CI/CD Pipeline

```yaml
# Pipeline stages
1. Build
2. Test
3. Deploy to staging
4. Deploy to production
```

---

## 7. Monitoring & Observability

### 7.1 Metrics

| Metric | Source | Alert Threshold |
|--------|--------|-----------------|
| {metric} | {source} | {threshold} |

### 7.2 Logging

| Log Type | Format | Retention |
|----------|--------|-----------|
| {type} | {format} | {period} |

---

## 8. Revision History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | {Date} | Initial design |
```

## Design Patterns

### API Design Guidelines

1. **RESTful conventions**
   - Use nouns for resources: `/articles`, `/users`
   - Use HTTP methods: GET (read), POST (create), PATCH (update), DELETE (remove)
   - Use plural nouns: `/articles` not `/article`

2. **Response format**
   ```json
   {
     "data": { },
     "meta": { "page": 1, "total": 100 },
     "error": null
   }
   ```

3. **Error format**
   ```json
   {
     "error": {
       "code": "VALIDATION_ERROR",
       "message": "Invalid input",
       "details": [{ "field": "email", "message": "Invalid format" }]
     }
   }
   ```

### Architecture Patterns

1. **Layered Architecture**
   ```
   Presentation → Application → Domain → Infrastructure
   ```

2. **Serverless Pattern**
   ```
   API Gateway → Lambda → DynamoDB
                      → S3
                      → External APIs
   ```

3. **Event-Driven Pattern**
   ```
   Producer → Message Queue → Consumer → Database
   ```

### Database Design Guidelines

1. **Naming conventions**
   - Tables: plural, snake_case (`user_profiles`)
   - Columns: singular, snake_case (`created_at`)
   - Indexes: `idx_{table}_{columns}`

2. **Common columns**
   - `id`: Primary key (UUID or auto-increment)
   - `created_at`: Timestamp
   - `updated_at`: Timestamp
   - `deleted_at`: Soft delete timestamp (nullable)
