---
name: Dependency & Critical Path Intelligence
description: Analyze program dependencies, sequencing, dependency chains, critical-path candidates, ownership gaps, and risk propagation from unstructured TPM updates.
---

# Dependency & Critical Path Intelligence

## Purpose

Analyze a program's dependency network and identify which relationships, dates, owners, or sequencing constraints could materially affect delivery.

The skill helps a TPM answer:

> **What depends on what, which dependencies matter most, where can failure propagate, and what should we validate or act on next?**

This is deeper than a simple dependency list. It focuses on relationships, sequencing, critical-path candidates, and propagation of delivery risk.

## When to Use

Use this skill when the user asks to:

- analyze project or program dependencies
- identify critical dependencies
- identify critical path candidates
- analyze upstream/downstream relationships
- understand dependency chains
- identify cross-team or vendor dependencies
- identify dependency ownership gaps
- assess dependency risk propagation
- analyze sequencing constraints
- find potential schedule bottlenecks

Do not use this skill merely to summarize a status update. It should focus specifically on **relationships between work, systems, teams, milestones, or external parties**.

## Core Principle: Do Not Invent the Network

Dependency analysis is particularly vulnerable to false certainty.

Use three evidence levels:

### Confirmed

The dependency or relationship is explicitly stated.

### Likely

The relationship is strongly supported by the provided information but is not explicitly confirmed.

### Unknown

The relationship cannot be reliably established from the available information.

Never convert a likely or unknown relationship into a confirmed dependency.

## Analysis Process

### 1. Extract Dependency Nodes

Identify relevant nodes such as:

- Teams
- Systems
- Components
- Vendors
- Deliverables
- Milestones
- Approvals
- Environments
- Data activities
- Testing activities
- Release activities

Do not create nodes that are not supported by the input.

### 2. Extract Relationships

For each dependency, identify where possible:

- Upstream node
- Downstream node
- Dependency type
- Required outcome
- Required-by date
- Owner
- Evidence
- Confidence

Useful dependency types include:

- Technical
- Data
- Resource
- Vendor
- Approval
- Environment
- Security
- Testing
- Schedule
- External

### 3. Identify Dependency Chains

Look for sequences such as:

`A → B → C → D`

where completion or availability of one node affects another.

For each chain, determine:

- Which relationships are confirmed
- Which are inferred
- Which links are unknown
- Where delays could propagate

Do not assume that all nodes in a sequence are on the critical path.

### 4. Analyze Sequencing

Determine whether activities are:

- Confirmed sequential
- Confirmed parallel
- Potentially parallel
- Sequencing unknown

Do not infer sequencing simply because two activities appear in a particular order in the user's text.

Example:

> Security review is planned and vendor testing is pending.

This does **not** establish whether security review must wait for vendor testing.

The correct assessment may be:

> Sequencing between security review and vendor testing is unknown.

### 5. Identify Critical-Path Candidates

A dependency can be a **critical-path candidate** when the available evidence suggests that:

- It gates a required milestone.
- There is little or no apparent schedule flexibility.
- Downstream work cannot proceed without it.
- It has a long lead time relative to available runway.
- Failure would materially affect the target date.

Use the phrase **critical-path candidate** unless the actual critical path is explicitly established by a schedule or authoritative project plan.

Do not claim a dependency is on the confirmed critical path without sufficient evidence.

### 6. Assess Dependency Criticality

Use:

- **Critical** — strong evidence that failure directly threatens a required milestone or delivery constraint.
- **High** — significant downstream impact is supported, but criticality is not fully established.
- **Medium** — meaningful impact is possible but alternatives or timing flexibility appear available.
- **Low** — limited delivery impact based on current information.
- **Unknown** — insufficient information to determine criticality.

These are analytical classifications, not numerical scores.

### 7. Analyze Risk Propagation

For important chains, ask:

> If this dependency fails, what downstream work could be affected?

Identify propagation such as:

`Vendor API → Integration Testing → UAT → Release`

The analysis must distinguish:

- Confirmed downstream impact
- Likely downstream impact
- Unknown downstream impact

Do not assume every downstream activity will be delayed.

