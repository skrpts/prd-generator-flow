---
type: document
id: stakeholder-mapping-guide
title: Stakeholder Mapping Guide
description: "Guide to stakeholder identification, influence mapping, and engagement planning for product initiatives"
tags: [Production, Customer-Facing]
connections:
  - target: prd-reference-guide
    type: references
metadata:
  document_type: "guide"
  audience: "product-managers"
---

## Stakeholder Mapping Guide

Effective stakeholder management is the difference between a PRD that gets approved and one that languishes in review. This guide walks you through identifying stakeholders, understanding their interests, mapping their influence, and planning your engagement approach.

### Why Stakeholder Mapping Matters

Every product initiative exists in an organisational context. The best requirements in the world are useless if the wrong people review them, the right people are excluded, or key concerns are not addressed.

Common failures caused by poor stakeholder mapping:
- A PRD is rejected because a decision maker was not consulted until the final review
- Engineering raises feasibility concerns at the eleventh hour because they were not involved during scoping
- Customer support is overwhelmed by enquiries about a feature they did not know was launching
- Legal blocks a release because compliance was not considered in the requirements

### Step 1: Identify Your Stakeholders

Cast a wide net initially — it is easier to remove stakeholders from the list than to discover missing ones late in the process.

**Start with these questions:**
- Who can approve or block this initiative?
- Who will build, design, or test what we are specifying?
- Who will use the feature directly?
- Whose work will change because of this feature (even if they do not use it)?
- Who could influence the outcome through informal channels?
- Who was involved in similar past initiatives?

**Common stakeholders by function:**

| Function | Typical Stakeholders | Their Primary Concern |
|----------|---------------------|----------------------|
| Executive | VP Product, CEO, Business Unit Lead | Strategic alignment, ROI, timeline |
| Engineering | Engineering Lead, Architects, DevOps | Feasibility, complexity, maintenance burden |
| Design | Design Lead, UX Researcher | User experience, consistency, research backing |
| Customer-facing | Support Lead, Sales Lead, Customer Success | User impact, training needs, positioning |
| Operations | Legal, Compliance, Security | Risk, regulatory compliance, data handling |
| Finance | Finance Lead, Revenue Ops | Cost, revenue impact, pricing implications |

### Step 2: Map Influence and Impact

For each stakeholder, assess two dimensions:

**Influence:** How much power do they have to shape the outcome of this initiative?
- **High:** Can approve, block, or fundamentally redirect the initiative
- **Medium:** Can shape specific requirements or design decisions
- **Low:** Limited formal ability to affect the outcome

**Impact:** How much does this initiative affect them?
- **High:** Their work, metrics, or responsibilities are significantly changed
- **Medium:** Noticeable effect on their work but manageable
- **Low:** Minimal direct effect

### Step 3: Determine Engagement Level

Based on the influence-impact matrix, assign an engagement level:

**Empower (High Influence, High Impact)**
These stakeholders are your partners. Involve them in requirements development, review cycles, and key decisions. Schedule regular one-on-one updates. Their concerns are your constraints.

**Collaborate (High Influence, Low Impact)**
These stakeholders have the power to block you but are not deeply affected. Keep them satisfied through regular updates and by addressing their concerns promptly. Do not burden them with detail — give them summaries and decision points.

**Consult (Low Influence, High Impact)**
These stakeholders are significantly affected but have limited power. Their input is valuable for getting requirements right. Actively seek their feedback on relevant sections. Their frustrations often surface as post-launch problems if ignored.

**Inform (Low Influence, Low Impact)**
These stakeholders need to know what is happening but do not need to participate in decisions. Periodic written updates are sufficient. Include them in announcement communications.

### Step 4: Identify Concerns and Align Interests

For each key stakeholder, answer:
- What do they care about most regarding this initiative?
- What would make them enthusiastic about it?
- What would make them oppose it?
- What information do they need to make a decision?
- What past experiences shape their perspective?

Use this understanding to tailor your PRD communication:
- For executives: Lead with strategic alignment and expected business impact
- For engineering: Lead with technical scope and known constraints
- For design: Lead with user research and persona insights
- For customer-facing teams: Lead with user impact and support implications

### Step 5: Plan for Conflict

Stakeholder conflicts are normal. Different functions have different priorities. Plan for them:

**Common conflict patterns:**
- Engineering says "too complex" while Product says "essential for users"
- Sales wants features for one large customer while Product prioritises the broader base
- Legal wants restrictive data handling while Product wants seamless UX
- Finance wants cost minimisation while Engineering wants the right tool for the job

**Resolution approach:**
1. Acknowledge both perspectives
2. Return to the problem statement — which position better serves the stated user need?
3. Quantify the trade-off — what does each option cost (in time, money, user impact)?
4. Escalate to the appropriate decision maker with a clear framing of the trade-off
5. Document the decision and rationale in the PRD

### Step 6: Create Your Engagement Plan

Document your plan in a simple table:

| Stakeholder | Engagement Level | Key Concern | Communication | Frequency | PRD Involvement |
|------------|-----------------|-------------|---------------|-----------|----------------|
| [Name/Role] | [Empower/Collaborate/Consult/Inform] | [Primary concern] | [Meeting/Email/Slack] | [Daily/Weekly/Milestone] | [Which sections they review] |

Review this plan at the start of every initiative. Update it as the initiative evolves and new stakeholders emerge.
