# Stakeholder Map: Open Banking Payments Platform

> This project sat at the intersection of regulation, banking, technology, and consulting economics. Every stakeholder had a different definition of success, and the product had to satisfy all of them while shipping against a non-negotiable regulatory deadline.

---

## Why This Project Had Unusual Stakeholder Complexity

Most product builds have a clear customer and a clear internal team. This one had layered complexity on both sides:

- **The buyer was not the user.** Bank compliance officers decided to purchase. Bank CTOs evaluated the technology. Bank operations teams used the platform daily. Each had different criteria for success.
- **The parent organization was a consulting firm, not a product company.** Internal incentives were structured around billable hours and project delivery, not recurring product revenue. Building a platform went against the organizational grain.
- **Regulators were a silent stakeholder.** PSD2 wasn't negotiable. The regulation dictated the minimum feature set, the authentication standards, and the deadline. I couldn't deprioritize a regulatory requirement no matter how low its RICE score.
- **Third-party providers (fintechs) were the eventual consumers of the APIs**, but they weren't at the table during the initial build. The platform had to serve an audience that hadn't weighed in on its design.

---

## Stakeholder Map

### Banking Clients (7 across European jurisdictions)

**What they cared about**: Compliance by the deadline. Minimal disruption to existing operations. Not being the bank that fails the regulatory audit.

**Their concern with this project**: "Can you actually deliver before the deadline? We've been burned by technology vendors before. And our core banking system is 20 years old. Can your platform even talk to it?"

**How I managed them**:
- The PoC was the trust builder. Taking it to two large prospects with a working demonstration of account information services and payment initiation was what moved the conversation from "interesting concept" to "let's sign."
- For each new bank, the first milestone was integration with their existing core banking system. Every bank had different legacy infrastructure, so this was always the highest-risk phase. I prioritized integration interface flexibility in the platform design specifically to handle this variation without custom code.
- Managed the tension between what banks asked for (bespoke everything) and what the platform could sustainably deliver (configurable parameters). Framed it as: "You get the same compliance outcome, faster, because you're leveraging a proven platform. The configuration handles your specific requirements."
- Regular compliance checkpoint meetings to demonstrate progress against the regulatory timeline. No surprises.

**What they needed from me**: Confidence that the deadline would be met, proof that the platform worked with their legacy systems, and assurance that their jurisdiction-specific requirements were handled.

**Alignment mechanism**: PoC demonstrations, integration milestone reviews, compliance checkpoint meetings, and direct relationships I'd built during the GTM phase.

---

### Compliance Officers (at Banking Clients)

**What they cared about**: Passing the regulatory audit. Documentation. Traceability. Nothing ambiguous.

**Their concern with this project**: "Does this platform meet every requirement in the PSD2 directive? Can we prove it to the regulator? What happens if the regulator interprets a requirement differently than you've implemented it?"

**How I managed them**:
- I'd gone through the PSD2 compliance documentation multiple times during the GTM phase. This domain expertise was the single biggest trust-builder with compliance officers. I could speak their language, reference specific articles in the directive, and explain exactly how each platform capability mapped to a regulatory requirement.
- Created compliance mapping documentation: every PSD2 requirement mapped to a specific platform feature, with technical details about how it was implemented. This document became the basis for the bank's regulatory audit submission.
- When national regulators interpreted requirements differently (which happened post-launch with SCA flows), I prioritized those variations immediately. Compliance is non-negotiable. A feature can slip a sprint. A compliance gap cannot.

**What they needed from me**: Proof that every requirement was covered, documentation they could show regulators, and fast response when regulatory interpretations changed.

**Alignment mechanism**: Compliance mapping documents, direct access for regulatory questions, priority handling of compliance-related changes.

---

### Bank CTOs / Technology Teams

**What they cared about**: Technical quality, integration with existing systems, security, not creating a dependency on a vendor they couldn't control.

**Their concern with this project**: "Our core banking system is a monolith from 2002. How does your platform integrate with it without breaking everything? And if we adopt your platform, what happens when you raise prices or discontinue support?"

**How I managed them**:
- Designed the integration interfaces to adapt to each bank's existing infrastructure rather than requiring the bank to change. The platform consumed whatever APIs or data formats the bank's core system already exposed.
- The multi-bank configuration engine addressed the vendor lock-in concern: the platform's PSD2 APIs followed open standards, meaning a bank could theoretically replace us with another PSD2 provider without re-engineering their third-party integrations.
- Shared architecture documentation openly. CTOs need to understand what they're buying. Black-box platforms don't win CTO trust.

**What they needed from me**: Technical credibility, integration flexibility, and architectural transparency.

**Alignment mechanism**: Architecture review sessions, integration milestone reviews, technical documentation.

---

### Internal Leadership (Consulting Firm)

**What they cared about**: Revenue, client satisfaction, utilization rates, and the reputation of the consulting practice.

**Their concern with this project**: Dual and contradictory. On one hand: "This could be a great new revenue stream." On the other: "Are we a product company now? What happens to our consulting revenue if banks buy a platform instead of hiring us for bespoke builds?"

**How I managed them**:
- Framed the platform as a consulting accelerator, not a consulting replacement. "The platform handles the commodity compliance work. Our consultants handle the high-value integration, customization, and advisory work on top of it. We can serve more banks with the same team because the platform does the heavy lifting."
- Showed the math: bespoke builds for 7 banks would require 7x the delivery team. The platform approach served 7 banks with the same team, generating $17M in ARR with significantly lower delivery cost per client.
- The 64% operational cost reduction was a number leadership cared deeply about. It proved that the platform approach wasn't just theoretically better, it was measurably cheaper.
- Made the GTM-to-PM transition case in terms leadership understood: "I know the regulation, the market, and the clients. A new PM hire would need 3-6 months to ramp up. The deadline doesn't wait."

