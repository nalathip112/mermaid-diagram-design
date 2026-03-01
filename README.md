# Login Flow

```mermaid
sequenceDiagram
User->>API: Login
API->>DB: Verify user
DB-->>API: Result
API-->>User: Token
```
