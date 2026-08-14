# Enterprise Identity Modernization — Sample Program Update

## Scenario

The identity modernization program is targeting production launch in 8 weeks.

The Identity Engineering team has completed the core identity-platform configuration. Application Engineering has migrated 6 of 10 applications. Four applications remain.

One of the remaining applications uses a legacy authentication integration that is not compatible with the target OpenID Connect implementation. The application team estimates 5 business days to modify the integration, but the estimate has not yet been reviewed by Identity Engineering.

The external identity vendor has committed a required configuration change for next week. The commitment is verbal and has not yet been recorded in a formal delivery plan.

Security has requested a review before production launch. The review has not started, and Security has indicated that the review normally requires 7 business days. It is not yet confirmed whether the vendor configuration change must be completed before the security review can begin.

QA has planned 2 weeks of end-to-end testing after the remaining application integrations are available. The testing schedule assumes the applications are ready at the start of the test window, but no contingency has been included in the current plan.

The infrastructure team has confirmed production environment availability for the planned launch window.

The program sponsor wants to maintain the 8-week launch date because of a downstream business commitment.

## Known Facts

- Target launch: 8 weeks
- 10 applications in scope
- 6 applications migrated
- 4 applications remain
- One remaining application requires an authentication integration change
- Estimated change duration: 5 business days
- Identity Engineering has not yet validated that estimate
- Vendor configuration change expected next week
- Vendor commitment is verbal
- Security review has not started
- Security review normally requires 7 business days
- Dependency between vendor configuration and security review is unknown
- End-to-end testing planned for 2 weeks
- Testing assumes applications are ready at test start
- No schedule contingency is currently included
- Production environment availability is confirmed
- Sponsor wants to maintain the launch date

## Important Unknowns

- Whether the vendor configuration is on the critical path
- Whether security can start before the vendor change is complete
- Whether the 5-day application estimate is achievable
- Whether all four remaining applications have similar integration complexity
- Whether testing can be performed in parallel for some applications
- Whether a fallback exists if the vendor misses its commitment
- Whether the launch date is contractually fixed or strategically preferred

## Evaluation Intent

This scenario is deliberately designed to exercise all four Skills:

1. Project Status Analyzer — overall health, schedule, risks, blockers, dependencies and actions.
2. Technical Change Impact Analyzer — impact of the authentication integration change.
3. Dependency & Critical Path Intelligence — vendor, security, application and testing dependency chains.
4. Decision Intelligence & Executive Briefing — whether and how leadership should act to protect the launch date.

The Skills should use only the facts relevant to the specific analysis and should preserve the stated unknowns.
