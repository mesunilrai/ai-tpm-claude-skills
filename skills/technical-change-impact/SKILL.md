---
name: Technical Change Impact Analyzer
description: Analyze a proposed technical or product change across systems, integrations, teams, data, security, testing, dependencies, schedule, risks, and decisions.
---

# Technical Change Impact Analyzer

## Purpose

Analyze a proposed technical or product change from a Technical Program Management perspective and produce an evidence-based impact assessment.

The skill helps a TPM answer:

> **If we make this change, what else could be affected, what do we need to validate, and what decisions are required?**

The analysis should help identify impacts across:

- Systems and architecture
- Integrations and interfaces
- Teams and ownership
- Data and data flows
- Security and compliance
- Testing and validation
- Dependencies and sequencing
- Schedule and delivery
- Risks and mitigations
- Unknowns and assumptions
- Decisions and approvals

This is a decision-support workflow, not an automatic change-approval mechanism.

## When to Use

Use this skill when the user provides a proposed change and asks to:

- assess technical change impact
- perform impact analysis
- understand what could be affected by a change
- assess downstream or upstream impact
- identify teams or systems affected by a change
- assess integration or data impact
- assess security or testing implications
- understand schedule or delivery implications
- identify decisions required before implementing a change

Do not use this skill as a generic project-status analyzer. It should focus on the consequences of a **specific proposed change**.

## Core Principle: Evidence Before Assumption

The quality of the analysis depends on distinguishing what is known from what is inferred.

Classify information as:

### Confirmed

Explicitly stated in the user's input or directly supported by it.

### Inference

A reasonable conclusion derived from confirmed information.

### Unknown

Information that could materially change the impact assessment but is not provided.

Never present an inference or unknown as a confirmed impact.

## Analysis Process

### 1. Define the Change

Extract the proposed change as precisely as possible.

Identify, when available:

- Current state
- Proposed state
- Reason for the change
- Scope
- Target date
- Constraints
- Success criteria
- Explicitly affected components

If the change itself is ambiguous, state the ambiguity before analyzing downstream impacts.

Do not invent a technical implementation approach that the user did not provide.

### 2. Establish the Change Boundary

Determine what is explicitly in scope and what is not established.

Ask:

- What component is changing?
- What interface or behavior changes?
- What consumers depend on the current behavior?
- What data enters or leaves the changed component?
- What environments are affected?
- Is the change temporary, permanent, phased, or a migration?

If the boundary cannot be established, identify the missing information as an unknown.

### 3. Analyze System and Architecture Impact

Assess potential impact to:

- Applications
- Services
- Platforms
- Infrastructure
- APIs
- Interfaces
- Authentication/authorization
- Configuration
- Environments
- Operational processes

For each item, distinguish:

- Confirmed impact
- Likely impact
- Unknown impact

Do not assume a component is affected merely because it is nearby in an architecture.

### 4. Analyze Integration Impact

Identify upstream and downstream integrations that may be affected.

Consider:

- API contracts
- Authentication
- Payloads and schemas
- Event/message flows
- File interfaces
- Batch processes
- Error handling
- Retry behavior
- Version compatibility
- Backward compatibility

For each integration, identify whether the impact is confirmed, inferred, or unknown.

If the input does not identify integration relationships, do not fabricate them.

### 5. Analyze Team and Ownership Impact

Identify teams that may need to:

- Modify systems
- Review architecture
- Validate security
- Update integrations
- Test functionality
- Update documentation
- Support deployment
- Monitor production

Only name an owner when the user provides one or the ownership is directly established.

If a responsible team is not known, state **Owner unknown** rather than inventing one.

### 6. Analyze Data Impact

Assess potential impact to:

- Data sources
- Data consumers
- Data schemas
- Data transformations
- Data mappings
- Data quality
- Historical data
- Data migration
- Retention
- Reporting and analytics

Consider whether the change can alter:

- Data structure
- Data meaning
- Data availability
- Data lineage
- Data timing
- Data access

Do not assume that data is affected unless the change provides evidence for that conclusion.

### 7. Analyze Security and Compliance Impact

Consider potential impact to:

- Authentication
- Authorization
- Identity
- Secrets or credentials
- Network boundaries
- Encryption
- Sensitive data
- Audit logging
- Access controls
- Security testing
- Compliance requirements

Use cautious language when the specific security architecture is unknown.

For example:

> **Potential security impact:** The proposed authentication change may require security review; the exact review scope is not established by the input.

Do not label a security requirement as mandatory unless the input establishes it or an explicit organizational requirement is provided.

### 8. Analyze Testing and Validation Impact

Identify potential changes to:

- Unit testing
- Integration testing
- End-to-end testing
- Regression testing
- Performance testing
- Security testing
- Data validation
- User acceptance testing
- Production verification

Consider both newly introduced behavior and existing behavior that could regress.

Do not assume a specific test duration unless provided.

### 9. Analyze Dependencies and Sequencing

Identify dependencies required for the change to succeed.

Examples:

- API availability
- Environment readiness
- Security review
- Data migration
- Vendor delivery
- Team availability
- Architecture approval
- Test environment readiness

Classify each relationship as:

- **Confirmed** — explicitly stated
- **Likely** — strongly supported by the input
- **Unknown** — relationship has not been established

Do not assume dependencies are sequential.

Do not assume activities can run in parallel unless the input establishes or strongly supports it.

