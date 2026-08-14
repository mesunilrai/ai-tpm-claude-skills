# Project Status Analyzer — Evaluation & MVP Validation

## 1. Purpose

This document defines the evaluation approach for the **Project Status Analyzer** Claude Skill.

The Skill converts unstructured project or program updates into structured Technical Program Management analysis covering:

* Program health
* Schedule and critical-path concerns
* Risks
* Blockers and issues
* Dependencies
* Unknowns and assumptions
* Recommended next actions
* Leadership attention

The evaluation focuses on whether the Skill produces **evidence-based, actionable and appropriately cautious TPM analysis**.

---

# 2. Evaluation Objectives

The Skill is evaluated against the following capabilities:

| Capability            | Evaluation Objective                                                 |
| --------------------- | -------------------------------------------------------------------- |
| Program Health        | Correctly classify Green, Amber or Red based on available evidence   |
| Assessment Confidence | Indicate confidence when information is incomplete                   |
| Schedule Analysis     | Identify timeline pressure without inventing schedule data           |
| Critical Path         | Identify potential critical-path concerns and sequencing uncertainty |
| Risk Analysis         | Identify and prioritize meaningful risks                             |
| Risk Calibration      | Avoid unsupported probability, impact or severity claims             |
| Blocker Detection     | Distinguish blockers from risks and general issues                   |
| Dependency Analysis   | Identify dependencies and confidence level                           |
| Evidence Discipline   | Separate facts, inferences and unknowns                              |
| Actionability         | Recommend specific and prioritized next actions                      |
| Leadership Attention  | Identify supported decisions or escalations                          |
| Hallucination Control | Avoid inventing dates, owners, commitments or metrics                |

---

# 3. Test Case 01 — Amber / Tight Schedule

## Scenario

A project is planned to go live in 4 weeks. Development is 80% complete, but the security review has not started. The security team has a 2-week lead time. The vendor also has a pending API issue that could take 1 week to resolve.

## Expected Behavior

The Skill should:

* Assess the project as potentially **Amber** based on the limited remaining timeline.
* Identify the 4-week runway.
* Identify 20% remaining development.
* Identify the 2-week security review lead time.
* Identify the vendor API issue and its stated potential 1-week resolution time.
* Avoid assuming that the vendor issue is currently blocking progress.
* Avoid assuming that the security review is a mandatory launch gate unless explicitly stated.
* Avoid assuming that security, development and vendor remediation must occur sequentially.
* Identify unknown sequencing and dependency relationships.
* Avoid calculating a precise schedule buffer when the remaining development duration is unknown.
* Distinguish confirmed facts from inferences.
* Recommend immediate actions to clarify schedule-critical information.
* Identify leadership attention only where supported by the available information.

## Validation Result

**PASS**

The final MVP:

* Classified the program as **Amber**.
* Provided **Low assessment confidence** because important schedule information was missing.
* Correctly identified the known timeline and lead times.
* Did not fabricate a schedule buffer.
* Identified sequencing and dependency relationships as unknown.
* Distinguished the vendor issue from a confirmed blocker.
* Clearly separated inferred risks from confirmed information.
* Recommended specific immediate and follow-up actions.

## Key Learning

The Skill demonstrated that it can identify schedule risk without converting incomplete information into unsupported facts.

---

# 4. Test Case 02 — Green / Healthy Program

## Scenario

A project is scheduled to go live in 8 weeks. Development is 90% complete and is tracking to the original plan. Testing is scheduled to begin next week and has a confirmed 2-week duration. Security review has already been completed. All required teams have confirmed resource availability. No open critical risks or blockers have been reported.

## Expected Behavior

The Skill should:

* Classify the project as **Green**.
* Explain that the project is tracking to plan.
* Recognize that development is substantially complete.
* Recognize that security review is already completed.
* Recognize confirmed resource availability.
* Avoid inventing risks simply to populate the risk section.
* Distinguish normal project activities from actual risks or blockers.
* Identify testing as an upcoming milestone rather than automatically treating it as a risk.
* Avoid manufacturing leadership escalations.
* State that no material leadership intervention is evident if appropriate.

## Evaluation Focus

This test ensures the Skill does not become overly risk-oriented and classify healthy projects as Amber or Red simply because work remains.

## Acceptance Criteria

**PASS** if the Skill:

* Produces Green health.
* Provides evidence for the classification.
* Does not manufacture material risks.
* Does not manufacture blockers.
* Does not manufacture leadership escalations.

---

# 5. Test Case 03 — Red / Critical Blocker

## Scenario

A production launch is planned for Friday. A critical integration defect is preventing end-to-end testing from completing. The engineering team estimates that the defect will require at least 7 business days to resolve. The launch date is fixed and cannot be moved. There are only 3 business days remaining before launch. No workaround has been identified.

## Expected Behavior

The Skill should:

* Classify the program as **Red**.
* Provide high confidence because the critical timing information is explicitly provided.
* Identify the integration defect as a confirmed blocker.
* Identify the mismatch between the 7-business-day estimated resolution and the 3-business-day remaining window.
* Identify the launch date as a confirmed fixed constraint.
* Identify the lack of workaround as additional evidence of schedule risk.
* Explain that the current plan is not viable based on the stated information.
* Recommend immediate escalation and recovery/decision actions.
* Distinguish between:

  * Technical remediation
  * Schedule decision
  * Risk acceptance
  * Go/no-go decision
* Avoid inventing an alternative launch date or recovery solution.

## Evaluation Focus

This test validates whether the Skill can recognize a genuinely critical situation rather than defaulting to Amber.

