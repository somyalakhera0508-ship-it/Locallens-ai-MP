
# LocalLens AI — Architecture Diagram

This diagram represents the proposed system workflow.
The application is not yet implemented.

```mermaid
flowchart TD
    A["Tourist enters preferences<br/>Interests, budget, time, group size"]
    B["Experience Dataset<br/>Local experiences across Madhya Pradesh"]
    C["Verification Checks<br/>Status and last-checked date"]
    D["Constraint Engine<br/>Budget, time, capacity, accessibility"]
    E["AI-Assisted Matching<br/>Match interests and explain results"]
    F["Suitable Recommendations<br/>Show available status and limitations"]
    G["Alternative Search"]
    H["Transparent Message<br/>No suitable option could be confirmed"]

    A --> D
    B --> C
    C --> D
    D -->|Eligible experiences| E
    D -->|No eligible experiences| G
    E --> F
    G -->|Suitable alternative found| F
    G -->|No suitable alternative| H
```

## How it works

1. The tourist enters their preferences.
2. The system checks experience records and verification status.
3. The constraint engine filters unsuitable experiences.
4. AI helps explain relevant recommendations.
5. If no suitable option is found, the system searches for alternatives or clearly communicates the limitation.

## Important Design Principle

AI must not invent availability or treat unverified listings as confirmed. Essential constraints are checked separately from AI-generated explanations.
