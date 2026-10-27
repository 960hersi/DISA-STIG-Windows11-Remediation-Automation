# Asking for a temporary security exception

An **exception** is permission to leave a requirement unmet for a limited time. **Compensating controls** are other safeguards that help reduce the risk while it remains unmet.

## Form
- Request ID and related control or issue:
- Who is asking and which system is affected:
- Requirement that cannot be met, including its version:
- Business reason and why the normal fix cannot happen now:
- What could go wrong and its impact:
- Likelihood and impact scores, with reasons:
- Other safeguards and proof that they work:
- Risk that remains after those safeguards:
- Person responsible for the fix and target date:
- Requested start, expiry and review dates:
- When the request must be escalated:
- Risk owner's decision, name and date:
- Final fix and retest evidence:

If information is missing, return the form for more detail. The assessor checks it; the authorized risk owner accepts or rejects the risk. Approval does not make the control pass.

## Fictional practice example
**EX-DEMO-01 is not a real finding or approved request.**

Imagine a training VM keeps two days of Security logs against a hypothetical seven-day requirement. The operator asks for time to configure log forwarding.

Possible temporary safeguards are daily private exports, restricted access and export-failure checks. These are proposals, not controls already in place. For practice, remaining risk is Medium because exports could miss events and their integrity has not been tested.

Owner, deadline, start and expiry are unassigned. Decision: **Not approved; example only.**
