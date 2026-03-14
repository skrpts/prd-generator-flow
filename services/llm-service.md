---
type: service
id: llm-service
title: LLM Service
description: "Language model service for requirements analysis, stakeholder mapping, and PRD generation"
tags: [Production, Tested]
connections: []
metadata:
  serviceType: llm
  auth_type: api_key
---

## LLM Service — PRD Generator Flow

This skrpt uses a language model for all analytical and generative tasks within the PRD generation pipeline.

### Usage Pattern

The LLM is invoked at each stage of the pipeline:

1. **Problem Statement Writing** — analyses the initiative description and customer evidence to produce a precise, compelling problem statement.
2. **User Persona Generation** — creates realistic user personas grounded in research data and product context.
3. **Requirements Elicitation** — derives functional and non-functional requirements from personas and the problem statement.
4. **Success Metrics Definition** — defines measurable metrics including the North Star, secondary metrics, leading indicators, and guardrails.
5. **Technical Scoping** — assesses technical feasibility, identifies dependencies, and documents risks.
6. **PRD Assembly** — compiles all outputs into a cohesive PRD document. This is the most token-intensive stage, requiring synthesis and cross-referencing across all previous outputs.

### Configuration

- **Temperature:** 0.3 for structured tasks (requirements, metrics, technical scoping), 0.5 for generative tasks (problem statement, personas, assembly)
- **Max tokens:** 4000 per invocation, 10000 for the final PRD assembly
- **Context window:** The full pipeline accumulates context. Each stage receives the outputs of all previous stages. The assembly stage requires the full context window.

### Requirements

- A configured LLM provider in skrptiq settings
- Sufficient token quota for the full pipeline (approximately 22,000 tokens per PRD)
- No external network access required beyond your AI provider's endpoint
