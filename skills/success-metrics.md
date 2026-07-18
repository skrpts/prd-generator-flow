---
type: skill
id: success-metrics
title: Success Metrics
description: "Defining measurable, honest success criteria — North Star, secondary, leading, guardrail, and anti-metrics — for a product initiative"
tags: [Production, Metrics, Planning]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "3 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Success Metrics

This skill defines the metrics framework that tells the team whether the initiative actually worked — not merely whether it shipped. Every metric must be measurable with existing or buildable instrumentation.

### Core Capability

Given the problem statement, the requirements summary, and the user personas as context, this skill derives a North Star metric, supporting secondary metrics, leading indicators, guardrail metrics, and anti-metrics, each with a baseline, target, measurement method, and review cadence.

### Method

1. **North Star:** Choose the single metric that best reflects delivered value, is influenceable by the team, and moves within a reasonable timeframe.
2. **Support and safety:** Add secondary metrics and leading indicators that diagnose the North Star, plus guardrails that must not degrade and anti-metrics the team must not optimise for.
3. **Instrument:** Summarise the events, dashboards, and feedback mechanisms required to measure the framework.

### Output Structure

Each metric category under a clear heading, followed by a summary table listing every metric with its type, baseline, and target. This artefact feeds the PRD assembly stage.
