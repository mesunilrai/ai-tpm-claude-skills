---
name: Decision Intelligence & Executive Briefing
description: Convert unstructured program information into evidence-based decisions, trade-offs, recommendations, and audience-specific executive or TPM briefings.
---

# Decision Intelligence & Executive Briefing

## Purpose

Convert complex or unstructured program information into decision-ready analysis and concise communication for the appropriate audience.

The skill helps a TPM answer:

> **What decision is needed, why does it matter, what are the viable options and trade-offs, what does the evidence support, and how should this be communicated?**

It supports two connected workflows:

1. **Decision intelligence** — identify and structure decisions, options, trade-offs, evidence, uncertainty, and recommendations.
2. **Executive briefing** — communicate the same underlying facts appropriately to executives, engineering leadership, or working teams.

The skill is decision support. It does not make decisions on behalf of stakeholders.

## When to Use

Use this skill when the user asks to:

- identify decisions required from a program update
- analyze decision options and trade-offs
- prepare leadership decision material
- create an executive program brief
- summarize complex program information for leadership
- translate program information for different audiences
- prepare a concise decision memo
- recommend next steps based on program evidence

Do not use it as a generic writing assistant. The output must preserve evidence, uncertainty, and decision context.

## Core Principle: Preserve the Evidence

Separate:

### Confirmed

Explicitly provided information.

### Inference

A reasonable conclusion derived from the information.

### Unknown

Information that could materially affect the decision but is not provided.

### Recommendation

A proposed course of action based on available evidence.

### Decision

An explicit choice that requires an accountable decision-maker.

A recommendation is not a decision.

Do not manufacture certainty merely to make the briefing sound executive-ready.

## Analysis Process

### 1. Establish the Decision Context

Identify, when available:

- Program objective
- Current situation
- Problem or trigger
- Decision required
- Decision deadline
- Constraints
- Success criteria
- Stakeholders

If the actual decision is unclear, identify the likely decision context and state that it requires confirmation.

### 2. Separate Facts from Interpretation

Before evaluating options, identify the evidence supporting the decision.

For important claims, distinguish:

- Confirmed fact
- Inference
- Unknown

Do not allow an executive summary to turn an inference into a fact.

### 3. Identify the Decision

A good decision statement should describe a choice.

Weak:

> We have a vendor issue.

Better:

> Decide whether to maintain the launch date with a reduced scope or move the launch to protect full scope.

If no real choice exists, do not manufacture one.

### 4. Identify Viable Options

Identify options supported by the input.

Common categories include:

- Maintain current plan
- Change scope
- Change sequence
- Add capacity
- Accept risk
- Delay milestone
- Use workaround
- Phase rollout

Do not invent an option that requires unsupported technical or organizational assumptions.

If an option is only conceptual, label it as such.

### 5. Analyze Trade-offs

For each viable option, assess where evidence allows:

- Delivery impact
- Scope impact
- Technical impact
- Risk impact
- Customer impact
- Resource impact
- Operational impact
- Security/compliance impact
- Reversibility
- Dependencies

Use **Unknown** where the input does not support an assessment.

Do not assign numerical scores unless the user provides a scoring framework.

### 6. Assess the Recommendation

A recommendation should:

- Clearly state the preferred option.
- Explain the strongest evidence.
- Explain material trade-offs.
- Identify important assumptions.
- Identify what would change the recommendation.

If evidence is insufficient for a recommendation, say so and identify the minimum information needed.

### 7. Identify Decision Owner and Deadline

Capture these only when known.

If missing:

- Decision owner: **Unknown**
- Decision required by: **Unknown**

Do not invent executives, teams, or dates.

### 8. Identify Leadership Attention

Leadership attention is appropriate when there is:

- A material trade-off
- A cross-team conflict
- A significant delivery decision
- A resource decision
- A risk acceptance decision
- A scope decision
- An unresolved dependency threatening a milestone
- A decision beyond the TPM's authority

Do not escalate every risk or issue.

### 9. Choose the Audience

Use the audience requested by the user. If no audience is specified, default to **engineering leadership / executive audience** for a briefing, while preserving technical details only where decision-relevant.

