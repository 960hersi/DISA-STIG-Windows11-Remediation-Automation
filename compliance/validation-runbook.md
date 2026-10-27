# Validation and evidence runbook
## Preparation
Use only the authorized lab VM. Record UTC time, host alias, OS build, snapshot/backup reference, pinned STIG release and Tenable audit version. Preserve the original script commit. Obtain raw historical exports if available; otherwise label all new scans as a new assessment.
Create a local private evidence folder. No control changes are made by the read commands below. Do not execute the existing remediation script just to collect evidence.

## Read effective state
Run an elevated PowerShell session on Windows 11:
```powershell
Get-Date -Format o
Get-CimInstance Win32_OperatingSystem | Select-Object Caption,Version,BuildNumber
wevtutil gl Application
wevtutil gl Security
wevtutil gl System
auditpol /get /subcategory:"Credential Validation"
auditpol /get /category:*
Get-ItemProperty 'HKLM:\SOFTWARE\Policies\Microsoft\Windows\EventLog\Application' -Name MaxSize
Get-ItemProperty 'HKLM:\SOFTWARE\Policies\Microsoft\Windows\EventLog\Security' -Name MaxSize
Get-ItemProperty 'HKLM:\SOFTWARE\Policies\Microsoft\Windows\EventLog\System' -Name MaxSize
Get-ItemProperty 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\WDigest' -Name UseLogonCredential
Get-ItemProperty 'HKLM:\SYSTEM\CurrentControlSet\Policies\EarlyLaunch' -Name DriverLoadPolicy
Get-ItemProperty 'HKLM:\SYSTEM\CurrentControlSet\Control\Lsa' -Name SCENoApplyLegacyAuditPolicy
Get-LocalUser | Where-Object { $_.SID.Value -match '-501$' } | Select-Object Name,Enabled,SID
'batfile','cmdfile','exefile','mscfile' | ForEach-Object {
  Get-ItemProperty ("HKLM:\SOFTWARE\Classes\{0}\shell\runasuser" -f $_) -Name SuppressionPolicy
}
```
A missing key or inaccessible command is an observation to investigate, not an automatic compliance result. English auditpol subcategory names may differ by OS language.
Policy MaxSize is KB; effective wevtutil maxSize is bytes. Compare units correctly. Observe Security-log oldest/newest event timestamps and representative volume before making a retention-duration claim.

## Functional tests
- CTL-04/05: perform controlled success/failure credential validation with a disposable lab identity. Respect lockout limits. Inspect relevant Security events on the validating authority; event 4776 applies to NTLM validation, not every sign-in. Absence on this VM can mean the test scenario is inapplicable.
- CTL-07: inspect each relevant file-type context menu. Do not infer a security authorization boundary.
- CTL-08: reconcile value 3 with the precise pinned STIG release before concluding that the policy is correct. Registry presence alone does not prove boot-time effectiveness.
- CTL-09: check Enabled separately. The existing name Guest_DISABLED is not evidence of disabled state.

## Controlled remediation
Create a change record containing requested configuration, risk, affected control IDs, pre-change backup, approval (or disclosed self-approval), execution log, restart needs and rollback method. Capture prior values and account name. A missing value must be restored to its original absence if rolling back. Use a VM snapshot only if available and recovery is verified.
The existing script has no complete automatic rollback or per-step success validation; do not describe it as production-ready.

## Retest and custody
Obtain authenticated Tenable exports with scan ID/time, target alias, audit version and per-check outcomes. Compare the same host and baseline scope. Save effective-state output after refresh/restart where required.
Record file path, capture time, collector, SHA-256 hash, redactions and reviewer in the register. Keep originals private; hash sanitized copies separately.
Only update CSV assessment results after evidence review. Update findings and report counts together.
