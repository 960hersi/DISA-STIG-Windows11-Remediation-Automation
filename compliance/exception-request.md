# Security exception request
## Reusable template
- Exception ID and related finding/control:
- Requestor, asset scope and business need:
- Exact unmet requirement and baseline version:
- Why standard remediation is currently infeasible:
- Threat scenario and impact:
- Inherent likelihood/impact and supporting rationale:
- Compensating controls with evidence and remaining limitations:
- Residual likelihood/impact and rationale:
- Remediation owner and dated action plan:
- Proposed start, expiry and review cadence:
- Escalation trigger if controls fail or deadline slips:
- Risk owner decision, approver identity and date:
- Closure/retest evidence:

Incomplete requests return to the requestor. The assessor checks evidence and recommends disposition; the authorized risk owner accepts/rejects risk. Approval never changes a failed requirement to Pass.

## Fictional worked example
EX-DEMO-01 concerns an isolated training VM whose measured Security-log retention is two days against a hypothetical seven-day lab requirement. This scenario is invented; it is not a measured finding on Saeed's VM.
Request: temporary exception while log forwarding is configured. Proposed compensating controls: private daily exports, restricted VM access, monitoring of export failures. These are proposals, not implemented facts.
Illustrative residual risk remains Medium because gaps between exports and export integrity have not been validated. Owner and target date are unassigned. Decision: **Not approved; demonstration only**. No effective date or expiry exists until an actual risk owner approves a time-bound request.
