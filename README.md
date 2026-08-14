# AI TPM Claude Skills

Practical AI Skills designed to support **Technical Program Management workflows** using Claude.

This repository demonstrates how AI can be applied to common TPM activities such as **program health assessment, risk analysis, dependency management, and decision support**.

---

## 🎯 Objective

Explore and build reusable AI Skills that help Technical Program Managers convert unstructured project information into **structured, evidence-based insights and actionable decisions**.

The focus is not only on generating AI output, but also on:

* Clear AI instruction design
* Evidence-based reasoning
* Handling uncertainty and missing information
* AI evaluation and test cases
* Iterative improvement
* Practical TPM use cases

---

## 🧩 Skills

### 1. Project Status Analyzer — MVP ✅

Analyzes unstructured project or program updates and produces:

* 🟢🟠🔴 Program Health
* 📅 Schedule & Critical Path Analysis
* ⚠️ Risk Identification & Prioritization
* 🚧 Blockers & Issues
* 🔗 Dependency Analysis
* ❓ Unknowns & Assumptions
* 🎯 Recommended Next Actions
* 👔 Leadership Attention

The Skill is designed to distinguish between **confirmed facts, reasonable inferences, and unknown information** rather than presenting assumptions as facts.

**[View Project Status Analyzer →](skills/project-status-analyzer/)**

### Evaluation

The Project Status Analyzer includes a structured evaluation suite covering:

* Green / healthy scenarios
* Amber / schedule-risk scenarios
* Red / critical-blocker scenarios
* Missing-information scenarios
* MVP acceptance criteria
* Known limitations

**[View Evaluation →](skills/project-status-analyzer/evaluation/test-cases.md)**

---

## 🧠 Development Approach

The Skills are developed iteratively:

```text
Define TPM Problem
       ↓
Design AI Skill
       ↓
Test with Realistic Scenarios
       ↓
Evaluate Output
       ↓
Identify Reasoning Gaps
       ↓
Improve Instructions
       ↓
Retest
       ↓
Document Results
```

The goal is to demonstrate **AI development and evaluation**, not simply prompt creation.

---

## 🔍 Example Capability

A typical project update such as:

> "Development is 80% complete, go-live is in 4 weeks, security review has a 2-week lead time, and a vendor API issue is unresolved."

can be transformed into structured TPM analysis covering:

**Health → Schedule → Risks → Blockers → Dependencies → Unknowns → Actions → Leadership Attention**

while explicitly identifying information that is not known.

---

## 📊 What This Demonstrates

This portfolio focuses on practical AI TPM capabilities including:

| Area                             | Demonstrated Capability                        |
| -------------------------------- | ---------------------------------------------- |
| AI Skills                        | Reusable AI workflow design                    |
| Prompt / Instruction Engineering | Structured behavioral instructions             |
| AI Evaluation                    | Scenario-based testing and acceptance criteria |
| Risk Management                  | Evidence-based risk analysis                   |
| Program Management               | Health, schedule and dependency analysis       |
| Decision Support                 | Action and leadership decision identification  |
| AI Reliability                   | Uncertainty and hallucination controls         |
| Iterative Development            | Test → evaluate → improve                      |

---

## 🚧 Roadmap

This repository will evolve into a broader **AI TPM toolkit**.

Planned capabilities include:

* [x] Risk Analyzer
* [ ] Dependency Analyzer
* [ ] RAID Analysis
* [ ] Executive Status Report Generator
* [ ] AI evaluation and benchmarking
* [ ] Automated Skill packaging
* [ ] AI-powered Program Intelligence prototype

The roadmap is intentionally incremental, with each capability tested and documented before being considered complete.

---

## 👤 About

Built as a practical **AI + Technical Program Management portfolio** to explore how AI can augment program management workflows and improve decision support.

The examples use synthetic project scenarios and do not contain proprietary company information.

---

## 📌 Status

**Current milestone:** Project Status Analyzer — **MVP Complete**

More AI TPM capabilities will be added incrementally.