### 8. Analyze Ownership

Identify dependency ownership only when provided.

For each dependency, capture:

- Dependency owner
- Dependent owner
- Decision owner, if relevant
- Escalation path, if known

If ownership is missing:

> **Owner: Unknown**

Do not invent organizational teams or names.

### 9. Analyze Date Sensitivity

For each material dependency, consider:

- Required-by date
- Supplier/producer delivery date
- Downstream start date
- Remaining runway
- Lead time
- Slack/buffer, only if calculable from provided dates

Do not calculate schedule slack when the required dates are missing.

Do not call a dependency late unless the input establishes that it has missed a required date.

### 10. Identify Dependency Gaps

Look for missing information that prevents reliable dependency analysis, including:

- Missing owner
- Missing required-by date
- Missing producer commitment
- Missing downstream milestone
- Unknown sequencing
- Unknown consumer
- Unknown workaround
- Unknown acceptance criteria

Prioritize unknowns that could change the delivery assessment.

### 11. Recommend Actions

Actions should focus on reducing dependency uncertainty or protecting the delivery path.

Examples:

- Confirm dependency owner.
- Confirm required-by date.
- Validate whether the dependency gates downstream work.
- Establish a fallback or workaround.
- Confirm vendor commitment.
- Validate whether work can proceed in parallel.
- Add a checkpoint before a date-sensitive dependency becomes critical.
- Escalate an unresolved critical dependency.

## Output Format

### Executive Summary

Provide a concise summary of:

- Most important dependency
- Most important chain
- Critical-path candidate(s)
- Biggest unknown
- Recommended immediate action

### Dependency Map

| Upstream | Downstream | Dependency | Confidence | Criticality | Owner | Required By |
|---|---|---|---|---|---|---|

Use **Unknown** rather than inventing missing information.

### Dependency Chains

Represent important chains in a simple form:

`A → B → C → D`

For each chain, explain where risk could propagate.

### Critical-Path Candidates

For each candidate:

- Dependency
- Evidence
- Why it may be critical
- What remains unknown
- Validation required

### Risk Propagation

| Dependency Failure | Potential Downstream Impact | Confidence |
|---|---|---|

### Ownership Gaps

List dependencies without a confirmed owner when ownership matters.

### Date & Sequencing Concerns

Identify required-by dates, lead times, and sequencing constraints supported by the input.

### Recommended Actions

Prioritize:

1. Critical dependency validation
2. Date/owner confirmation
3. Dependency protection or mitigation
4. Escalation or decision
5. Follow-up monitoring

### Leadership Attention

Identify only dependency decisions or escalations that require leadership attention.

If none are evident:

> No specific leadership intervention is evident from the available dependency information.

## Example

### Input

> The vendor API is expected next week. The integration team needs the API for testing. Security review is also planned before launch, but we have not confirmed whether the API is required for the security review. Launch is in four weeks.

### Expected Reasoning

Confirmed:

- Vendor API expected next week.
- Integration team needs the API for testing.
- Security review is planned.
- Launch is in four weeks.

Likely:

- Vendor API availability is important to the integration testing path.

Unknown:

- Whether the API gates security review.
- Exact integration testing duration.
- Whether the vendor date is a firm commitment.
- Whether a workaround exists.

The Skill should identify the vendor API as a **critical-path candidate**, not automatically state that it is definitively on the critical path.

## Guardrails

- Do not invent dependencies.
- Do not invent owners, dates, milestones, systems, teams, or commitments.
- Do not claim an item is on the confirmed critical path without sufficient evidence.
- Prefer **critical-path candidate** when the evidence is suggestive but incomplete.
- Do not assume sequential execution.
- Do not assume parallel execution.
- Do not assume a dependency failure automatically causes a downstream delay.
- Do not calculate buffer or slack without sufficient dates.
- Do not assign unsupported numerical scores.
- Clearly separate confirmed, likely, and unknown relationships.
- Do not create escalation recommendations merely because a dependency exists.
- Focus on dependencies that materially affect delivery, decisions, or risk.
- Keep the output useful for both junior TPMs and experienced program leaders.
