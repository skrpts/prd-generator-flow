---
type: skill
id: technical-scoping
title: Technical Scoping
description: "Assessing technical feasibility, identifying constraints, dependencies, and architectural implications"
tags: [Production, Tested, Code, Planning]
connections:
  - target: llm-service
    type: runs_on
  - target: prd-reference-guide
    type: references
metadata:
  estimated_duration: "5 minutes"
  avg_tokens: 3000
  trigger: manual
---

## Technical Scoping

This skill assesses the technical feasibility and implications of a product initiative. It produces a technical scoping document that engineering teams can use to estimate effort, identify risks, and plan architecture.

### Core Capability

Given a set of product requirements, this skill evaluates what is technically required to deliver them, what risks exist, what dependencies must be resolved, and what infrastructure changes are needed. It does not design the solution — it maps the technical landscape that the solution must navigate.

### Scoping Dimensions

**1. System Dependencies**

Identify every system, service, or data source the initiative depends on:

- **Internal dependencies:** Existing services, databases, APIs, shared libraries, or platform capabilities that the initiative relies on. For each, note: current capacity, known limitations, team ownership, and any planned changes.
- **External dependencies:** Third-party APIs, services, SDKs, or data feeds. For each, note: SLA, pricing model, rate limits, and fallback strategy if the service is unavailable.
- **Data dependencies:** Data that must exist, be migrated, or be generated for the initiative to function. Note: current format, required transformations, volume, and quality.

**2. Architecture Impact**

Assess how the initiative affects the existing system architecture:

- **New components:** Services, modules, or systems that must be created
- **Modified components:** Existing components that must be changed — and the scope of those changes
- **Integration points:** Where new and existing components connect, and what contracts (APIs, events, data formats) they share
- **Scaling considerations:** Will the initiative change load patterns? Does it require different scaling strategies than the current architecture supports?

**3. Technical Risks**

Identify risks that could affect delivery, quality, or maintainability:

| Risk Category | Examples |
|--------------|----------|
| Complexity | Novel algorithms, unfamiliar technology, complex state management |
| Performance | Latency-sensitive operations, large data processing, real-time requirements |
| Security | New attack surfaces, sensitive data handling, authentication flows |
| Reliability | Single points of failure, eventual consistency challenges, data integrity risks |
| Compatibility | Browser support requirements, backwards compatibility, migration paths |

For each risk:
- **Description:** What could go wrong
- **Likelihood:** High, Medium, or Low
- **Impact:** What the consequence would be
- **Mitigation:** How to reduce the risk (spike, prototype, progressive rollout, feature flag)

**4. Infrastructure Requirements**

Identify new infrastructure needed:

- **Compute:** New services, functions, workers, or processing capacity
- **Storage:** New databases, caches, file storage, or schema changes to existing stores
- **Networking:** New endpoints, load balancers, CDN configuration, DNS changes
- **Monitoring:** New metrics, alerts, dashboards, or logging requirements
- **Environments:** Changes to development, staging, or production environments

**5. Migration and Rollout**

Assess the transition from current state to target state:

- **Data migration:** Must existing data be transformed? What is the estimated duration? Can it run without downtime?
- **Feature flagging:** Should the feature be rolled out progressively? What flag strategy is appropriate?
- **Rollback plan:** If the release causes problems, how is the previous state restored? Is rollback automatic or manual?
- **Backwards compatibility:** Must old clients, APIs, or data formats continue to work during or after the transition?

### Feasibility Assessment

For each major requirement, provide a feasibility rating:

| Rating | Definition |
|--------|-----------|
| Straightforward | Well-understood problem, proven approach, low risk |
| Achievable | Some complexity or unknowns, but team has relevant experience |
| Challenging | Significant unknowns, may require spikes or prototyping |
| Uncertain | Fundamental feasibility question — recommend a spike before committing |
| Infeasible | Cannot be achieved with current technology, budget, or timeline |

### Output Structure

The technical scoping produces:
- A dependency register (all internal, external, and data dependencies)
- An architecture impact assessment (new components, modified components, integration points)
- A risk register (categorised risks with likelihood, impact, and mitigation)
- An infrastructure requirements list
- A migration and rollout plan
- A feasibility summary with per-requirement ratings
