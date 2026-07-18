---
type: skill
id: prd-assembly
title: PRD Assembler
description: "Assembling all pipeline outputs into a single, complete, reviewable product requirements document"
tags: [Production, Planning, Strategy]
connections:
  - target: llm-service
    type: runs_on
  - target: prd-template
    type: references
metadata:
  estimated_duration: "5 minutes"
  avg_tokens: 5000
  trigger: manual
---

## PRD Assembler

This skill assembles the outputs of the full analysis pipeline into a single product requirements document — detailed enough for engineering estimation, clear enough for stakeholder approval, and structured enough for ongoing reference.

### Core Capability

Given the problem statement, user personas, requirements, success metrics, and technical scope as context, this skill compiles them into a complete PRD following the prd-template: header and sign-off table, executive summary, problem statement, personas, requirements, success metrics, technical scope, timeline, open questions and risks, and appendices.

### Method

1. **Import and reconcile:** Bring each upstream artefact into its section without loss, resolving contradictions between requirements, metrics, and scope.
2. **Synthesise:** Write the executive summary and the suggested timeline from the assembled material, and build the traceability matrix linking requirements to personas and business objectives.
3. **Quality-check:** Verify every Must Have traces to the primary persona and the problem statement, the North Star aligns with the stated impact, and every technical risk has a mitigation.

### Output Structure

A single markdown PRD (3000–5000 words) with consistent heading levels. This is the deliverable of the workflow; language-polish refines it into the final output.
