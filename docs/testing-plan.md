# LocalLens AI — Testing and Evaluation Plan

## 1. Objective

This plan defines how the LocalLens AI visit-readiness workflow will be evaluated before any real-world deployment. Testing will focus on evidence reliability, visit feasibility, uncertainty handling, and responsible recommendations.

## 2. Test Scenarios

| Test | Input or condition | Expected result |
|---|---|---|
| Time constraint | Required visit duration exceeds the visitor's available time | Experience is marked infeasible for the stated time window. |
| Unverified listing | Critical listing details have not been verified | System communicates uncertainty and does not claim confirmed availability. |
| Outdated information | A critical listing detail exceeds its defined freshness threshold | System flags stale information and requests confirmation where necessary. |
| Conflicting sources | Two sources provide different information about a critical detail | System flags the conflict and preserves both claims for review. |
| Access restriction | A reliable, applicable source confirms a restriction that prevents the proposed visit | Experience is not recommended under those conditions. |
| Unknown permission | Required appointment or permission status cannot be established | System advises confirmation before travel. |
| Unsupported AI claim | AI extracts a claim that cannot be traced to supporting evidence | Claim remains unverified and cannot independently justify a readiness decision. |
| Accessibility uncertainty | Required accessibility information is missing | System reports the information as unknown and does not assume the requirement is met. |
| Suitable alternative | The initial choice fails a hard constraint, but another eligible experience passes all applicable checks | System may offer the alternative with its evidence and limitations. |
| No suitable option | No option meets the required evidence and feasibility criteria | System explains that no suitable option could be confirmed. |
| Service failure | Evidence extraction or another required service fails | System reports the uncertainty or failure rather than presenting an unsupported ready result. |

## 3. Evaluation Metrics

- **Verified recommendation accuracy:** Proportion of recommendations labelled verified that satisfy the predefined verification criteria.
- **Hard-constraint compliance:** Proportion of recommendations satisfying all applicable hard constraints.
- **Conflict detection rate:** Proportion of deliberately introduced source conflicts correctly flagged.
- **Unsafe false-ready rate:** Frequency with which an experience is labelled ready despite a critical unresolved issue that should prevent that outcome.
- **Unsupported availability claims:** Number of claims of confirmed availability without adequate evidence. Target: zero in the defined test set.
- **Lesser-known provider discovery:** Number or proportion of eligible, relevant lesser-known experiences surfaced, assessed alongside evidence quality and constraint compliance.

## 4. Testing Method

Initial evaluation will use a small, curated dataset containing traceable sources and clearly labelled demonstration cases. Synthetic edge cases may be used to test conflicts, missing information, restrictions, and service failures; they will not be presented as real-world observations.

Before execution, each test will have a defined input, expected outcome, and reference answer. The team will record the actual output, pass/fail status, and explanation for failures. Where feasible, ordinary browsing of the same source material will serve as a baseline for comparing decision accuracy and time to decision.

## 5. Current Status

This document defines the proposed testing approach. The tests have not yet been executed, and no accuracy, performance, or real-world impact results are claimed.

## 6. Future Improvements

Future evaluation may include visitor and local-operator feedback, operator-confirmed updates, more destinations across Madhya Pradesh, and an assessment of whether the system's recommendations are useful and appropriate for local communities. Any wider claims will depend on the quality and representativeness of the evidence collected.
