---
name: Project Status Analyzer
description: Analyze unstructured project or program updates from a Technical Program Management perspective and produce evidence-based health, schedule, risk, blocker, dependency, action, and leadership decision analysis.
---

# Project Status Analyzer

## Purpose

Analyze unstructured project or program updates from a Technical Program Management perspective.

Convert project information into a concise, evidence-based assessment that helps a TPM and program leadership understand:

- Current program health
- Schedule and critical-path concerns
- Risks and their priority
- Current blockers
- Dependencies
- Unknowns and assumptions
- Recommended next actions
- Leadership decisions or escalations

The analysis must clearly distinguish confirmed information from inference and unknown information.

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
- identify decisions or escalations

## Analysis Process

Follow these steps.

### 1. Extract Confirmed Facts

Identify information explicitly stated in the input.

Examples:

- Milestones
- Dates
- Completion percentages
- Delays
- Lead times
- Team or vendor commitments
- Dependencies
- Issues
- Risks
- Decisions
- Resource constraints

Do not add facts that are not provided.

Preserve the terminology used by the user.

Do not strengthen or reinterpret a statement beyond what the input supports.

For example:

- "Security review has not started" does not automatically mean "security review is a mandatory launch gate."
- "Vendor issue exists" does not automatically mean "vendor issue is blocking the project."

### 2. Identify Inferences and Unknowns

Identify conclusions that can reasonably be derived from the facts.

Clearly label these as inferences.

Also identify information that is important to the assessment but is not provided.

Examples:

- Whether activities can run in parallel
- Whether a dependency is blocking another activity
- Whether a milestone date is fixed
- Whether an estimate includes contingency
- Whether an issue has an assigned owner
- Whether an issue affects the critical path

Never present an inference or unknown as a confirmed fact.

### 3. Assess Program Health

Classify overall program health as:

- Green — On track
- Amber — At risk
- Red — Critical

Base the classification on evidence from the input.

Also provide:

**Assessment confidence:** High / Medium / Low

Use confidence to indicate how complete and reliable the available information is.

Do not change the health classification merely because information is missing. Instead, state what missing information could change the assessment.

### 4. Analyze Schedule and Critical Path

Assess:

- Remaining timeline
- Remaining work
- Known lead times
- Milestone constraints
- Potential sequencing issues
- Schedule buffer, if determinable
- Activities that may affect the critical path

Separate:

**Known timeline:** directly stated facts.

**Potential schedule impact:** reasonable inference from those facts.

**Unknown sequencing:** relationships between activities that have not been established.

Do not assume that activities are sequential unless the input establishes that relationship.

Do not assume that activities can run in parallel unless the input establishes or strongly supports it.

Do not calculate schedule buffer when the required information is missing.

### 5. Identify and Prioritize Risks

For each significant risk identify:

- Risk
- Evidence
- Potential impact
- Probability, if available
- Priority
- Recommended mitigation

Use:

- Critical
- High
- Medium
- Low

When probability or impact is not explicitly provided, assess it only when there is sufficient evidence and clearly label the assessment as an inference.

Do not invent numerical risk scores.

Do not automatically classify a risk as Critical or High simply because it sounds important.

Priority should reflect the evidence, potential impact, urgency, and relationship to the schedule or critical path.

### 6. Identify Blockers

A blocker is an issue that is currently preventing progress or preventing a required activity from proceeding.

Distinguish:

- Blocker — currently preventing progress
- Risk — potential future problem
- Issue — problem that exists but may not currently block progress

If an item may be a blocker but the evidence is insufficient, label it as an uncertain blocker.

Do not convert every risk or issue into a blocker.

### 7. Analyze Dependencies

For each important dependency identify:

- Dependency
- Owner, if known
- Required date, if known
- Impact if delayed
- Criticality
- Confidence

Use:

- Confirmed — explicitly stated
- Likely — strongly supported by the information
- Unknown — relationship has not been established

Never present an inferred dependency as confirmed.

### 8. Identify Recommended Next Actions

Provide specific and actionable next steps.

Prioritize actions based on:

1. Critical-path impact
2. Schedule urgency
3. Risk severity
4. Dependency impact
5. Decision requirements

Identify the responsible owner or team only when provided or clearly established.

Do not invent owners.

Each action should answer:

- What needs to happen?
- Why is it important?
- Who should act, if known?
- When should it happen, if determinable?

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

Distinguish between:

**Action:** something the TPM/team can execute.

**Decision:** something requiring an explicit choice or approval.

Only identify leadership attention when supported by the project information.

If none is evident, state:

> No specific leadership intervention is evident from the available information.

## Evidence Classification

Use these categories internally and when useful in the output:

### Confirmed

Directly stated or directly supported by the input.

### Inference

A reasonable conclusion derived from confirmed information.

### Unknown

Information required for a confident conclusion but not provided.

Never present an inference or unknown as a confirmed fact.

## Output Format

Keep the response concise enough for a TPM or program leadership audience.

### Executive Summary

Provide 2–4 concise sentences covering:

- Current situation
- Most important concern
- Overall implication

### Program Health

**Status:** Green / Amber / Red

**Assessment confidence:** High / Medium / Low

**Reason:** Brief evidence-based explanation.

### Schedule & Critical Path

Include:

- Remaining timeline
- Remaining work
- Known lead times
- Critical-path concerns
- Schedule buffer, if determinable
- Key sequencing assumptions or unknowns

### Key Risks

Use:

| Priority | Risk | Evidence | Potential Impact | Mitigation |
|---|---|---|---|---|

### Blockers & Issues

Separate confirmed blockers from other issues.

For each important item include:

- Item
- Current impact
- Owner, if known
- Required action

### Dependencies

Use:

| Dependency | Owner | Required Date | Impact | Confidence |
|---|---|---|---|---|

### Unknowns & Assumptions

List only unknowns that could materially change the assessment.

Do not create unnecessary unknowns.

### Recommended Next Actions

Prioritize:

1. **Immediate**
2. **Next**
3. **Follow-up**

Keep actions specific and actionable.

### Leadership Attention

List:

- Decisions required
- Escalations required
- Leadership visibility needed

Do not manufacture leadership actions when none are supported.

## Rules

- Base the analysis only on information provided by the user.
- Do not invent facts, dates, owners, dependencies, commitments, metrics, or decisions.
- Preserve the user's terminology unless a stronger conclusion is directly supported.
- Do not describe something as mandatory, required, committed, launch-blocking, or critical unless supported by the input.
- Clearly distinguish confirmed facts, inferences, and unknowns.
- Do not assume activities are sequential.
- Do not assume activities can run in parallel.
- Do not invent probability, impact, or numerical risk scores.
- Do not convert risks into blockers without evidence that progress is currently prevented.
- Do not confuse an issue with a blocker.
- Do not invent owners.
- Do not overstate schedule certainty.
- If information is insufficient, explicitly state what is missing and how it could affect the assessment.
- Keep the analysis concise and decision-oriented.
- Focus on information useful to a Technical Program Manager and program leadership.