## Acceptance Criteria

**PASS** if the Skill:

* Produces Red health.
* Identifies the defect as a confirmed blocker.
* Uses the explicit timeline mismatch as evidence.
* Identifies the fixed launch date.
* Recommends appropriate immediate escalation.
* Does not invent a recovery plan that is not supported by the input.

---

# 6. Test Case 04 — Missing Information / Uncertain Assessment

## Scenario

A project team reports that development is progressing and a vendor issue is under investigation. The team expects to complete the project soon, but no target launch date, remaining development percentage, vendor resolution estimate, dependency information, or confirmed blocker status is provided.

## Expected Behavior

The Skill should:

* Avoid making a confident Green, Amber or Red classification.
* Use an appropriate confidence level.
* Clearly identify the missing information required for a meaningful assessment.
* Avoid inventing a launch date.
* Avoid inventing schedule buffer.
* Avoid assuming the vendor issue is a blocker.
* Avoid assigning unsupported risk severity.
* Recommend obtaining the minimum information needed to assess project health.
* Keep the output useful rather than simply stating that information is missing.

## Evaluation Focus

This test validates the Skill's behavior when the input is insufficient for reliable program assessment.

## Acceptance Criteria

**PASS** if the Skill:

* Explicitly identifies material unknowns.
* Avoids unsupported conclusions.
* Provides practical information-gathering actions.
* Maintains a useful TPM-oriented response.

---

# 7. Evidence Classification Standard

The Skill uses three evidence categories.

## Confirmed

Information explicitly stated or directly supported by the user input.

Example:

> Development is 80% complete.

This is a confirmed fact.

## Inference

A reasonable conclusion derived from confirmed information.

Example:

> The remaining schedule appears tight.

This is an inference based on the stated timeline and remaining work.

## Unknown

Information needed for a reliable conclusion but not provided.

Example:

> It is unknown whether the vendor API issue blocks security testing.

The Skill must not present an inference or unknown as a confirmed fact.

---

# 8. Risk Classification Standard

The Skill uses:

* **Critical**
* **High**
* **Medium**
* **Low**

Risk priority should be based on available evidence, including:

* Potential impact
* Urgency
* Schedule proximity
* Critical-path relationship
* Dependency impact

The Skill must not invent numerical probability, impact or risk scores unless the user provides an explicit scoring framework.

When priority is an inference, the output should make that clear.

---

# 9. Blocker vs. Risk vs. Issue

The Skill uses the following distinction:

### Blocker

An issue that is currently preventing progress or preventing a required activity from proceeding.

### Risk

A potential future problem that may affect the project.

### Issue

A problem that currently exists but is not confirmed to be preventing progress.

An issue must not automatically be classified as a blocker.

---

# 10. Dependency Confidence

Dependencies are classified as:

### Confirmed

The relationship is explicitly stated.

### Likely

The relationship is strongly supported by the available information.

### Unknown

The relationship has not been established.

The Skill must not present an inferred dependency as confirmed.

---

# 11. MVP Acceptance Criteria

The Project Status Analyzer MVP is considered successful when it can:

* Produce evidence-based program health assessment.
* Express confidence in the assessment.
* Analyze schedule constraints.
* Identify potential critical-path concerns.
* Distinguish confirmed facts from inference and unknowns.
* Identify and prioritize meaningful risks.
* Distinguish blockers from risks and issues.
* Analyze dependency confidence.
* Avoid unsupported schedule calculations.
* Avoid inventing owners, dates, commitments or metrics.
* Produce prioritized and actionable next steps.
* Identify supported leadership decisions or escalations.
* Remain useful when information is incomplete.
* Avoid manufacturing risks or escalations for healthy projects.

---

# 12. V1 → V2 → MVP Evolution

## V1 — Initial Skill

The initial Skill provided:

* Executive summary
* Program health
* Risks
* Blockers
* Dependencies
* Recommended actions

### V1 Observation

The initial test demonstrated useful TPM analysis but showed that the model could strengthen inferred relationships into statements that sounded like confirmed facts.

---

## V2 — Evidence-Based Reasoning

V2 introduced:

* Confirmed facts
* Inferences
* Unknowns
* Critical-path reasoning
* Dependency confidence
* Risk prioritization
* Leadership attention

### V2 Observation

V2 substantially improved evidence discipline but showed that terminology could still occasionally become stronger than the original user input.

---

## MVP — Final Version

The final MVP strengthened:

* Evidence discipline
* Health assessment confidence
* Risk calibration
* Schedule reasoning
* Blocker vs. issue distinction
* Dependency confidence
* Action vs. leadership decision distinction
* Unsupported terminology prevention

### MVP Outcome

The final test demonstrated a more defensible TPM assessment with explicit uncertainty handling and without unsupported schedule calculations.

---

# 13. Known Limitations

The MVP is intentionally designed as a decision-support Skill rather than an autonomous program-management system.

It does not:

* Access live project systems.
* Validate project information against external sources.
* Automatically calculate complex schedules.
* Automatically determine organizational ownership.
* Replace TPM judgment.
* Make project decisions on behalf of leadership.
* Guarantee that an inference is correct.

The quality of the analysis depends on the quality and completeness of the project information provided.

---

# 14. Evaluation Philosophy

The objective is not to make the AI sound confident.

The objective is to make the AI **usefully accurate and appropriately uncertain**.

A strong output should:

> Know what is known.

> Clearly identify what is inferred.

> Explicitly identify what is unknown.

> Help the TPM determine what to do next.
