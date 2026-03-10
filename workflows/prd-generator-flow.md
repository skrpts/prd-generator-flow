---
type: workflow
id: prd-generator-flow
title: PRD Generator Flow
description: "End-to-end workflow for generating a comprehensive product requirements document with stakeholder analysis, success metrics, and technical constraints"
tags: [Production, Tested]
connections:
  - target: requirements-structuring
    type: uses
  - target: stakeholder-analysis
    type: uses
  - target: technical-scoping
    type: uses
  - target: problem-statement-writer
    type: uses
  - target: user-persona-generator
    type: uses
  - target: requirements-prompt
    type: uses
  - target: success-metrics-definer
    type: uses
  - target: technical-constraints-prompt
    type: uses
  - target: prd-assembler
    type: uses
  - target: claude-service
    type: runs_on
  - target: prd-reference-guide
    type: references
  - target: prd-writing-standards
    type: references
  - target: stakeholder-mapping-guide
    type: references
  - target: prd-template
    type: references
  - target: persona-card-template
    type: references
metadata:
  estimated_duration: "30 minutes"
  avg_tokens: 22000
  trigger: manual
---

## PRD Generator Flow

This workflow produces a comprehensive product requirements document (PRD) from initial problem definition through to assembled, reviewable document. It follows a six-stage pipeline that addresses the full spectrum of PRD content: problem framing, user context, requirements elicitation, success measurement, technical feasibility, and document assembly.

### Stage 1: Problem Statement

**Input:** A product opportunity, customer request, or strategic initiative — in any level of detail.

1. Invoke the **problem-statement-writer** prompt.
2. The prompt produces:
   - A clear, concise problem statement (the "why")
   - Market or user context that makes the problem urgent
   - Impact of inaction (what happens if this problem is not solved)
   - Connection to business objectives or strategy
3. **Validation gate:** The problem statement must pass the "so what?" test. If a reader could reasonably respond with "so what?", the statement needs more specificity about who is affected and what the consequence is.

### Stage 2: User Personas

**Input:** The problem statement from Stage 1, plus any available user research or customer data.

1. Invoke the **user-persona-generator** prompt.
2. The prompt generates 2-4 user personas relevant to this product initiative:
   - Primary persona (the main user the PRD serves)
   - Secondary personas (other users who interact with or are affected by the feature)
   - Anti-persona (who this is explicitly NOT for — prevents scope creep)
3. Each persona includes demographics, goals, frustrations, current workflow, and relationship to the problem.
4. **Validation gate:** At least one persona must directly experience the problem defined in Stage 1. If no persona clearly maps to the problem, either the problem statement or the personas need revision.

### Stage 3: Requirements Elicitation

**Input:** Problem statement and user personas from Stages 1-2.

1. Invoke the **requirements-prompt** using the **requirements-structuring** skill.
2. The prompt elicits and structures both functional and non-functional requirements:
   - **Functional requirements:** What the product must do, organised hierarchically
   - **Non-functional requirements:** Performance, security, accessibility, scalability, compliance
   - **Constraints:** Technical, regulatory, or business constraints that limit design options
3. Each requirement is assigned a priority (Must Have, Should Have, Could Have, Won't Have).
4. **Validation gate:** Every Must Have requirement must trace back to the primary persona's goals. If a Must Have cannot be justified by the problem statement and personas, it should be downgraded.

### Stage 4: Success Metrics

**Input:** Requirements from Stage 3, problem statement from Stage 1.

1. Invoke the **success-metrics-definer** prompt.
2. The prompt defines measurable success criteria:
   - Primary success metric (the one number that tells you the initiative worked)
   - Secondary metrics (supporting indicators)
   - Leading indicators (early signals of success or failure)
   - Guardrail metrics (things that must NOT degrade as a result of this initiative)
3. Each metric includes a baseline, target, measurement method, and review cadence.
4. **Validation gate:** Every metric must be measurable with currently available or reasonably buildable instrumentation. Aspirational metrics with no measurement path are flagged.

### Stage 5: Technical Scoping

**Input:** Requirements from Stage 3.

1. Invoke the **technical-constraints-prompt** using the **technical-scoping** skill.
2. The prompt documents:
   - Technical dependencies (systems, APIs, data sources the initiative depends on)
   - Architecture considerations (how this fits into the existing system)
   - Technical risks (unknowns, complexity hotspots, scalability concerns)
   - Infrastructure requirements (new services, storage, compute)
   - Migration considerations (data migration, feature flagging, rollback plan)
3. **Validation gate:** Each technical dependency must be verified as available. Any dependency with unknown availability is flagged as a blocking risk.

### Stage 6: PRD Assembly

**Input:** All outputs from Stages 1-5.

1. Invoke the **prd-assembler** prompt using the **requirements-structuring** skill.
2. Compile all sections into a single PRD following the **prd-template**.
3. Add:
   - Table of contents
   - Stakeholder sign-off section
   - Change log
   - Glossary of domain terms
   - Cross-references between related requirements
4. **Output:** A complete PRD ready for stakeholder review and engineering handoff.

### Error Handling

- **Insufficient context:** If the initial input is too vague to produce a meaningful problem statement, prompt the user for specific customer quotes, data points, or strategic context.
- **Persona-problem mismatch:** If the generated personas do not experience the stated problem, flag the disconnect and recommend re-examining the problem definition.
- **Requirements scope explosion:** If more than 30 requirements are generated, recommend splitting into multiple PRDs or phasing the initiative.
- **Unmeasurable metrics:** If success metrics cannot be measured with existing tooling, include a "metrics infrastructure" requirement in the PRD.
- **Technical blocker:** If technical scoping reveals a fundamental feasibility issue, halt PRD generation and recommend a technical spike before proceeding.
