---
type: asset
id: prd-template
title: PRD Template
description: "Template for the final product requirements document"
tags: [Production, Customer-Facing]
connections: []
metadata:
  asset_type: "template"
  format: "markdown"
---

## PRD Template

Use this template structure when assembling the final product requirements document.

---

# Product Requirements Document: [Initiative Name]

| Field | Value |
|-------|-------|
| **Product** | [Product name] |
| **Initiative** | [Initiative name] |
| **Version** | 1.0 |
| **Author** | [Author name] |
| **Date** | [YYYY-MM-DD] |
| **Status** | Draft / Review / Approved |

### Stakeholder Sign-Off

| Role | Name | Status | Date |
|------|------|--------|------|
| [Decision Maker 1] | [Name] | Pending | |
| [Decision Maker 2] | [Name] | Pending | |
| [Engineering Lead] | [Name] | Pending | |
| [Design Lead] | [Name] | Pending | |

## 1. Executive Summary

[Maximum 300 words. Problem, audience, solution, key metric, critical dependencies.]

## 2. Problem Statement

### Short Form
[2-3 sentences. The version for slide decks and stakeholder conversations.]

### Long Form
[1-2 paragraphs with supporting evidence and quantified impact.]

### Supporting Evidence
| Evidence | Source | Date |
|----------|--------|------|
| [Data point or quote] | [Source] | [Date] |

## 3. User Personas

### Persona Overview
[Brief narrative connecting personas to each other and the problem]

### Primary Persona: [Name]

| Attribute | Detail |
|-----------|--------|
| **Role** | [Job title, company context] |
| **Experience** | [Years, technical proficiency] |
| **Primary goal** | [What they want to achieve] |
| **Key frustration** | [Main pain point] |

**Goals:** [Bullet list]

**Frustrations:** [Bullet list]

**Current workaround:** [Description]

**Quotes:**
> "[Quote about frustration]"
> "[Quote about ideal solution]"

### Secondary Persona: [Name]
[Same structure]

### Anti-Persona: [Name]
[Description of who this is NOT for and why]

## 4. Requirements

### Summary
| Priority | Count | Percentage |
|----------|-------|-----------|
| Must Have | [X] | [X%] |
| Should Have | [X] | [X%] |
| Could Have | [X] | [X%] |
| Won't Have | [X] | [X%] |

### Functional Requirements

#### Epic: [Epic Name]

**[REQ-001] [Title]**
- **Description:** [What the system must do]
- **Priority:** [Must Have / Should Have / Could Have / Won't Have]
- **Persona:** [Which persona this serves]
- **Acceptance Criteria:**
  - [Criterion 1]
  - [Criterion 2]
- **Dependencies:** [REQ-XXX or None]

[Continue for each requirement]

### Non-Functional Requirements

#### Performance
| Requirement | Target | Measurement |
|-------------|--------|-------------|
| [Metric] | [Target] | [How measured] |

#### Security
[Requirements list]

#### Accessibility
[Requirements list]

#### Scalability
[Requirements list]

#### Reliability
[Requirements list]

### Constraints
| Type | Constraint | Impact |
|------|-----------|--------|
| Technical | [Description] | [How it limits design options] |
| Business | [Description] | [How it limits scope] |
| Regulatory | [Description] | [What must be complied with] |

## 5. Success Metrics

### North Star Metric
| Field | Value |
|-------|-------|
| **Metric** | [Name] |
| **Definition** | [Exactly what is measured] |
| **Baseline** | [Current value] |
| **Target** | [Target value + timeframe] |
| **Measurement** | [How tracked] |
| **Review cadence** | [Frequency] |

### Secondary Metrics
| Metric | Baseline | Target | Relationship to North Star |
|--------|----------|--------|---------------------------|
| [Name] | [Value] | [Value] | [Leading/Component/Contextual] |

### Leading Indicators
| Indicator | Signal Threshold | Time Advantage |
|-----------|-----------------|----------------|
| [Name] | [Good/Bad thresholds] | [How far ahead it signals] |

### Guardrail Metrics
| Metric | Acceptable Range | Action if Breached |
|--------|-----------------|-------------------|
| [Name] | [Range] | [Action] |

### Anti-Metrics
| Metric | Why Not to Optimise | Focus Instead On |
|--------|--------------------|--------------------|
| [Name] | [Reason] | [Better metric] |

## 6. Technical Scope

### Dependencies
| Dependency | Type | Owner | Risk |
|-----------|------|-------|------|
| [System/Service] | [Internal/External] | [Team] | [Low/Medium/High] |

### Architecture Impact
[New components, modified components, integration points]

### Technical Risks
| ID | Risk | Likelihood | Impact | Mitigation |
|----|------|-----------|--------|-----------|
| TR-01 | [Description] | [H/M/L] | [H/M/L] | [Approach] |

### Infrastructure Requirements
[Compute, storage, networking, monitoring needs]

### Migration and Rollout
[Data migration plan, feature flagging, rollback strategy]

### Feasibility Summary
| Area | Rating | Notes |
|------|--------|-------|
| [Area] | [Straightforward/Achievable/Challenging/Uncertain] | [Brief note] |

## 7. Timeline and Milestones

| Phase | Duration | Key Activities | Decision Points |
|-------|----------|---------------|-----------------|
| Discovery | [Duration] | [Activities] | [Decisions needed] |
| Build | [Duration] | [Activities] | [Decisions needed] |
| Test | [Duration] | [Activities] | [Decisions needed] |
| Launch | [Duration] | [Activities] | [Decisions needed] |

## 8. Open Questions and Risks

| Item | Type | Owner | Deadline | Blocking? |
|------|------|-------|----------|-----------|
| [Question/Risk] | [Question/Risk] | [Name] | [Date] | [Yes/No] |

## Appendices

### A. Glossary
| Term | Definition |
|------|-----------|
| [Term] | [Definition] |

### B. Traceability Matrix
| Requirement | Persona | Business Objective |
|------------|---------|-------------------|
| REQ-001 | [Persona] | [Objective] |

### C. Change Log
| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | [Date] | [Author] | Initial PRD |

### D. References
- [Link to related documents]
- [Link to research]
- [Link to designs]

---

*This PRD is a living document. Update it as decisions are made and understanding deepens. Log all changes in the Change Log.*
