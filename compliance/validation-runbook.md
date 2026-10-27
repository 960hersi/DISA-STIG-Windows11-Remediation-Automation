# How I will check the controls and save evidence

I am new to compliance. This guide helps me practise saving proof of how a control works. The commands have not been run as part of this documentation update.
## Before I start
Use only the lab VM I am allowed to test. Record UTC time, host alias, OS build, snapshot/backup reference, STIG version I am using and Tenable audit version. Preserve the original script commit. Obtain original scan exports if available; otherwise label all new scans as a new assessment.
Create a local private evidence folder. No control changes are made by the read commands below. Do not execute the existing remediation script just to collect evidence.

## Check the settings actually in use
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

## Check whether the controls work
- CTL-04/05: perform controlled success/failure credential validation with a disposable lab identity. Respect lockout limits. Inspect relevant Security events on the validating authority; event 4776 applies to NTLM validation, not every sign-in. Absence on this VM can mean the test scenario is inapplicable.
- CTL-07: inspect each relevant file-type context menu. Do not infer a security authorization boundary.
- CTL-08: check value 3 against the exact STIG version I am using before concluding that the policy is correct. Registry presence alone does not prove boot-time effectiveness.
- CTL-09: check Enabled separately. The existing name Guest_DISABLED is not evidence of disabled state.

## Make changes carefully
Before a change, record the planned setting, risk, control IDs, backup, approval, commands run, restart needs and how to undo it. If I approve my own lab change, I will say so. Capture prior values and account name. A missing value must be restored to its original absence if rolling back. Use a VM snapshot only if available and recovery is verified.
The existing script does not automatically undo every change or check every step. I will not describe it as ready for production.

## Check again and save proof
Save authenticated Tenable scan exports with scan ID/time, target alias, audit version and per-check outcomes. Compare the same host and baseline scope. Save effective-state output after refresh/restart where required.
Record the file path, capture time, person collecting it, SHA-256 hash, details removed and reviewer in the evidence list. Keep originals private; hash sanitized copies separately.
I will update checklist results only after reviewing the evidence. Update findings and report counts together.