Supported views:

#### Executive / VP Engineering

Focus on:

- Business or program outcome
- Current health
- Material risk
- Decisions required
- Trade-offs
- Recommendation
- Timing

Avoid unnecessary implementation detail.

#### Engineering Director / Engineering Leadership

Focus on:

- Technical implications
- Dependencies
- Delivery risk
- Resource implications
- Architecture/testing concerns
- Decisions and trade-offs

#### TPM / Working Team

Focus on:

- Actions
- Owners
- Dates
- Dependencies
- Open questions
- Follow-ups

### 10. Preserve Cross-Audience Consistency

Changing the audience must not change the underlying facts.

The executive version may be shorter, but it must not:

- Remove a material uncertainty
- Turn an inference into a fact
- Change the recommendation without explanation
- Hide a material trade-off

## Output Format

### Executive Summary

Provide a concise summary containing:

- Current situation
- Material impact
- Decision required
- Recommendation, if supported

### Decision Required

**Decision:**

**Why now:**

**Decision owner:**

**Decision required by:**

### Evidence

| Evidence | Classification | Relevance |
|---|---|---|

### Options & Trade-offs

| Option | Benefits | Trade-offs / Risks | Key Unknowns |
|---|---|---|---|

### Recommendation

State:

- Recommended option
- Evidence supporting it
- Material trade-offs
- Assumptions
- What could change the recommendation

### Risks & Dependencies

List only decision-relevant risks and dependencies.

### Actions

| Priority | Action | Owner | Due | Purpose |
|---|---|---|---|---|

Use **Unknown** for missing ownership or dates.

### Leadership Attention

Identify the specific decision or escalation required.

If none is evident:

> No specific leadership intervention is evident from the available information.

## Executive Briefing Format

When the user asks for an executive briefing, prefer:

### 1. Overall Status

One concise statement.

### 2. What Changed / What Matters

Up to three bullets.

### 3. Key Risks

Up to three material risks.

### 4. Decisions Required

Clearly state decisions and deadlines.

### 5. Recommendation

One concise recommendation supported by evidence.

### 6. Next Steps

The most important actions and owners where known.

Avoid turning every project detail into an executive bullet.

## Decision Quality Checks

Before finalizing, check:

- Is there actually a decision?
- Is the decision stated as a choice?
- Are options genuinely different?
- Are trade-offs visible?
- Is the recommendation evidence-based?
- Are important unknowns visible?
- Is the decision owner known or explicitly marked unknown?
- Is the deadline known or explicitly marked unknown?
- Is leadership attention warranted?
- Does the briefing preserve material uncertainty?

## Example

### Input

> The launch is four weeks away. Development is 80% complete. The vendor API issue may take one week to resolve. Security review has not started and normally takes two weeks. We do not know whether the API issue blocks the security review. The team wants to keep the launch date.

### Expected Reasoning

Confirmed:

- Four weeks remain.
- Development is 80% complete.
- Vendor issue may take one week.
- Security review has not started.
- Security review normally takes two weeks.
- Team preference is to maintain launch date.

Unknown:

- Whether the API issue blocks security review.
- Remaining development duration.
- Whether all activities can run in parallel.
- Whether the launch date is fixed.

Potential decision:

> Decide whether to maintain the launch date subject to defined scope/recovery conditions or move the launch if the unresolved dependency threatens required validation.

The Skill should not claim that the launch must move or that the API definitely blocks security review.

## Guardrails

- Do not invent decisions that do not exist.
- Do not invent options, owners, dates, commitments, metrics, or constraints.
- Do not turn recommendations into decisions.
- Do not hide material uncertainty for executive brevity.
- Do not fabricate business impact.
- Do not assign numerical option scores without a provided framework.
- Do not present an inferred trade-off as confirmed.
- Do not escalate every risk.
- Do not assume an executive is the decision owner.
- Do not change facts when changing audience.
- Do not manufacture a recommendation when evidence is insufficient.
- Use concise executive language without sacrificing accuracy.
- Keep the output useful for junior TPMs and experienced program leaders.
