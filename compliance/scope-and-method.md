# Scope and assessment method
## Boundary
One Windows 11 Azure lab VM described by the existing project. Exact VM alias, OS build, assessment date, STIG release/version and Tenable audit-file version must be recorded before testing. No production systems, payment infrastructure, customer data, enterprise ISMS, vendor controls or assessment period are included.

## Evidence reviewed
Text of README.md and Remediation Script at commit dd75ab152865361640a08901a332bb9090e01bbd. Historical author statements are retained as reported claims, not independently re-performed results. Screenshot URLs are pointers, not reviewed artifacts.

## Assessment approach
For each control: confirm applicability against the pinned STIG; define expected state; inspect implementation; collect effective-state evidence; perform an authorized functional test where applicable; compare with expected state; record result and limitations; remediate; retest.
Check design (could this address the stated risk?) separately from implementation (is it configured?) and operation (does it work over the relevant period?).
A one-time lab test cannot establish Type II period-wide effectiveness.

## Results
Not assessed: evidence absent or not reviewed.
Pass: dated effective-state evidence meets the scoped test, with reviewer recorded.
Fail: reviewed evidence contradicts the defined requirement.
Partial: some required tests meet criteria but others remain unmet.
Not applicable: documented applicability rationale reviewed by a named reviewer.
Do not count Not assessed as either Pass or Fail.

## Roles and decisions
Saeed Hersi is the portfolio author and proposed lab operator. Reviewer, control owner, risk owner and approver fields remain unassigned until a person accepts the role. Self-review is allowed for learning but must be disclosed as such; do not imply independent assurance.

## Prioritization
Use documented likelihood (1-3) times impact (1-3): 1-2 Low, 3-4 Medium, 6-9 High. These are local lab ratings, not DISA CAT ratings or CVSS.
Documentation observations use action priority, not invented vulnerability severity.

## Closure
A finding closes only when remediation evidence, retest outcome, test date and reviewer are recorded, or an authorized time-limited exception is linked. An exception does not turn a failed control into a pass.
Keep evidence private until redacted. Publish aliases instead of tenant IDs, public IPs, usernames, tokens or unredacted scan inventories.
