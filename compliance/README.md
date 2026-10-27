# Security control assessment and remediation
This compliance extension turns the existing ten-check Windows 11 STIG project into an evidence-led assessment exercise. It documents control objectives, proposed cross-framework mappings, assessment procedures, evidence requests, findings management and reporting.

## Start here
1. Read [scope and method](scope-and-method.md).
2. Review the ten rows in [control-assessment.csv](control-assessment.csv) and [mapping rationale](framework-mapping.md).
3. Follow [validation-runbook.md](validation-runbook.md) on the authorized lab VM.
4. Record artifacts in [evidence-register.csv](evidence-register.csv).
5. Update [findings-register.csv](findings-register.csv), then [management-report.md](management-report.md).
6. Use [exception-request.md](exception-request.md) only for an actual unmet requirement; the sample is fictional.
7. Complete [vendor-assurance-review.md](vendor-assurance-review.md) as a separate mock SOC 2 interpretation exercise.

## Evidence status
The existing README reports remediation and includes screenshot links. The existing script contains ten configuration changes. This extension reviewed their text at commit dd75ab152865361640a08901a332bb9090e01bbd; it did not execute the script, inspect the linked images, access the VM or inspect raw Tenable exports. No new pass results, scan dates, approvals or operating-effectiveness conclusions are asserted.
All ten technical assessment results start as **Not assessed**. This is different from a failed test: required evidence has not yet been reviewed.

## Deliverables
- 10 assessed-scope controls with test procedures and proposed ISO/NIST/SOC 2 mappings.
- 12 evidence-register entries linking the existing script and README to ten pending evidence bundles.
- Four open documentation/evidence observations, not four newly discovered endpoint vulnerabilities.
- A closure workflow, exception template, mock vendor review and management summary.

This is a lab portfolio, not an ISO certification, SOC 2 report, third-party audit or full-framework compliance claim.
