---
type: prompt
id: user-persona-generator
title: User Persona Generator
description: "Generate detailed user personas from research data and product context using the persona card template"
tags: [Production]
connections:
  - target: stakeholder-analysis
    type: derived_from
  - target: requirements-prompt
    type: uses
  - target: persona-card-template
    type: references
metadata:
  estimated_duration: "4 minutes"
  avg_tokens: 3000
  trigger: manual
---

## User Persona Generator

You are a product strategist creating user personas that will drive requirements decisions throughout a PRD. Your personas must be realistic, specific, and grounded in actual user behaviour — not aspirational stereotypes.

### Input

**Problem statement:** {{steps.problem-statement-writer.output}}

**Product description:** {{input.initiative_description}}

**Available user research:** {{input.customer_evidence}}

**Known user segments:** Infer user segments from the initiative description and {{steps.problem-statement-writer.output}}.

### Instructions

Generate user personas that represent the key user types for this product initiative. Use the persona-card-template format for each persona.

**Persona Types to Create**

1. **Primary Persona:** The person whose needs this initiative primarily serves. There should be exactly one primary persona. This is the person you optimise for when design trade-offs arise.

2. **Secondary Personas (1-2):** People who interact with the feature or are affected by it, but whose needs are secondary to the primary persona. These personas help identify edge cases and integration requirements.

3. **Anti-Persona (1):** A person who this initiative is explicitly NOT designed for. Defining the anti-persona prevents scope creep by making it clear whose requests should be deferred to a different initiative.

**For Each Persona, Provide:**

**Demographics and Context**
- Name (fictional but realistic)
- Job title and company context (company size, industry)
- Years of experience in their role
- Technical proficiency level (Novice, Intermediate, Advanced, Expert)
- Key tools in their daily workflow (what software they use regularly)

**Goals and Motivations**
- Primary goal: What they are trying to achieve that relates to this initiative (one sentence)
- Secondary goals: 2-3 other objectives that influence how they interact with the product
- What success looks like for them: How they would know the initiative has helped them
- Underlying motivation: The deeper "why" behind their goals (career advancement, reducing stress, serving their customers better)

**Frustrations and Pain Points**
- Current pain: 3-4 specific frustrations related to the problem statement
- Workarounds: What they currently do to work around these frustrations
- Cost of the status quo: How much time, money, or effort their workarounds cost
- Emotional dimension: How the problem makes them feel (frustrated, anxious, embarrassed)

**Behaviour Patterns**
- Frequency of interaction: How often they would use this feature (daily, weekly, monthly)
- Context of use: When and where they typically work (office, remote, mobile, in meetings)
- Decision-making style: Do they explore options or follow established patterns?
- Adoption pattern: Are they an early adopter, pragmatist, or sceptic?

**Relationship to the Problem**
- How directly they experience the problem described in the problem statement
- What would change for them if the problem were solved
- What their ideal solution would look like (in their words, not product language)

**Quotes**

For each persona, write 2-3 realistic quotes that capture their perspective:
- One about their current frustration
- One about what they wish existed
- One about what matters most to them in a solution

These quotes should sound like things a real person would say in an interview, not marketing copy.

**Anti-Persona Specifics**

For the anti-persona, explain:
- Why they are excluded (their needs are fundamentally different, serving them would compromise the primary persona's experience, or their use case is better served by a different initiative)
- How requests from this persona should be handled (redirect to another initiative, defer to a future phase, or explicitly decline)

### Output Format

Present each persona using the persona-card-template structure. Lead with the primary persona, then secondary personas, then the anti-persona. Include a one-paragraph summary at the top explaining how the personas relate to each other and to the problem statement.
