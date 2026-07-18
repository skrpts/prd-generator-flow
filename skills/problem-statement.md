---
type: skill
id: problem-statement
title: Problem Statement
description: "Crafting a clear, evidence-grounded problem statement that anchors the entire product requirements document"
tags: [Production, Planning, Strategy]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "3 minutes"
  avg_tokens: 2000
  trigger: manual
---

## Problem Statement

This skill produces the problem statement that grounds the whole PRD. Every requirement, metric, and design decision that follows must trace back to it, so the statement has to be specific about who is affected, what they experience, and why it matters.

### Core Capability

Given the initiative description, customer evidence, and business context, this skill answers the five framing questions (who, what, when/where, impact, cost of inaction) and synthesises them into a short-form statement, a long-form context paragraph, and a supporting-evidence list with source and recency.

### Method

1. **Frame:** Identify the specific affected group, describe the problem in the user's terms (observable and measurable), and establish where and how often it occurs.
2. **Quantify:** Set out the revenue, efficiency, experience, and strategic impact, plus the trajectory if nothing is done.
3. **Ground:** Attach concrete evidence to each claim, flagging anything older than twelve months as potentially stale.

### Output Structure

A short-form problem statement, a long-form context paragraph, and a supporting-evidence list. This artefact feeds the personas, requirements, success-metrics, and assembly stages downstream.
