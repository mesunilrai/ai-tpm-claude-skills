# AI TPM Skills — Cross-Skill Validation Scorecard

## 1. Purpose

Provide a repeatable checklist for evaluating the four AI TPM Skills as an integrated workflow.

**Status:** Not executed — awaiting validation of the actual Skills.

## 2. Scoring Scale

| Score | Meaning |
|---|---|
| 2 | Meets expectation; supported by output evidence |
| 1 | Partially meets expectation; a material gap exists |
| 0 | Fails expectation or contains a material error |
| N/A | Not applicable, with rationale documented |

A score must not be assigned without reviewing the relevant output.

## 3. Quality Dimensions

| ID | Dimension | What to verify |
|---|---|---|
| Q01 | Fact preservation | Counts, dates, durations, commitments, and constraints remain accurate |
| Q02 | Evidence traceability | Material claims are supported by input facts or explicitly labeled inferences |
| Q03 | Hallucination control | No invented owners, dates, dependencies, requirements, or metrics |
| Q04 | Uncertainty handling | Unknowns and unvalidated estimates remain explicit |
| Q05 | Dependency reasoning | Confirmed relationships are separated from candidate relationships |
| Q06 | Schedule reasoning | No unsupported claim that the launch is guaranteed, impossible, or on the critical path |
| Q07 | Risk propagation | Relevant risks identified in one analysis are considered by other relevant analyses |
| Q08 | Decision quality | Options, trade-offs, evidence, and decision gaps are clear |
| Q09 | Executive fidelity | The briefing preserves material facts, caveats, and trade-offs |
| Q10 | Actionability | Recommended actions have clear purpose and validation outcomes |

## 4. Cross-Skill Consistency Checks

For each check, record the source output, evidence excerpt, score, and reviewer notes.

### C01 — Common facts

Do all Skills preserve the same baseline facts?

- 10 applications in scope
- 6 migrated; 4 remaining
- One known legacy-authentication incompatibility
- Five-business-day estimate, not yet validated
- Verbal vendor commitment expected next week
- Security review pending; normally seven business days
- Two weeks of end-to-end testing planned
- No schedule contingency included
- Production environment availability confirmed
- Eight-week target launch

### C02 — Uncertainty propagation

Verify that:

- The vendor-to-security dependency is not asserted as confirmed.
- The critical path is not presented as confirmed without adequate evidence.
- The five-day estimate remains unvalidated.
- Unknown fallback arrangements remain unknown.
- Unconfirmed ownership and dates are not invented.

### C03 — Risk consistency

If a Skill identifies a material risk, check whether the relevant downstream Skills reflect its implications.

A risk need not appear identically in every output. Differences should be explainable by the Skill's purpose and scope.

### C04 — Dependency-to-decision traceability

For each material recommendation, ask:

- Which dependency or risk supports it?
- What evidence supports the dependency?
- Which assumption could invalidate the recommendation?
- What needs to be confirmed before commitment?

### C05 — Executive fidelity

Compare the executive briefing with the detailed analyses.

Check whether any material risk, uncertainty, qualification, or trade-off was omitted or overstated.

## 5. Execution Results

| Check | Score | Evidence / notes |
|---|---|---|
| Q01 — Fact preservation | Pending | |
| Q02 — Evidence traceability | Pending | |
| Q03 — Hallucination control | Pending | |
| Q04 — Uncertainty handling | Pending | |
| Q05 — Dependency reasoning | Pending | |
| Q06 — Schedule reasoning | Pending | |
| Q07 — Risk propagation | Pending | |
| Q08 — Decision quality | Pending | |
| Q09 — Executive fidelity | Pending | |
| Q10 — Actionability | Pending | |
| C01 — Common facts | Pending | |
| C02 — Uncertainty propagation | Pending | |
| C03 — Risk consistency | Pending | |
| C04 — Dependency-to-decision traceability | Pending | |
| C05 — Executive fidelity | Pending | |

## 6. Failure Severity

- **Critical:** Could materially change a launch or leadership decision.
- **High:** Could materially mislead a TPM or stakeholder.
- **Medium:** A meaningful gap that weakens analysis but does not invalidate the main conclusion.
- **Low:** A minor, non-material issue.

Record the actual output excerpt for every material failure.

## 7. Release Gate

The following are proposed quality gates, not results already achieved.

- No unresolved Critical findings.
- No unresolved High findings affecting the integrated decision.
- Material facts and uncertainties are preserved.
- All material recommendations are evidence-linked.
- Cross-skill contradictions are resolved or explicitly explained.
- Changes made to address findings have been retested.
- The final assessment matches the observed evidence.

**Final outcome:** Pending execution.

**Reviewer decision:** Pending.

**Outstanding findings:** Pending.

**Retest required:** Pending.
