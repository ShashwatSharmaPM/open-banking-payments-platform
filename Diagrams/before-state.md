# Before state: banks facing PSD2 with no infrastructure

> PSD2 regulation mandates open banking APIs. Most banks, especially small and mid-sized, have no internal capability to build compliant infrastructure from scratch. Deadline approaching.

```mermaid
graph TD
    REG[PSD2 regulation approaching<br/>Europe, ~2018] --> MANDATE[Banks must open payment<br/>infrastructure to third parties]

    MANDATE --> LARGE[Large banks]
    MANDATE --> MID[Mid-size banks]
    MANDATE --> SMALL[Small banks]

    LARGE --> CAP1[Have internal dev teams<br/>but timeline is tight]
    MID --> CAP2[Limited internal capability<br/>cannot build from scratch]
    SMALL --> CAP3[No internal capability<br/>fully dependent on vendors]

    classDef reg fill:#d94f4f,color:#fff,stroke:#b33a3a
    classDef mandate fill:#c68a2e,color:#fff,stroke:#a06e1e
    classDef bank fill:#4a8bc2,color:#fff,stroke:#3670a0
    classDef cap fill:#e8a0a0,color:#2a0a0a,stroke:#c27070

    class REG reg
    class MANDATE mandate
    class LARGE,MID,SMALL bank
    class CAP1,CAP2,CAP3 cap
```

### What PSD2 compliance required

```mermaid
graph TD
    PSD2[PSD2 compliance requirements] --> AIS[Account information<br/>services API]
    PSD2 --> PIS[Payment initiation<br/>services API]
    PSD2 --> SCA[Strong customer<br/>authentication]
    PSD2 --> TPP[Third-party provider<br/>registration and access]

    AIS --> INFRA[Requires API infrastructure<br/>banks don't have]
    PIS --> INFRA
    SCA --> INFRA
    TPP --> INFRA

    INFRA --> BUILD[Build in-house?<br/>12-18+ months, massive cost]
    INFRA --> BUY[Buy a turnkey solution?<br/>Market barely exists yet]

    classDef req fill:#c68a2e,color:#fff,stroke:#a06e1e
    classDef component fill:#4a8bc2,color:#fff,stroke:#3670a0
    classDef infra fill:#d94f4f,color:#fff,stroke:#b33a3a
    classDef option fill:#e8a0a0,color:#2a0a0a,stroke:#c27070

    class PSD2 req
    class AIS,PIS,SCA,TPP component
    class INFRA infra
    class BUILD,BUY option
```

### The market gap

```mermaid
graph TD
    BANKS[Banks need PSD2 compliance fast] --> LOOK{Available solutions?}
    LOOK -->|Large consultancies| BESPOKE[Bespoke builds<br/>expensive, slow, not reusable]
    LOOK -->|Fintech startups| IMMATURE[Early stage<br/>no enterprise track record]
    LOOK -->|In-house| SLOW[12-18+ months<br/>most banks can't make the deadline]

    BESPOKE --> GAP[No turnkey platform exists<br/>that works across bank sizes]
    IMMATURE --> GAP
    SLOW --> GAP

    classDef need fill:#4a8bc2,color:#fff,stroke:#3670a0
    classDef option fill:#c68a2e,color:#fff,stroke:#a06e1e
    classDef problem fill:#e8a0a0,color:#2a0a0a,stroke:#c27070
    classDef gap fill:#d94f4f,color:#fff,stroke:#b33a3a

    class BANKS need
    class LOOK option
    class BESPOKE,IMMATURE,SLOW problem
    class GAP gap
```

## Pain points summary

| Problem | Impact |
|---------|--------|
| **Regulatory deadline with no infrastructure** | Banks must comply with PSD2 but most lack the API infrastructure to do so. Non-compliance means being locked out of the payments ecosystem. |
| **No turnkey solutions in the market** | Large consultancies offered bespoke builds (expensive, slow). Fintechs were too immature for enterprise banking. No one had a platform approach. |
| **Each bank has different legacy systems** | Core banking systems vary wildly. Any solution needs to integrate with each bank's existing infrastructure, not replace it. |
| **Compliance is the floor, not the ceiling** | Banks focused only on "how do we comply?" but the real opportunity was in what open APIs could enable after compliance: fintech partnerships, new payment experiences, data analytics. |
| **Consulting firm DNA vs. product thinking** | The parent organization's instinct was to build bespoke solutions for each client. A scalable platform approach required fighting that instinct. |
