# Cloud Architecture Overview

This diagram illustrates the monorepo structure and runtime flow between the React frontend and Express backend.

```mermaid
flowchart TD
  U[User]
  FE[React Frontend - packages/frontend]
  BE[Express API - packages/backend]
  DB[SQLite In-Memory]

  U --> FE
  FE --> BE
  BE --> DB

  subgraph Monorepo
    FE
    BE
  end
```

## Sequence: Create TODO

```mermaid
sequenceDiagram
  participant U as User
  participant FE as React Frontend
  participant BE as Express API
  participant DB as SQLite In-Memory

  U->>FE: Enter title, description, due date
  FE->>FE: Validate title, normalize due date
  FE->>BE: POST /api/tasks {title, description, due_date, priority}
  BE->>BE: Validate title and payload
  BE->>DB: Insert task
  DB-->>BE: New task record
  BE-->>FE: 201 Created + task JSON
  FE->>FE: Update list and reset form
  FE-->>U: Show task with chips
```
