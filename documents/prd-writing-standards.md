---
type: document
id: prd-writing-standards
title: PRD Writing Standards
description: "Internal standards and conventions for writing product requirements documents"
tags: [Production, Customer-Facing, planning:product, design:product]
connections:
  - target: prd-reference-guide
    type: references
metadata:
  document_type: "standards"
  audience: "product-managers"
---

## PRD Writing Standards

This document defines the writing standards and conventions that all PRDs produced through this pipeline must follow. Consistent standards ensure that PRDs are readable, reviewable, and actionable regardless of who writes them.

### Language Standards

**Voice:** Use active voice throughout. "The system displays a confirmation message" not "A confirmation message is displayed by the system."

**Tense:** Use present tense for requirements ("The system validates email format") and future tense for outcomes and metrics ("Adoption will be measured monthly").

**Precision:** Replace vague language with specific, measurable statements:

| Instead of | Write |
|-----------|-------|
| "The system should be fast" | "The system responds within 200ms at the 95th percentile" |
| "Users can easily find..." | "Users can reach [feature] within 2 clicks from the dashboard" |
| "The system handles errors gracefully" | "When [specific error] occurs, the system displays [specific message] and logs the error to [specific location]" |
| "The feature works on mobile" | "The feature is fully functional on iOS 15+ and Android 12+ in portrait orientation" |
| "Large datasets" | "Datasets containing up to 100,000 records" |

**Terminology:** Use consistent terminology throughout the document. If you call it "workspace" in one section, do not call it "project" in another. Define all domain terms in the glossary.

**Audience awareness:** Write for a mixed audience. Product managers, engineers, designers, and executives will all read this document. Technical details should be in clearly labelled sections. The executive summary should contain no jargon.

### Structural Standards

**Heading hierarchy:**
- H1: Document title (used once)
- H2: Major sections (Problem Statement, Requirements, Metrics, etc.)
- H3: Subsections within major sections
- H4: Individual items within subsections (use sparingly)

**Requirement formatting:**
```
[REQ-XXX] Requirement Title
Description: What the system must do (one sentence)
Priority: Must Have / Should Have / Could Have / Won't Have
Acceptance Criteria:
  - Criterion 1 (testable, specific)
  - Criterion 2
Dependencies: REQ-YYY, REQ-ZZZ (or "None")
```

**Tables:** Use tables for structured comparisons, requirement summaries, and metric definitions. Tables are easier to scan than bullet lists for comparative data.

**Bullet lists:** Use for unordered items, feature descriptions, and constraint lists. Each bullet should be one complete thought.

**Numbered lists:** Use for sequences, prioritised items, and process steps.

### Requirements Writing Rules

1. **One requirement, one statement.** If a requirement contains "and", consider splitting it into two requirements.

2. **Observable outcomes only.** Every requirement must describe something a user can see, an engineer can test, or an analyst can measure. "The system is secure" is not a requirement. "The system encrypts user passwords using bcrypt with a minimum cost factor of 12" is.

3. **Solution-agnostic requirements.** Describe what the system must do, not how it should be built. "The system exports user data" is a requirement. "The system uses a React component with a Material UI dropdown to trigger a CSV export via a REST API endpoint" is an implementation specification.

4. **Avoid modal verbs confusion.** Use "must" for Must Have requirements. Use "should" for Should Have. Use "may" for Could Have. Do not use "shall" (legacy formal language) or "can" (ambiguous between ability and permission).

5. **Quantify everything.** Time durations, data volumes, user counts, response times, file sizes — if it can be quantified, quantify it. Unquantified requirements are unverifiable.

### Metric Standards

**Every metric must include:**
- A precise definition (exactly what is counted or measured)
- A measurement method (how the data is collected)
- A baseline (current value or "To be established")
- A target (specific value with a timeframe)
- A review cadence (how often it is checked)

**Metric naming conventions:**
- Use descriptive names, not abbreviations ("Feature Activation Rate" not "FAR")
- Qualify metrics with context ("7-Day Retention Rate" not "Retention Rate")
- Avoid misleading names (do not call something a "Conversion Rate" if it measures something other than conversion)

### Review Standards

**Self-review checklist (before requesting review):**
- All sections are complete (no "TBD" or placeholder content)
- All requirement IDs are unique and sequential
- All cross-references (requirement dependencies, persona references) resolve to actual items
- The executive summary accurately reflects the document body
- The glossary defines all domain-specific terms used in the document
- Spelling and grammar have been checked
- Tables render correctly

**Peer review expectations:**
- Reviewers should focus on substance (are the requirements right?) not style (wording preferences)
- Feedback should be specific ("REQ-005 is ambiguous because..." not "some requirements are vague")
- Blocking feedback (must be addressed before approval) should be clearly distinguished from suggestions (nice to have improvements)
