# Fill-in Residential Customer Details
``` mermaid
sequenceDiagram
User->>Frontend: Input data
Frontend->>Baeckend API: Check Customer Type [(name)Yes=Res ,No=Non]
Baeckend API->>DB: Query Residential Data
DB-->>Baeckend API: Return Customer Type
Baeckend API-->>Frontend:  Return Customer Type

alt Residential
  Frontend->>Baeckend API: GetResidentialDetails(ID card/ Passport)
  Baeckend API->>DB: Query Residential Data
  DB-->>Baeckend API: Return Customer Details
  Baeckend API-->>Frontend: Return Customer Details
else Non-Residential
  Frontend->>Baeckend API: GetNonResidentialDetails
  Baeckend API->>DB: Query NonResidential 
  DB-->>Baeckend API: Return Customer Details
  Baeckend API-->>Frontend: Return Customer Details
end
Frontend-->>User: Display Customer Details
```
