# Prioritization: Open Banking Payments Platform

> How I prioritized a 0-to-1 product build against a regulatory deadline, while managing the tension between "ship fast for compliance" and "build right for a platform." Inside a consulting firm that wanted to build bespoke for every client.

---

## The Core Tension

This project had a constraint most products don't: a **regulatory deadline**. PSD2 compliance wasn't optional. Banks that didn't comply by the deadline would be locked out of the European payments ecosystem.

That meant every prioritization decision lived inside a three-way tension:

1. **Speed to compliance** (what the first two banking prospects needed immediately)
2. **Platform scalability** (what would make client #3 through #7 possible without rebuilding from scratch)
3. **Revenue beyond compliance** (what would turn a compliance tool into a revenue-generating platform after the deadline passed)

The consulting firm I was in naturally leaned toward #1 (deliver fast for this client, worry about the next one later). My job was to hold the line on #2 and plant the seeds for #3, while never missing the compliance deadline.

---

## Framework: Regulatory-Gated Phasing

Standard RICE doesn't work well when your primary constraint is a legal deadline, not user demand. I used a phased model where the regulatory timeline was the immovable constraint, and everything else was sequenced around it.

### Phase 1: Compliance MVP (Year 1)
**Constraint**: Regulatory deadline. Must ship the minimum viable set of PSD2-compliant capabilities.

| Capability | Regulatory Requirement? | Client Demand | Effort | Decision |
|-----------|------------------------|---------------|--------|----------|
| Account information services API | Yes (mandatory) | Both prospects need it | High | **Build first** -- no compliance without it |
| Payment initiation services API | Yes (mandatory) | Both prospects need it | High | **Build first** -- no compliance without it |
| Strong customer authentication | Yes (mandatory) | Security teams insist | Medium | **Build first** -- regulatory non-negotiable |
| Third-party provider registration | Yes (mandatory) | Required for API access | Medium | **Build first** -- regulatory non-negotiable |
| Multi-bank configuration engine | No (our architecture choice) | Only matters at scale | High | **Build now anyway** -- this is what makes it a platform, not a bespoke build. Without it, client #2 is a rebuild. |
| Transaction analytics dashboard | No | Both prospects asked for it | Medium | **Defer to Phase 2** -- nice to have, not compliance-critical |
| Fintech partnership portal | No | Not requested yet | High | **Defer to Phase 3** -- future revenue stream, not urgent |

The hardest call in Phase 1 was the **multi-bank configuration engine**. Neither prospect needed it (each bank only cares about its own deployment). The consulting team pushed back: "Why are we spending effort on something the client didn't ask for?" Because without it, every new bank would be a ground-up build. The configuration engine is what made this a product instead of a series of consulting engagements.

### Phase 2: Scale and Optimize (Year 2)
**Constraint**: Onboard clients 3-7 without rebuilding. Prove that the platform approach works.

| Capability | Why Now | Decision |
|-----------|---------|----------|
| Multi-jurisdiction support | New clients in different European countries with different regulatory nuances | **Build** -- blocking new client onboarding |
| Infrastructure right-sizing | Small banks over-provisioned, large banks under-provisioned | **Build** -- 64% cost reduction opportunity confirmed by performance data |
| Transaction analytics dashboard | Clients now asking for visibility beyond compliance | **Build** -- differentiator in competitive deals |
| Enhanced SCA flows | National regulators interpreting SCA differently | **Build** -- compliance variations emerging post-launch |

### Phase 3: Beyond Compliance (Years 3-5)
**Constraint**: The compliance deadline has passed. Now the question is: what else can this API infrastructure do?

| Capability | Revenue Potential | Decision |
|-----------|-------------------|----------|
| Fintech partnership portal | High -- banks can onboard third-party providers via our APIs | **Build** -- new revenue stream |
| Payment experience enhancements | Medium -- differentiation for banks competing on UX | **Build** -- drives retention |
| Data analytics for banks | Medium -- banks want insights from their open banking data | **Build** -- stickiness play |
| Additional payment methods | High -- extending beyond core PSD2 scope | **Build** -- market expansion |

This is where the 50+ revenue streams and 150+ features came from. The 5-year roadmap was structured around the principle that compliance builds the infrastructure, and the infrastructure creates the surface area for revenue streams that have nothing to do with compliance.

---

## The Bigger Prioritization: Platform vs. Bespoke

This was the defining prioritization battle of the entire project, and it played out on every feature decision.

### The consulting firm's instinct

Every time a new banking client had a unique requirement, the instinct from the delivery team was: "Let's just build it custom for them." This is rational in a consulting model. You bill hours. Custom work = more hours = more revenue. The client is happy because they got exactly what they asked for.

### Why I pushed back

Custom builds for each bank would mean:
- Client #7 costs the same effort as client #1
- Improvements for one client don't benefit others
- Maintenance multiplies with every deployment
- No recurring product revenue, only project-based consulting fees

### How I won the argument

I didn't win it once. I won it repeatedly, on every feature decision, by maintaining a simple rule:

**"If a requirement is truly unique to one bank, we build it as a configuration parameter. If it's common across banks, we build it into the core platform. If it's a one-off request that doesn't fit either model, we say no."**

This gave the delivery team a clear decision framework instead of a philosophical debate every time. Over time, the pattern proved itself: each new client onboarded faster than the previous one, and the per-client delivery cost dropped steadily.

---

## Prioritization Under Uncertainty: The PoC-to-Product Decision

The single biggest prioritization decision on this project wasn't a feature. It was: **who should own the product build?**

After the PoC landed two serious prospects, the organization had to decide between:

| Option | Pros | Cons |
|--------|------|------|
| Hire a dedicated PM | Fresh perspective, PM credentials | 3-6 month ramp on regulation, market, and client relationships. Deadline doesn't wait. |
| Transition me from GTM to PM | Deep regulatory knowledge, existing client relationships, knows what was promised | No formal PM experience. Risk of GTM mindset carrying over. |

I made the case for option 2 by framing it as a prioritization of speed-to-market over organizational tidiness: "We have a regulatory deadline. I've gone through the compliance document multiple times. I know the two prospects personally. A new PM would spend their first quarter learning what I already know. We can't afford that quarter."

This transition from GTM strategist to PM was the foundation of my product career.

---

## What I'd Do Differently

1. **Invest in the configuration engine even more aggressively.** I fought for it in Phase 1, but it was still somewhat under-scoped. By client #4, we were adding configuration parameters we should have anticipated. A more thorough upfront analysis of jurisdiction-specific variations would have saved rework.

2. **Build the infrastructure optimization model from day one.** We only discovered the over-provisioning / under-provisioning problem after several clients were live and we had performance data. A lightweight cost model built during Phase 1 would have surfaced the 64% savings opportunity earlier.

3. **Formalize the "platform vs. bespoke" rule earlier.** The configuration-parameter-vs-core-platform-vs-no framework I described above emerged organically through repeated debates. If I'd documented it as an explicit decision rule from the start, it would have reduced the friction on every subsequent feature decision.

---

*All company names, client names, and partner names have been anonymized. Metrics and decision frameworks are accurate as applied.*