**What they needed from me**: Revenue growth, proof that the platform model worked financially, and assurance that the consulting practice wasn't being cannibalized.

**Alignment mechanism**: Quarterly business reviews, revenue reporting, cost comparison (platform vs. bespoke), and regular updates on client pipeline.

---

### Internal Delivery / Engineering Team

**What they cared about**: Clear requirements, achievable timelines, technically interesting work, not being blamed when the regulatory deadline created pressure.

**Their concern with this project**: "The compliance deadline is fixed. The scope keeps growing as we onboard new banks. And we're told to build a platform when we've always built bespoke. How do we deliver all of this?"

**How I managed them**:
- The phased approach (compliance MVP first, scale second, beyond-compliance third) gave the team a clear, manageable scope for each phase. They weren't staring at a 5-year roadmap and feeling overwhelmed; they were delivering against a 6-month compliance milestone.
- When I pushed for the multi-bank configuration engine in Phase 1, I involved the engineering team in the architecture decision. They saw the value: building it now meant less rework later when bank #3 through #7 arrived.
- Protected them from scope creep. When individual banks requested bespoke features, I applied the decision framework (configuration parameter vs. core platform vs. no) before it reached the engineering backlog. The team didn't have to fight every custom request themselves.
- After launch, the infrastructure optimization work (right-sizing provisioning for different bank sizes) was technically interesting work that improved the system. It wasn't just business cost-cutting; it was engineering excellence.

**What they needed from me**: Scope clarity, protection from bespoke scope creep, phased milestones that felt achievable, and the political cover to say "this is a platform, not a custom build."

**Alignment mechanism**: Phase-based milestones, the configuration vs. core vs. no decision framework, regular scope reviews, and shared ownership of the architecture decisions.

---

### Sales / GTM Team

**What they cared about**: Pipeline, deal velocity, competitive differentiation, collateral they could use in pitches.

**Their concern with this project**: "We have two hot prospects. When can we tell them it's ready? Can we sell to more banks before it's fully built? What's the pitch against bespoke competitors?"

**How I managed them**:
- I was the GTM team before I was the PM. I'd built the pitch deck, taken the PoC to prospects, and sat in the rooms where the deals were discussed. This gave me a direct understanding of what sales needed: not feature lists, but a story about speed-to-compliance and total cost of ownership vs. bespoke builds.
- Set clear expectations about what was available in each phase. No selling capabilities that weren't built. The PoC-to-product transition was fast, but it wasn't instant. Sales needed honest timelines.
- After Phase 1, the sales pitch shifted from "we can help you comply" (table stakes) to "we can help you comply faster and cheaper than anyone else, and then monetize the infrastructure" (differentiated). The 5-year roadmap with 50+ revenue streams became the upsell story.

**What they needed from me**: Honest timelines, a competitive pitch narrative, and post-launch proof points (cost reduction, speed-to-compliance) they could use in deals.

**Alignment mechanism**: Direct collaboration (I was originally on this team), shared pipeline visibility, pitch narrative co-creation.

---

### European Regulators (Silent Stakeholder)

**What they cared about**: Banks complying with PSD2. Consumer protection. Open competition in the payments ecosystem.

**Their concern with this project**: None directly (regulators don't evaluate vendors). But their interpretation of PSD2 requirements was the immovable constraint around which everything else was prioritized.

**How I managed them**:
- Did not interact with regulators directly (that's the bank's responsibility). But I monitored regulatory guidance closely, especially national interpretations that varied from the EU-level directive.
- When regulatory interpretations changed (e.g., SCA flow requirements interpreted differently by a national regulator), I prioritized the platform update immediately, ahead of any feature work. Compliance gaps can't wait for the next sprint.
- The compliance mapping documentation I created for banking clients was designed to be regulator-readable: clear, traceable, and specific about how each requirement was implemented.

**What they needed from me**: Nothing directly. But the platform's compliance quality reflected on every bank using it.

**Alignment mechanism**: Regulatory monitoring, compliance mapping documents, priority handling of interpretation changes.

---

## How Stakeholder Dynamics Shifted Over the Project Lifecycle

| Phase | Who Had the Loudest Voice | My Focus |
|-------|--------------------------|----------|
| **GTM / PoC** | Sales team + banking prospects | Market validation, PoC demonstrations, building relationships |
| **PoC-to-product transition** | Internal leadership | Making the case for my role transition, platform vs. bespoke argument |
| **Phase 1: Compliance MVP** | Compliance officers + engineering | Regulatory mapping, deadline pressure, architecture decisions |
| **Phase 2: Scale** | Bank CTOs + delivery team | Integration flexibility, infrastructure optimization, new jurisdiction support |
| **Phase 3: Beyond compliance** | Sales + banking clients | 5-year roadmap, revenue streams beyond compliance, retention and upsell |

---

## Key Takeaway

The defining stakeholder challenge on this project was internal, not external. Banking clients were motivated (they had a regulatory deadline). The sales team was motivated (they had pipeline). Even compliance officers were motivated (they needed to pass audits).

The hardest stakeholder to manage was the internal consulting organization. Their business model, their incentive structures, and their professional identity were all built around bespoke client delivery. Convincing them to invest in a platform required proving, client by client, quarter by quarter, that the platform approach generated more revenue with less effort. It wasn't a one-time pitch. It was a 3-year demonstration.

---

*All company names, client names, and partner names have been anonymized. Stakeholder dynamics and management approaches are accurate as experienced.*
