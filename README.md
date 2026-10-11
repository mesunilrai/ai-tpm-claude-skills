# AI TPM Claude Skills

Practical AI Skills for **Technical Program Management, engineering delivery, and leadership decision support** using Claude.

This portfolio explores how AI can augment TPM workflows beyond summarization—by analyzing program health, technical change impact, dependency chains, and delivery decisions while explicitly handling uncertainty.

> **Portfolio focus:** reusable TPM workflows, evidence-grounded reasoning, and systematic evaluation—not a collection of shallow prompts.

## What This Portfolio Demonstrates

Each capability is designed around a repeatable TPM workflow and evaluated for:

- Evidence adherence and reasoning quality
- Uncertainty handling and hallucination control
- Completeness and actionability
- Decision usefulness and audience fit

## Core Skills

### 1. Project Status Analyzer — MVP Complete; consolidated validation pending

**Question:** *What is happening with the program, and where should the TPM focus?*

Analyzes unstructured program updates across:

- 🟢🟠🔴 Program health and assessment confidence
- 📅 Schedule and critical-path concerns
- ⚠️ Risks and prioritization
- 🚧 Blockers vs. issues
- 🔗 Dependencies
- ❓ Unknowns and assumptions
- 🎯 Recommended actions
- 👔 Leadership attention

The Skill distinguishes **confirmed facts, inferences, and unknowns**.

**[View Skill →](skills/project-status-analyzer/)** · **[View evaluation test cases →](skills/project-status-analyzer/evaluation/test-cases.md)**

### 2. Technical Change Impact Analyzer — Built; validation pending

**Question:** *If we make this change, what else could be affected?*

Analyzes proposed technical/product changes across systems, architecture, integrations, teams, data flows, security, testing, dependencies, schedule, risks, and decisions.

**[View Skill →](skills/technical-change-impact/)**

### 3. Dependency & Critical Path Intelligence — Built; validation pending

**Question:** *What depends on what, where can failure propagate, and which dependencies may be critical?*

Analyzes upstream/downstream relationships, dependency chains, sequencing, critical-path candidates, cross-team and vendor dependencies, ownership gaps, date sensitivity, and risk propagation.

The Skill uses **critical-path candidate** when evidence is suggestive rather than claiming a confirmed critical path without sufficient evidence.

**[View Skill →](skills/dependency-critical-path-intelligence/)**

### 4. Decision Intelligence & Executive Briefing — Built; validation pending

**Question:** *What decision is needed, what are the trade-offs, and how should leadership see it?*

Structures decision context, evidence, options, trade-offs, recommendations, unknowns, ownership and timing gaps, and audience-specific executive, engineering, and TPM briefings.

The underlying facts should remain consistent when the audience changes.

**[View Skill →](skills/decision-intelligence-executive-briefing/)**

## Quick Start

1. **Choose a Skill** from the links above based on the TPM problem you want to analyze.
2. **Review its instructions and supporting files** so you understand the intended inputs, workflow, and guardrails.
3. **Use it in a Claude environment that supports custom Skills.** Follow the platform's current instructions to install or enable the Skill; requirements may vary by environment.
4. **Provide a realistic, non-sensitive project update** with the relevant context, constraints, dates, dependencies, and known unknowns.
5. **Review the output critically.** Check material claims against your input, verify assumptions, and do not treat recommendations as confirmed facts.
6. **Capture failure cases and retest** after changing instructions.

Start with the [Project Status Analyzer](skills/project-status-analyzer/) and its [evaluation test cases](skills/project-status-analyzer/evaluation/test-cases.md). See Anthropic's [Skill authoring guidance](https://support.claude.com/en/articles/12512198-how-to-create-custom-skills) for platform-specific instructions.

## Illustrative Example

**Sample input**

> The program targets launch in eight weeks. Six of ten applications have migrated. One remaining application needs a legacy authentication change estimated at five business days, but the estimate is not yet validated. A vendor change is expected next week under a verbal commitment. Security review has not started and normally takes seven business days. The dependency between the vendor change and security review is unknown.