### 10. Analyze Schedule and Delivery Impact

Assess:

- Target date
- Required-by dates
- Implementation work
- Testing implications
- Dependencies
- Lead times
- Migration or rollout activities
- Potential schedule pressure

Separate:

**Known schedule facts** — directly stated.

**Potential schedule impact** — reasonable inference.

**Unknown schedule factors** — information required for a reliable assessment.

Do not calculate schedule buffer when required durations are missing.

Do not state that a change will delay a release unless the available evidence supports that conclusion.

### 11. Identify Risks

Identify risks introduced or increased by the proposed change.

For each significant risk provide:

- Risk statement
- Evidence
- Potential impact
- Priority
- Mitigation
- Trigger, if identifiable
- Contingency, if identifiable

Use:

- Critical
- High
- Medium
- Low

If priority is an inference, label it as such.

Do not invent numerical probability, impact, or risk scores.

Do not create risks simply to populate the output.

### 12. Identify Decisions Required

Identify decisions that may be needed before proceeding.

Examples:

- Scope decision
- Architecture decision
- Security approval
- Rollout strategy
- Migration approach
- Backward compatibility decision
- Resource decision
- Schedule decision
- Risk acceptance

Distinguish:

**Recommendation:** what the TPM believes should happen based on available evidence.

**Decision:** an explicit choice that requires an accountable decision-maker.

Do not invent a decision owner unless provided or clearly established.

### 13. Identify Unknowns and Validation Questions

List only unknowns that could materially change the impact assessment.

For each important unknown, provide a question that can resolve it.

Example:

**Unknown:** Whether existing clients depend on the current API contract.

**Validation question:** Which active consumers currently use the affected API version?

This section should be useful to a TPM preparing stakeholder discussions.

## Impact Classification

Use the following confidence categories:

### Confirmed Impact

The input explicitly establishes that the change affects the component or activity.

### Likely Impact

The impact is strongly supported by the information but is not explicitly confirmed.

### Unknown Impact

The relationship cannot be reliably determined from the available information.

Do not convert likely or unknown impact into confirmed impact.

## Output Format

Keep the output concise enough for a TPM or engineering leadership audience while providing enough detail to support decisions.

### Executive Summary

Provide 3–5 sentences covering:

- What is changing
- Most significant impact
- Most significant risk
- Most important unknown
- Overall recommendation or next step

### Change Definition

| Item | Assessment |
|---|---|
| Current State | |
| Proposed Change | |
| Reason | |
| Scope | |
| Target Date | |
| Constraints | |

Use **Not provided** rather than inventing missing information.

### Impact Summary

| Area | Impact | Confidence | Evidence / Rationale |
|---|---|---|---|
| Systems / Architecture | | | |
| Integrations | | | |
| Teams / Ownership | | | |
| Data | | | |
| Security / Compliance | | | |
| Testing | | | |
| Dependencies | | | |
| Schedule / Delivery | | | |

### Dependency & Sequencing Considerations

Identify important dependencies and whether their sequencing is confirmed, likely, or unknown.

### Key Risks

| Priority | Risk | Evidence | Impact | Mitigation |
|---|---|---|---|---|

### Decisions Required

For each decision:

- Decision
- Why it matters
- Options, if identifiable
- Recommendation, if evidence supports one
- Decision owner, if known
- Decision-by date, if known

### Unknowns & Validation Questions

| Unknown | Why It Matters | Validation Question |
|---|---|---|

### Recommended Next Actions

Prioritize actions as:

1. **Immediate validation**
2. **Pre-change actions**
3. **Implementation / testing actions**
4. **Follow-up**

Actions should be specific and actionable.

### Leadership Attention

Identify only the decisions, escalations, or trade-offs that warrant leadership attention based on the available evidence.

If none are evident, state:

> No specific leadership intervention is evident from the available information.

## Example

### Input

> We are replacing the current SAML-based authentication flow with OpenID Connect before the next release. The identity team will implement the new flow. No other project details are available.

### Expected Reasoning

The change itself is confirmed. The identity team ownership is confirmed. Potential impacts to authentication consumers, security review, testing, backward compatibility, rollout, and dependent applications are plausible but not confirmed.

The Skill should **not** claim that every consuming application must change, that security approval is mandatory, or that the release will slip.

Instead, it should identify these as areas requiring validation and provide targeted questions.

## Guardrails

- Base the analysis only on information provided by the user.
- Do not invent systems, integrations, teams, owners, dates, requirements, dependencies, commitments, or metrics.
- Preserve the user's terminology unless a stronger conclusion is directly supported.
- Do not describe an impact as confirmed when it is only likely or unknown.
- Do not assume technical architecture that the user has not provided.
- Do not assume downstream consumers exist without evidence.
- Do not assume a security or compliance requirement is mandatory without supporting evidence.
- Do not assume activities are sequential.
- Do not assume activities can run in parallel.
- Do not invent schedule durations or buffer calculations.
- Do not manufacture risks simply because a change is being proposed.
- Do not convert potential impact into a confirmed blocker.
- Do not invent decision owners.
- Do not provide implementation instructions unless the user explicitly asks for them; this skill is for impact analysis.
- Clearly distinguish confirmed information, inference, and unknowns.
- Keep the analysis decision-oriented and useful to both TPMs and engineering leadership.
- When information is insufficient, identify the minimum additional information needed to improve confidence.
