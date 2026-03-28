---
type: skill
id: requirements-structuring
title: Requirements Structuring
description: "Organising raw requirements into structured, hierarchical format with clear categorisation and traceability"
tags: [Production, Tested]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "4 minutes"
  avg_tokens: 3000
  trigger: manual
---

## Requirements Structuring

This skill transforms unstructured requirements input — stakeholder requests, user stories, meeting notes, feature ideas — into a rigorously structured requirements hierarchy. The output is suitable for inclusion in specifications and for engineering estimation.

### Core Capability

Given raw requirements input from any source, this skill produces a structured, hierarchical requirements document that is complete, consistent, unambiguous, and traceable to user needs.

### Structuring Method

**1. Requirements Extraction**

Scan the input for explicit and implicit requirements:
- **Explicit requirements:** Statements that directly state what the product must do ("Users must be able to export data as CSV")
- **Implicit requirements:** Needs implied by the context but not stated ("If users can export, they need a way to select which data to include")
- **Derived requirements:** Technical necessities that follow from functional requirements ("CSV export requires a background job queue for large datasets")

**2. Categorisation**

Assign each requirement to a category:

| Category | Definition | Examples |
|----------|-----------|----------|
| Functional | What the product must do | "Users can filter the dashboard by date range" |
| Performance | How fast, how much, how many | "Page loads within 2 seconds for datasets up to 10,000 rows" |
| Security | Access control, data protection | "User data is encrypted at rest using AES-256" |
| Accessibility | WCAG compliance, inclusive design | "All interactive elements are keyboard navigable" |
| Scalability | Growth and load handling | "The system supports 10x current user count without architecture changes" |
| Compliance | Regulatory and legal | "Data handling complies with GDPR Article 17 (right to erasure)" |
| Usability | Ease of use, learnability | "A new user can complete their first task within 5 minutes without documentation" |

**3. Hierarchical Organisation**

Structure requirements into a three-level hierarchy:

- **Epic level:** A high-level capability area (e.g., "Data Export")
  - **Feature level:** A specific feature within the epic (e.g., "CSV Export", "PDF Export")
    - **Requirement level:** An individual, testable requirement (e.g., "User can select specific columns for CSV export")

Each requirement at the lowest level must be:
- **Atomic:** Describes one thing only
- **Testable:** Has a clear pass/fail condition
- **Traceable:** Links back to a user need or business objective
- **Independent:** Can be implemented without depending on requirements in other epics (where possible)

**4. Priority Assignment**

Apply MoSCoW prioritisation:
- **Must Have:** The initiative fails without this. Cap at 60% of total requirements.
- **Should Have:** Significantly impacts the experience if missing. 20-30% of total.
- **Could Have:** Enhances the experience. 10-20% of total.
- **Won't Have:** Explicitly deferred. No limit.

**5. Dependency Mapping**

Identify dependencies between requirements:
- Which requirements must be implemented before others?
- Which requirements share infrastructure or data models?
- Which requirements conflict with or constrain each other?

### Output Structure

The structured output includes:
- A requirements summary table (ID, title, category, priority, dependencies)
- Detailed requirement cards (ID, title, description, acceptance criteria, priority, category, dependencies, notes)
- A dependency diagram showing critical paths
- A traceability matrix linking requirements to user personas and business objectives

### Anti-Patterns

- **Gold plating:** Adding requirements beyond what users need. Every requirement must trace to a stated need.
- **Ambiguous language:** "The system should handle errors gracefully" is not a requirement. Specify which errors, what "graceful" looks like, and what the user sees.
- **Hidden assumptions:** If a requirement assumes something about the technical environment, state the assumption explicitly.
- **Scope creep markers:** Requirements starting with "while we're at it" or "it would also be nice to" are scope creep signals. Evaluate them separately.
