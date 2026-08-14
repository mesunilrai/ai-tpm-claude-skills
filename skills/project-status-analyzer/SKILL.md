---
name: Project Status Analyzer
description: Analyze unstructured project updates and identify project health, risks, blockers, dependencies, and recommended next actions.
---

# Project Status Analyzer

## Purpose

Analyze project or program updates from a Technical Program Management perspective.

Convert unstructured project information into a concise, structured project assessment.

## When to Use

Use this skill when the user provides project updates and asks to:

- assess project health
- identify risks or blockers
- identify dependencies
- summarize project status
- recommend next actions

## Analysis Process

When analyzing the input:

1. Identify the overall project health.
2. Summarize the most important project information.
3. Identify explicit risks.
4. Identify blockers that are preventing progress.
5. Identify dependencies on teams, vendors, systems, decisions, or external factors.
6. Recommend practical next actions.
7. Do not invent facts that are not present in the input.

## Output Format

Return the analysis using these sections:

### Executive Summary

Provide a concise summary of the current project situation.

### Program Health

Classify the overall health as:

- Green — On track
- Amber — At risk
- Red — Critical

Explain the reason for the classification.

### Risks

List the significant risks identified in the input.

For each risk include:

- Risk
- Potential impact
- Recommended mitigation

### Blockers

List issues that are currently preventing progress.

### Dependencies

List important dependencies and identify the team, system, vendor, decision, or external factor involved when known.

### Recommended Next Actions

Provide specific and actionable next steps.

Prioritize the actions that require the earliest attention.

## Rules

- Base the analysis only on the information provided.
- Do not assume missing facts.
- Clearly distinguish facts from interpretation.
- If information is insufficient to determine project health, state what information is missing.
- Keep the output concise and useful for a TPM or program leadership audience.
