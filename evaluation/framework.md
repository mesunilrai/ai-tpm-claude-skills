# AI TPM Skills — Evaluation Framework

## Purpose

Provide a reusable evaluation approach for assessing whether AI TPM Skills produce useful, accurate, evidence-based and decision-oriented outputs.

The framework is designed to evaluate **reasoning quality**, not merely whether the output looks well formatted.

## Evaluation Dimensions

| Dimension | Question |
|---|---|
| Accuracy | Did the Skill correctly understand the provided information? |
| Evidence adherence | Did it stay grounded in the supplied facts? |
| Hallucination control | Did it invent facts, owners, dates, dependencies, metrics or requirements? |
| Completeness | Did it identify the material information relevant to the task? |
| Reasoning quality | Are conclusions defensible from the evidence? |
| Uncertainty handling | Did it clearly identify important unknowns and assumptions? |
| Actionability | Can a TPM actually use the recommended actions? |
| Decision quality | Are decisions, options and trade-offs clearly structured when relevant? |
| Consistency | Does the Skill behave consistently across similar scenarios? |
| Format adherence | Does it follow the intended output structure without sacrificing substance? |
| Audience fit | Is the communication appropriate for the intended TPM or leadership audience? |

## Test Design

Each Skill should be tested with a small set of deliberately different scenarios rather than many nearly identical prompts.

At minimum, include:

1. **Healthy / low-risk scenario** — tests whether the Skill avoids manufacturing problems.
2. **Ambiguous scenario** — tests uncertainty handling.
3. **High-risk / constrained scenario** — tests prioritization and escalation.
4. **Missing-information scenario** — tests whether the Skill asks for or identifies material gaps.

Where appropriate, add a domain-specific edge case.

## Expected Behavior

Before running a test, define what a good response should do.

Expected behavior should describe:

- Facts that must be preserved
- Conclusions that are reasonable
- Assumptions that must remain explicit
- Important unknowns
- Risks or dependencies that should be identified
- Actions or decisions that should be surfaced
- Things the Skill must **not** claim

This prevents evaluating an AI response only after seeing the answer.

## Pass / Fail Standard

A test passes when the output:

- Preserves material facts.
- Does not introduce material unsupported facts.
- Makes important inference boundaries visible.
- Identifies material unknowns.
- Produces conclusions proportionate to the evidence.
- Provides useful actions or decisions when appropriate.
- Avoids unnecessary alarm or manufactured risk.

A test fails when the output contains a material reasoning error, such as:

- Invented dependency
- Invented owner or date
- Unsupported critical-path claim
- Unsupported mandatory requirement
- Incorrect health classification
- Treating an issue as a confirmed blocker without evidence
- Hiding a material uncertainty
- Recommending an action that depends on an unsupported assumption

## Severity of Findings

### Critical

The error could materially change a program decision, launch decision, risk posture, or executive understanding.

### High

The error could materially mislead a TPM or stakeholder but is unlikely to independently change the overall decision.

### Medium

The output is materially incomplete, imprecise, or less useful but the main conclusion remains defensible.

### Low

Minor wording, formatting, or non-material completeness issue.

## Iterative Improvement Loop

Use the following development loop for each Skill:

```text
Design
  ↓
Baseline Test
  ↓
Evaluate
  ↓
Identify Failure Mode
  ↓
Change Skill Instructions
  ↓
Retest
  ↓
Compare
  ↓
Document
```

A change should be made because a test exposed a meaningful weakness—not simply because another wording variation seems preferable.

## Evaluation Record

For each tested scenario capture:

### Test Case

- Scenario
- Input
- Expected behavior

### Result

- Actual behavior
- Pass / Fail
- Findings
- Severity

### Improvement

- Failure mode
- Instruction change
- Retest result

## Quality Bar

The objective is not to make the AI sound confident.

The objective is to make it **usefully accurate, appropriately uncertain, and actionable**.

A strong AI TPM Skill should behave like a disciplined second pair of eyes for a TPM—not like an autonomous decision-maker.
