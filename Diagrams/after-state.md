# After state: turnkey PSD2 platform scaled to 7 global clients

> One platform, configurable per bank, $17M ARR. Compliance achieved in short turnaround times. 50+ revenue streams beyond the initial compliance use case.

```mermaid
graph TD
    TPP[Third-party providers<br/>fintechs, payment apps] --> PLAT

    subgraph PLAT[" PSD2 compliance platform "]
        direction TB
        AIS[Account information<br/>services API]
        PIS[Payment initiation<br/>services API]
        SCA[Strong customer<br/>authentication layer]
        CONFIG[Multi-bank configuration<br/>engine]
    end

    PLAT --> B1[Bank's core<br/>infrastructure]
        
    classDef tpp fill:#7b6bb5,color:#fff,stroke:#5f519a
    classDef plat fill:#2d9d78,color:#fff,stroke:#1d7a5c
    classDef component fill:#a3dcc8,color:#0a2a1e,stroke:#5dbfa0
    classDef bank fill:#4a8bc2,color:#fff,stroke:#3670a0
    classDef core fill:#777,color:#fff,stroke:#555

    class TPP tpp
    class PLAT plat
    class AIS,PIS,SCA,CONFIG component
    class B1,B2,B3 bank
    class CORE1,CORE2,CORE3 core
```

### Platform vs. bespoke: the architecture decision

```mermaid
graph TD
    REQ[New bank client signs up] --> FORK{Approach?}

    FORK -->|Consulting instinct| BESPOKE[Build custom solution<br/>from scratch for this bank]
    FORK -->|Platform approach| CONFIGURE[Configure existing platform<br/>to this bank's infrastructure]

    BESPOKE --> SLOW[3-6 months per client<br/>not reusable, high cost]
    CONFIGURE --> FAST[Weeks to go live<br/>reusable, scalable]

    FAST --> SCALE[7 clients on different instances of one platform.<br/>Shared improvements benefit all]

    classDef start fill:#4a8bc2,color:#fff,stroke:#3670a0
    classDef fork fill:#c68a2e,color:#fff,stroke:#a06e1e
    classDef bad fill:#d94f4f,color:#fff,stroke:#b33a3a
    classDef good fill:#2d9d78,color:#fff,stroke:#1d7a5c
    classDef outcome fill:#a3dcc8,color:#0a2a1e,stroke:#5dbfa0

    class REQ start
    class FORK fork
    class BESPOKE,SLOW bad
    class CONFIGURE,FAST good
    class SCALE outcome
```

### 5-year roadmap: compliance as floor, revenue as ceiling

```mermaid
graph TD
    Y1[Year 1: Core compliance<br/>AIS, PIS, SCA] --> Y2[Year 2: Scale to 7 clients<br/>multi-jurisdiction support, $12M ARR]
    Y2 --> Y3[Year 3: Beyond compliance<br/>fintech partnerships, analytics]
    Y3 --> Y4[Year 4-5: 50+ revenue streams<br/>150+ features, $17M ARR]

    Y1 --> OPT[Infrastructure optimization<br/>64% cost reduction]

    classDef early fill:#c68a2e,color:#fff,stroke:#a06e1e
    classDef mid fill:#4a8bc2,color:#fff,stroke:#3670a0
    classDef mature fill:#2d9d78,color:#fff,stroke:#1d7a5c
    classDef ops fill:#a3dcc8,color:#0a2a1e,stroke:#5dbfa0

    class Y1 early
    class Y2 mid
    class Y3,Y4 mature
    class OPT ops
```

### My role transition

```mermaid
graph TD
    GTM[Joined as go-to-market<br/>strategist] --> DEEP[Went deep into PSD2<br/>regulation document]
    DEEP --> POC[Built PoC with<br/>engineering team]
    POC --> SELL[Took PoC to two<br/>large banking prospects]
    SELL --> INTEREST[Prospects showed<br/>serious interest]
    INTEREST --> CASE[Made the case:<br/>I know the regulation,<br/>the market, and the customers]
    CASE --> PM[Transitioned to<br/>product manager]
    PM --> LAUNCH[Delivered platform<br/>from 0 to 1]

    classDef gtm fill:#c68a2e,color:#fff,stroke:#a06e1e
    classDef build fill:#4a8bc2,color:#fff,stroke:#3670a0
    classDef transition fill:#7b6bb5,color:#fff,stroke:#5f519a
    classDef pm fill:#2d9d78,color:#fff,stroke:#1d7a5c

    class GTM,DEEP,POC gtm
    class SELL,INTEREST build
    class CASE transition
    class PM,LAUNCH pm
```

## Before vs. after comparison

| Dimension | Before | After |
|-----------|--------|-------|
| **PSD2 compliance** | Banks had no infrastructure. Non-compliance meant being locked out of payments ecosystem. | Turnkey platform achieves compliance in short turnaround time. |
| **Market offering** | No platform-based solution existed. Only bespoke consulting builds or immature fintech offerings. | One configurable platform serving 7 global clients across European jurisdictions. |
| **Time to compliance** | 12-18+ months for in-house builds | Weeks to months via platform configuration |
| **Revenue** | Zero (pre-product) | $17M ARR |
| **Revenue streams** | None | 50+ revenue streams across the 5-year roadmap |
| **Features** | PoC only | 150+ features shipped |
| **Operational costs** | Over-provisioned for small banks, under-provisioned for large ones | 64% reduction through infrastructure recalibration |
| **Client base** | 2 PoC prospects | 7 global banking clients |
| **Approach** | Consulting firm instinct: bespoke per client | Platform approach: one core, configurable per bank |
| **My role** | Go-to-market strategist | Product manager owning the full product lifecycle |

## Key architectural decisions

**Why platform, not bespoke:**
The parent organization was a consulting firm. Their DNA was to build custom for every client. I pushed for a platform approach because: (a) bespoke builds aren't reusable, so client #7 costs the same as client #1, (b) improvements for one client benefit all clients on the platform, and (c) a platform generates recurring product revenue, not one-time consulting fees. This was a constant negotiation internally.

**Why multi-jurisdiction configuration, not separate instances:**
European banks operate under different national regulators even within PSD2. Rather than spinning up a separate platform instance for each jurisdiction, we built a configuration engine that handled jurisdiction-specific requirements (authentication flows, data residency, reporting formats) as parameters, not code changes.

**Why infrastructure optimization mattered:**
With 7 clients of varying sizes, the same infrastructure allocation didn't make sense. Small banks were over-provisioned (paying for capacity they didn't use), large banks were occasionally under-provisioned (hitting performance limits during peak transaction volumes). Recalibrating based on actual performance metrics cut operational costs by 64% without any SLA impact.
