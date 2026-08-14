# AI TPM Claude Skills

Practical AI Skills for **Technical Program Management, engineering delivery, and leadership decision support** using Claude.

This portfolio explores how AI can augment TPM workflows beyond summarization—by analyzing program health, technical change impact, dependency chains, and delivery decisions while explicitly handling uncertainty.

## 🎯 What This Portfolio Demonstrates

The goal is to build a **small set of high-value, reusable AI TPM capabilities**, not a collection of shallow prompts.

Each capability is designed around a repeatable TPM workflow and evaluated for:

- Evidence adherence
- Reasoning quality
- Uncertainty handling
- Hallucination control
- Actionability
- Decision usefulness

## 🧩 Core Skills

### 1. Project Status Analyzer — MVP Complete ✅

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

The Skill explicitly distinguishes **confirmed facts, inferences, and unknowns**.

**[View Skill →](skills/project-status-analyzer/)** · **[View evaluation →](skills/project-status-analyzer/evaluation/test-cases.md)**

### 2. Technical Change Impact Analyzer — Built; Validation in Progress 🔄

**Question:** *If we make this change, what else could be affected?*

Analyzes proposed technical/product changes across:

- 🏗️ Systems and architecture
- 🔌 Integrations and interfaces
- 👥 Teams and ownership
- 🗄️ Data and data flows
- 🔐 Security and compliance
- 🧪 Testing and validation
- 🔗 Dependencies and sequencing
- 📅 Schedule and delivery
- ⚠️ Risks and mitigations
- ❓ Unknowns and validation questions
- ⚖️ Decisions and leadership attention

**[View Skill →](skills/technical-change-impact/)**

### 3. Dependency & Critical Path Intelligence — Built; Validation in Progress 🔄

**Question:** *What depends on what, where can failure propagate, and which dependencies may be critical?*

Analyzes:

- Upstream/downstream relationships
- Dependency chains
- Sequencing
- Critical-path candidates
- Cross-team and vendor dependencies
- Ownership gaps
- Date sensitivity
- Risk propagation
- Dependency validation actions

The Skill deliberately uses **critical-path candidate** when evidence is suggestive rather than claiming a confirmed critical path without sufficient evidence.

**[View Skill →](skills/dependency-critical-path-intelligence/)**

### 4. Decision Intelligence & Executive Briefing — Built; Validation in Progress 🔄

**Question:** *What decision is needed, what are the trade-offs, and how should leadership see it?*

Structures:

- Decision context
- Evidence
- Options
- Trade-offs
- Recommendations
- Unknowns
- Decision ownership and timing
- Leadership attention
- Audience-specific executive / engineering / TPM briefings

The underlying facts are preserved when the audience changes.

**[View Skill →](skills/decision-intelligence-executive-briefing/)**

## 🧠 Portfolio Architecture

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

## 🧪 Evaluation Approach

The portfolio treats **evaluation as part of AI development**.

```text
Define TPM Problem
        ↓
Design Skill
        ↓
Baseline Test
        ↓
Evaluate Output
        ↓
Identify Failure Mode
        ↓
Improve Instructions
        ↓
Retest
        ↓
Document Result
```

Evaluation dimensions include:

| Dimension | What is evaluated |
|---|---|
| Accuracy | Correct understanding of supplied information |
| Evidence adherence | Conclusions remain grounded in input |
| Hallucination control | No invented facts, owners, dates, dependencies or requirements |
| Completeness | Material impacts, risks and unknowns are identified |
| Reasoning quality | Conclusions are defensible from evidence |
| Uncertainty | Important unknowns remain visible |
| Actionability | Recommendations are usable by TPMs |
| Decision quality | Options and trade-offs are structured appropriately |
| Audience fit | Communication matches the intended audience |

**[View evaluation framework →](evaluation/framework.md)**

## 🏢 End-to-End Case Study

A synthetic **Enterprise Identity Modernization** program is used to evaluate the four Skills together.

The scenario includes:

- 10 applications in scope
- Identity modernization / OpenID Connect migration
- Remaining legacy authentication integration work
- External vendor dependency
- Security review
- End-to-end testing
- 8-week launch constraint
- Cross-team dependencies
- Material unknowns and leadership trade-offs

The case study is intentionally synthetic and contains no proprietary company information.

**[View program context →](case-study/program-context.md)** · **[View sample update →](case-study/sample-input.md)** · **[View end-to-end evaluation →](case-study/end-to-end-analysis.md)**

## 📌 Current Status

**Portfolio V1 structure:** Complete  
**Skills:** 4 core capabilities built  
**Validation:** In progress; consolidated testing will be performed against the shared case study  
**Next:** Refine only where testing identifies a meaningful weakness

## 🚧 Why Only Four Skills?

The portfolio intentionally prioritizes **depth over quantity**.

The target is to demonstrate that AI can support the TPM lifecycle from:

> **Understand → Assess → Analyze Change → Trace Dependencies → Decide → Communicate**

Additional Skills will only be added if they provide materially different TPM value.

## 👤 About

Built as a practical **AI + Technical Program Management portfolio** exploring how AI can augment program management workflows and engineering decision support.

The examples use synthetic project scenarios and do not contain proprietary company information.

## 📚 Skill Authoring Reference

The Skills follow Anthropic's current custom Skill guidance: focused workflows, required `name` and `description` metadata, explicit usage guidance, examples, guardrails, and incremental testing. See the [Anthropic Skill authoring guide](https://support.claude.com/en/articles/12512198-how-to-create-custom-skills) for the platform reference.

## License

Released under the MIT License. See [LICENSE](LICENSE).
