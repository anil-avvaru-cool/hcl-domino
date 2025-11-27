# Sequence Diagram — User Creates an Issue in HCL Domino

```mermaid
sequenceDiagram
    actor User
    participant Form as Issue Form
    participant Validation as Field Validation
    participant Agent as CreateIssueAgent
    participant NSF as Domino NSF

    User->>Form: Open Issue Form
    User->>Form: Enter Issue Details
    Form->>Validation: Trigger Validation
    Validation-->>Form: Validation Result (OK)
    Form->>Agent: Submit Issue Data
    Agent->>Agent: Create NotesDocument
    Agent->>NSF: doc.Save(True False)
    NSF-->>Agent: Save Successful
    Agent-->>Form: Return Issue ID / Status
    Form-->>User: Show Confirmation
```

## Steps Explained

1. **User** opens the form and enters data.
2. The **Form** performs client-side or server-side validation.
3. **CreateIssueAgent** receives validated data.
4. Agent constructs a **NotesDocument** and executes `doc.Save(True, False)`.
5. Document is written to the **NSF database**.
6. Confirmation is returned back to the user.
