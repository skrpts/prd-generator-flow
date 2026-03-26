---
type: prompt
id: technical-constraints-prompt
title: Technical Constraints Documenter
description: "Document technical constraints, dependencies, architecture impact, and migration considerations"
tags: [Production]
connections:
  - target: technical-scoping
    type: derived_from
  - target: prd-assembler
    type: uses
metadata:
  estimated_duration: "4 minutes"
  avg_tokens: 3000
  trigger: manual
---

## Technical Constraints Documenter

You are a senior technical product manager documenting the technical landscape that a product initiative must navigate. Your output helps engineering teams estimate effort, identify risks, and plan their architecture approach.

### Input

**Requirements summary:** {{steps.requirements-prompt.output}}

**Current system architecture:** {{input.technical_context}}

**Technology stack:** {{input.technical_context}}

**Known technical constraints:** {{input.technical_context}}

**Team capabilities:** Infer from {{input.initiative_description}} and {{input.technical_context}}.

### Instructions

Produce a thorough technical constraints and scoping document for this initiative. Work through each section systematically.

**Section 1: System Dependencies**

Identify every system, service, or data source the initiative depends on.

For each internal dependency:
- **System name:** [Name]
- **Owning team:** [Team responsible]
- **Dependency type:** Read-only, read-write, or event-driven
- **Current capacity:** Any known limitations (rate limits, data volume caps, queue depths)
- **Availability:** Reliability track record and SLA
- **Change risk:** Is this system stable, or are changes planned that could affect this initiative?

For each external dependency:
- **Service name:** [Name]
- **Provider:** [Company]
- **API version:** [Version in use]
- **SLA:** [Uptime guarantee]
- **Rate limits:** [Requests per second/minute/hour]
- **Cost model:** [Per request, subscription, usage-based]
- **Fallback strategy:** What happens when this service is unavailable?

For each data dependency:
- **Data source:** [Name]
- **Current format:** [Schema, file format, API response structure]
- **Required transformations:** What must change for this initiative?
- **Volume:** Current size and growth rate
- **Quality:** Known data quality issues

**Section 2: Architecture Impact**

Describe how the initiative affects the existing system:

**New components to build:**
For each new component:
- Name and purpose
- Technology recommendation (with justification)
- Estimated complexity (Simple, Moderate, Complex)
- Interfaces with existing systems

**Existing components to modify:**
For each modification:
- Component name
- Nature of change (new endpoint, schema change, behaviour change, performance optimisation)
- Estimated scope of change (Small patch, Moderate refactor, Significant rework)
- Risk of regression (Low, Medium, High)

**Integration contracts:**
For each integration point:
- What connects to what
- Protocol (REST, GraphQL, gRPC, events, direct DB)
- Contract format (schema, API specification, event format)
- Versioning strategy

**Section 3: Technical Risks**

Identify and assess technical risks:

| ID | Risk | Category | Likelihood | Impact | Mitigation |
|----|------|----------|-----------|--------|-----------|
| TR-01 | [Description] | [Complexity/Performance/Security/Reliability/Compatibility] | [H/M/L] | [H/M/L] | [Approach] |

For each High likelihood or High impact risk, provide a detailed mitigation plan:
- What spike or proof-of-concept work would reduce uncertainty
- What alternative approaches exist if the risk materialises
- What monitoring would detect the risk early

**Section 4: Infrastructure Requirements**

List new infrastructure needed:

- **Compute:** New services, workers, functions — with estimated resource requirements
- **Storage:** New databases, caches, blob storage — with estimated capacity
- **Networking:** New endpoints, load balancers, CDN rules, firewall changes
- **Monitoring:** New dashboards, alerts, log aggregation, tracing
- **DevOps:** CI/CD pipeline changes, new environments, deployment process modifications

Include estimated cost impact for any significant infrastructure additions.

**Section 5: Migration and Rollout Strategy**

**Data migration:**
- Is data migration required? If yes, describe the migration plan
- Can the migration run without downtime?
- What is the estimated duration for the migration?
- What is the rollback plan if migration fails?

**Feature rollout:**
- Recommended rollout strategy (big bang, percentage rollout, segment-based, beta programme)
- Feature flag requirements
- Rollback procedure and triggers
- Communication plan for affected users

**Backwards compatibility:**
- Must old API versions continue to work? For how long?
- Must old data formats continue to be readable?
- Are there mobile app versions that need to continue working?

**Section 6: Feasibility Summary**

Provide an overall feasibility assessment:

| Requirement Area | Feasibility | Notes |
|-----------------|-------------|-------|
| [Area] | [Straightforward / Achievable / Challenging / Uncertain / Infeasible] | [Brief justification] |

Flag any "Uncertain" or "Infeasible" items as blocking — these must be resolved before the PRD can be approved.

### Output Format

Present each section with clear headings. Use tables for structured data. Provide enough detail for engineering leads to validate and refine during technical planning.
