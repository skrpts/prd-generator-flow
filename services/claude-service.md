---
type: service
id: claude-service
title: Claude Service
description: "How this skrpt uses Anthropic Claude for requirements analysis, stakeholder mapping, and PRD generation"
tags: [Production, Tested]
connections: []
metadata:
  provider: "anthropic"
  model: "claude-sonnet"
  estimated_duration: "N/A"
---

## Claude Service — PRD Generator Flow

This skrpt uses Anthropic Claude as its primary AI service for all analytical and generative tasks within the PRD generation pipeline.

### Usage Pattern

Claude is invoked at each stage of the pipeline:

1. **Problem Statement Writing** — Claude analyses the initiative description and customer evidence to produce a precise, compelling problem statement. This requires the ability to distil complex situations into clear articulations of user pain.

2. **User Persona Generation** — Claude creates realistic user personas grounded in research data and product context. This requires understanding of user-centric thinking and the ability to create specific, believable characters that drive requirements decisions.

3. **Requirements Elicitation** — Claude derives functional and non-functional requirements from personas and the problem statement. This requires structured analytical thinking and knowledge of requirements engineering best practices.

4. **Success Metrics Definition** — Claude defines measurable metrics including the North Star, secondary metrics, leading indicators, and guardrails. This requires understanding of product analytics and the ability to identify meaningful measurements.

5. **Technical Scoping** — Claude assesses technical feasibility, identifies dependencies, and documents risks. This requires broad technical knowledge and the ability to reason about system architecture and integration patterns.

6. **PRD Assembly** — Claude compiles all outputs into a cohesive PRD document. This is the most token-intensive stage, requiring synthesis, cross-referencing, and quality checking across all previous outputs.

### Configuration

- **Temperature:** 0.3 for structured tasks (requirements, metrics, technical scoping), 0.5 for generative tasks (problem statement, personas, assembly)
- **Max tokens:** 4000 per invocation, 10000 for the final PRD assembly
- **Context window:** The full pipeline accumulates context. Each stage receives the outputs of all previous stages. The assembly stage requires the full context window.

### Requirements

- An active Anthropic API key or Claude CLI access
- Sufficient token quota for the full pipeline (approximately 22,000 tokens per PRD)
- No external network access required beyond the Anthropic API endpoint
