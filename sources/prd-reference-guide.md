---
type: source
id: prd-reference-guide
title: PRD Reference Guide
description: "Reference standards for PRD writing, including section definitions, quality criteria, and industry conventions"
tags: [Production, Planning, Writing]
connections: []
metadata:
  source_type: "reference"
  last_updated: "2026-03-10"
---

## PRD Reference Guide

This source document defines the standards, conventions, and quality criteria for product requirements documents produced by this pipeline.

### What a PRD Is (and Is Not)

**A PRD is:**
- A contract between product, engineering, and design that defines what will be built and why
- A reference document that guides decisions throughout the build process
- A record of the rationale behind requirements decisions
- A communication tool for stakeholders at different levels of detail

**A PRD is not:**
- A design document (it does not specify UI layouts or interaction patterns)
- A technical specification (it does not prescribe architecture or implementation)
- A project plan (it does not define sprints, tasks, or assignments)
- A static document (it should evolve as understanding deepens)

### PRD Quality Criteria

**Completeness:** Every section is addressed. Empty sections indicate gaps in understanding that must be resolved.

**Consistency:** Requirements do not contradict each other. Success metrics align with the problem statement. Technical scope matches the requirements.

**Clarity:** Any reader — product, engineering, design, or executive — can understand each section without asking clarifying questions. Domain-specific terms are defined in the glossary.

**Traceability:** Every requirement traces to a user need (persona) and business objective. Requirements without traceability are candidates for removal.

**Testability:** Every requirement has acceptance criteria that a QA engineer could execute without interpretation.

**Prioritisation:** All requirements are prioritised. The distribution follows MoSCoW guidelines:
- Must Have: 50-60% of requirements (never exceed 60%)
- Should Have: 20-30%
- Could Have: 10-20%
- Won't Have: documented but explicitly deferred

### Section Standards

**Problem Statement:**
- Must be solution-agnostic (describes the problem, not a feature)
- Must quantify impact where possible
- Must identify who is affected
- Must pass the "so what?" test

**User Personas:**
- Must include at least one primary and one anti-persona
- Must be grounded in research or data, not assumptions
- Must include behavioural patterns, not just demographics
- Must include realistic quotes

**Requirements:**
- Each requirement must be atomic (tests one thing)
- Each requirement must use active voice ("The system sends..." not "An email should be sent...")
- Each requirement must have a unique ID for reference
- Each requirement must have acceptance criteria

**Success Metrics:**
- Must include a single North Star metric
- Must include guardrail metrics (things that must not degrade)
- Must include measurement method and cadence
- Must specify baselines and targets with timeframes

**Technical Scope:**
- Must identify all dependencies (internal and external)
- Must assess feasibility (not just describe the technical landscape)
- Must include a rollout and rollback strategy
- Must flag risks with likelihood and impact ratings

### Version Control

PRDs use semantic versioning:
- **Major version (2.0):** Fundamental changes to scope, problem definition, or success criteria
- **Minor version (1.1):** New requirements added, existing requirements modified, metrics updated
- **Patch version (1.0.1):** Wording clarifications, typo fixes, formatting improvements

Every version change must be documented in the change log with: date, author, description of change, and reason.

### Review and Approval

A PRD moves through three statuses:

| Status | Definition | Who Reviews |
|--------|-----------|-------------|
| Draft | Under development, not ready for review | Author only |
| Review | Ready for stakeholder feedback | Engineering lead, Design lead, key stakeholders |
| Approved | Accepted and ready for implementation | Decision makers sign off |

**Review checklist for reviewers:**
- Does the problem statement reflect a genuine user need?
- Do the personas feel realistic?
- Are the Must Have requirements truly essential?
- Are the success metrics measurable and meaningful?
- Are the technical risks adequately mitigated?
- Is the timeline realistic given the scope?

### Common PRD Mistakes

1. **Solution-first thinking:** Writing requirements around a predetermined solution rather than starting from the problem
2. **Missing the anti-persona:** Without an explicit anti-persona, scope creep is inevitable
3. **Unmeasurable success:** "Improve user experience" is not a metric. Define how improvement will be measured.
4. **Ignoring non-functional requirements:** Performance, security, and accessibility are not "nice to haves" — they are requirements
5. **Static PRDs:** A PRD that is written once and never updated becomes a fiction. Build in a revision cycle.
6. **Over-specification:** Prescribing implementation details (specific algorithms, database schemas, API designs) belongs in a technical spec, not a PRD
