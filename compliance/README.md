# Security compliance - Windows Remediation Automation

A **control** is a safeguard, such as an audit setting. **Evidence** is the information used to show whether that safeguard works.

## What I added
- A [checklist](control-assessment.csv) for the ten controls in my script.
- [Possible ISO NIST and SOC 2 connections](framework-mapping.md).
- An [evidence list](evidence-register.csv) and an [issues list](findings-register.csv).
- A [testing guide](validation-runbook.md), [exception form](exception-request.md), [progress report](management-report.md) and [practice vendor review](vendor-assurance-review.md).

## What is finished
The documents are written. The original README describes remediation and links to screenshots. This update used the text of the README and script at commit dd75ab152865361640a08901a332bb9090e01bbd. The screenshots and raw scans have not been reviewed for this update, and no new VM tests have been run.

All ten results start as **Not checked yet**. This means I still need evidence; it does not mean the controls failed.

## How I will use it
1. Read [what I am checking and how](scope-and-method.md).
2. Choose a checklist row and follow its test instructions.
3. Save the results and update the evidence list.
4. Record problems and check them again after fixing them.
5. Update the progress report.

