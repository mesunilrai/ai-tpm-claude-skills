---
name: Project Status Analyzer
description: Analyze unstructured project or program updates from a Technical Program Management perspective and produce evidence-based health, schedule, risk, blocker, dependency, action, and leadership decision analysis.
---

# Project Status Analyzer

## Purpose

Analyze unstructured project or program updates from a Technical Program Management perspective.

Convert project information into an evidence-based assessment that helps a TPM understand:

- Current program health
- Schedule and critical-path concerns
- Risks and their priority
- Current blockers
- Dependencies
- Unknowns and assumptions
- Recommended next actions
- Decisions or escalations requiring leadership attention

The analysis must distinguish between confirmed facts, reasonable inferences, and unknown information.

## When to Use

Use this skill when the user provides project or program information and asks to:

- assess project or program health
- summarize project status
- identify risks
- identify blockers
- analyze dependencies
- assess schedule risk
- identify critical-path concerns
- recommend next actions
- identify decisions or escalations needed

## Analysis Process

Follow these steps in order.

### 1. Extract the Facts

Identify information explicitly stated in the input.

Examples:

- Milestones
- Dates
- Completion percentages
- Delays
- Team or vendor commitments
- Dependencies
- Issues
- Risks
- Decisions
- Resource constraints

Do not add facts that are not provided.

### 2. Identify Unknowns and Assumptions

Identify information that is important to the analysis but is not provided.

Examples:

- Whether two activities can run in parallel
- Whether a dependency is blocking another activity
- Whether a milestone date is fixed
- Whether a reported estimate includes contingency
- Whether an issue has an assigned owner

Do not silently convert unknown information into facts.

### 3. Assess Program Health

Classify overall program health as:

- Green — On track
- Amber — At risk
- Red — Critical

Base the classification on evidence from the input.

Explain the primary reasons for the classification.

If the available information is insufficient for a confident classification, state the limitation.

### 4. Analyze Schedule and Critical Path

Assess:

- Remaining time
- Remaining work
- Known lead times
- Milestone constraints
- Potential sequencing issues
- Available schedule buffer
- Activities that may affect the critical path

Clearly distinguish confirmed sequencing from assumed sequencing.

If parallel execution is possible but not confirmed, identify it as an unknown.

Do not calculate schedule buffer when the necessary information is missing.

### 5. Identify and Prioritize Risks

For each significant risk identify:

- Risk
- Evidence
- Potential impact
- Probability, if provided or reasonably assessed from evidence
- Priority
- Recommended mitigation

Use these priority levels:

- Critical
- High
- Medium
- Low

If probability or impact is not explicitly provided, clearly label the assessment as an inference rather than a confirmed fact.

Do not invent numerical risk scores unless the user provides a scoring framework.

### 6. Identify Blockers

List issues that are currently preventing progress or preventing a required milestone from being completed.

Distinguish blockers from risks:

- Blocker = currently preventing progress
- Risk = potential future problem

If an item may be a blocker but the evidence is insufficient, identify it as an uncertain blocker.

### 7. Analyze Dependencies

For each important dependency identify:

- Dependency
- Dependency owner, if known
- Required date, if known
- Impact if delayed
- Criticality
- Confidence

Use dependency confidence:

- Confirmed — explicitly stated
- Likely — strongly supported by the information
- Unknown — relationship is not established

Never present an inferred dependency as confirmed.

### 8. Identify Recommended Next Actions

Provide specific and actionable next steps.

Prioritize actions based on:

1. Critical-path impact
2. Schedule urgency
3. Risk severity
4. Dependency impact
5. Decision requirements

Where possible, identify the responsible team or owner if provided.

Do not invent owners.

### 9. Identify Leadership Attention

Identify decisions, escalations, or leadership interventions that may be required.

Examples:

- Date commitment decision
- Resource escalation
- Vendor escalation
- Scope trade-off
- Risk acceptance
- Dependency resolution
- Go/no-go decision

Only identify leadership attention when supported by the project information.

## Evidence Classification

When making important conclusions, distinguish:

### Confirmed

Directly stated or directly supported by the input.

### Inference

A reasonable conclusion derived from confirmed information.

### Unknown

Information required for a confident conclusion but not provided.

Never present an inference or unknown as a confirmed fact.

## Output Format

Return the analysis using the following sections.

### Executive Summary

Provide a concise summary of the current program situation.

Highlight the most important facts and the primary concern.

### Program Health

**Status:** Green / Amber / Red

**Reason:**

Explain the evidence supporting the classification.

### Schedule & Critical Path

Summarize:

- Remaining timeline
- Remaining work
- Known lead times
- Critical-path concerns
- Schedule buffer, if determinable
- Important sequencing assumptions

### Key Risks

Use a table:

| Priority | Risk | Evidence | Potential Impact | Mitigation |
|---|---|---|---|---|

Clearly distinguish evidence from inference.

### Blockers

List current blockers.

For each blocker include:

- Blocker
- Impact
- Owner, if known
- Required action

### Dependencies

Use a table:

| Dependency | Owner | Required Date | Impact | Confidence |
|---|---|---|---|---|

### Unknowns & Assumptions

List information that could materially change the assessment.

### Recommended Next Actions

Provide prioritized, actionable next steps.

Use:

1. **Immediate**
2. **Next**
3. **Follow-up**

### Leadership Attention

List decisions, escalations, or interventions requiring leadership attention.

If none are evident, state:

> No specific leadership intervention is evident from the available information.

## Rules

- Base the analysis only on information provided by the user.
- Do not invent facts, dates, owners, dependencies, commitments, or metrics.
- Clearly distinguish facts, inferences, and unknowns.
- Do not assume that two activities are sequential unless the input establishes that relationship.
- Do not assume that two activities can run in parallel unless the input establishes or strongly supports it.
- Do not invent probability or impact scores.
- Do not invent numerical risk scores.
- Do not convert risks into blockers without evidence that progress is currently prevented.
- If information is insufficient, explicitly state what is missing.
- Prefer concise, actionable analysis over lengthy narrative.
- Focus on information useful to a Technical Program Manager and program leadership.