**What a useful analysis should surface**

- **Known facts:** 6 of 10 applications migrated; target launch in eight weeks; integration estimate is unvalidated.
- **Risks to investigate:** vendor commitment reliability, remaining integration readiness, and security-review timing.
- **Unknowns to preserve:** whether security review can start before the vendor change and whether these activities affect the confirmed critical path.
- **Next actions:** validate the integration estimate, confirm vendor delivery in writing, and ask Security to clarify review prerequisites and earliest start.

*This is an illustrative expected response, not a recorded execution result. The Skills have not yet been validated against this example.*

## Portfolio Architecture

```text
                 Unstructured Program Information
                              │
          ┌───────────────────┼───────────────────┐
          ↓                   ↓                   ↓
   Program Status        Change Impact       Dependency /
     Analysis             Analysis         Critical Path
          └───────────────────┼───────────────────┘
                              ↓
                 Decision Intelligence
                              ↓
                    Executive Briefing
                              │
                              ↓
                    Leadership Decision
```

The four Skills are intentionally complementary rather than four variations of the same prompt.

## Evaluation Approach

**Evaluation is part of AI development.** The intended cycle is:

```text
Define TPM Problem
        ↓
Design Skill
        ↓
Run Baseline Test
        ↓
Evaluate Actual Output
        ↓
Identify Failure Mode
        ↓
Improve Instructions
        ↓
Retest
        ↓
Document Evidence
```

Evaluation dimensions include:

| Dimension | What is evaluated |
|---|---|
| Accuracy | Correct understanding of supplied information |
| Evidence adherence | Conclusions remain grounded in input |
| Hallucination control | No invented facts, owners, dates, dependencies, or requirements |
| Completeness | Material impacts, risks, and unknowns are identified |
| Reasoning quality | Conclusions are defensible from evidence |
| Uncertainty | Important unknowns remain visible |
| Actionability | Recommendations are usable by TPMs |
| Decision quality | Options and trade-offs are structured appropriately |
| Audience fit | Communication matches the intended audience |

**[View evaluation framework →](evaluation/framework.md)**

## End-to-End Case Study

A synthetic **Enterprise Identity Modernization** program is used to evaluate the four Skills together. It includes 10 applications, an OpenID Connect migration, legacy authentication work, a vendor dependency, pending security review, end-to-end testing, an eight-week launch target, and material unknowns.

The scenario is synthetic and contains no proprietary company information.

- [Program context](case-study/program-context.md)
- [Sample program update](case-study/sample-input.md)
- [End-to-end evaluation plan](case-study/end-to-end-analysis.md)
- [Cross-skill validation scorecard](case-study/cross-skill-validation-scorecard.md)

## Current Status

- **Portfolio V1 structure:** Complete
- **Core Skills:** Four built
- **Validation:** Actual execution and consolidated review pending
- **Case study and scorecard:** Prepared for validation; results remain pending
- **Next:** Execute the Skills, record evidence, and improve only where testing identifies a meaningful weakness

“Built” describes implementation status; it does **not** mean the Skill has passed consolidated validation.

## Why Only Four Skills?

The portfolio prioritizes **depth over quantity**. The goal is to support the TPM lifecycle:

> **Understand → Assess → Analyze Change → Trace Dependencies → Decide → Communicate**

Additional Skills will be added only if they provide materially different TPM value.

## About

Built as a practical **AI + Technical Program Management portfolio** exploring how AI can augment program management workflows and engineering decision support.

The examples use synthetic project scenarios and do not contain proprietary company information.

## Skill Authoring Reference

The Skills follow Anthropic's custom Skill guidance: focused workflows, required `name` and `description` metadata, explicit usage guidance, examples, guardrails, and incremental testing. See the [Anthropic Skill authoring guide](https://support.claude.com/en/articles/12512198-how-to-create-custom-skills).

## License

Released under the MIT License. See [LICENSE](LICENSE).
