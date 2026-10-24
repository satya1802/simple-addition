# Data Model

<!-- sdlc:auto:start entities -->
### tape_line

| Field | Type | PK | FK | Nullable |
|---|---|---|---|---|
| id | string (uuid) | True | — | False |
| value | decimal string | False | — | False |
| position | integer | False | — | False |

### tape

| Field | Type | PK | FK | Nullable |
|---|---|---|---|---|
| id | string | True | — | False |
| updated_at | timestamp | False | — | False |
<!-- sdlc:auto:end entities -->

<!-- sdlc:auto:start relationships -->
| Source | Target | Type |
|---|---|---|
| tape | tape_line | one-to-many |
<!-- sdlc:auto:end relationships -->

<!-- sdlc:auto:start er-diagram -->
```mermaid
erDiagram
  tape_line {
    string__uuid_ id PK
    decimal_string value
    integer position
  }
  tape {
    string id PK
    timestamp updated_at
  }
  tape ||--o{ tape_line : "one-to-many"
```
<!-- sdlc:auto:end er-diagram -->
