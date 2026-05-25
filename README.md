# DISA-STIG-Windows11-Remediation-Automation

# DISA-STIG-Windows11-Remediation-Automation

## Defense Information Systems Agency - Security Technical Implementation Guides (DISA STIGs)

### Windows 11 STIG Batch Remediation Assessment

---

## Overview

This project demonstrates the process of identifying, remediating, validating, and documenting Windows 11 DISA STIG compliance findings using PowerShell automation and Tenable Vulnerability Management.

The assessment was conducted using:

* Windows 11 Virtual Machine
* Microsoft Azure
* Tenable Vulnerability Management
* PowerShell ISE
* Windows Registry Editor

The goal of this assessment was to:

1. Perform a Windows 11 DISA STIG compliance scan
2. Identify failed STIG findings
3. Research remediation methods
4. Implement remediation manually and through automation
5. Validate successful remediation with Tenable rescans
6. Document the remediation process

---

# Technologies Used

* Windows 11
* Microsoft Azure
* Tenable Vulnerability Management
* PowerShell
* Windows Registry
* DISA STIG Compliance Checks

---

# STIGs Assessed

The following Windows 11 DISA STIG findings were identified and remediated:

| STIG ID        | Description                                                            |
| -------------- | ---------------------------------------------------------------------- |
| WN11-AU-000500 | Application event log size must be configured to 32768 KB or greater   |
| WN11-AU-000505 | Security event log size must retain at least one week of audit records |
| WN11-AU-000510 | System event log size must be configured to 32768 KB or greater        |
| WN11-AU-000005 | Audit Credential Validation failures                                   |
| WN11-AU-000010 | Audit Credential Validation successes                                  |
| WN11-CC-000038 | WDigest Authentication must be disabled                                |
| WN11-CC-000039 | Run as different user must be removed from context menus               |
| WN11-CC-000085 | Early Launch Antimalware Boot-Start Driver Initialization Policy       |
| WN11-SO-000025 | Built-in Guest account must be renamed                                 |
| WN11-SO-000030 | Audit policy using subcategories must be enabled                       |

---

# Initial Scan Results

The baseline Windows 11 DISA STIG scan was conducted using Tenable Vulnerability Management.

![Initial Scan Results](images/DISASTIG.png)

---

# Individual STIG Findings

## WN11-AU-000500

Application event log size compliance failure.

![WN11-AU-000500](images/WN11-AU-000500.png)

---

## WN11-AU-000505

Security event log size compliance failure.

![WN11-AU-000505](images/WN11-AU-000505.png)

---

## WN11-AU-000510

System event log size compliance failure.

![WN11-AU-000510](images/WN11-AU-000510.png)

---

## WN11-AU-000005

Audit Credential Validation failures compliance finding.

![WN11-AU-000005](images/WN11-AU-000005.png)

---

## WN11-AU-000010

Audit Credential Validation successes compliance finding.

![WN11-AU-000010](images/WN11-AU-000010.png)

---

## WN11-CC-000038

WDigest Authentication compliance finding.

![WN11-CC-000038](images/WN11-CC-000038.png)

---

## WN11-CC-000039

Run as different user context menu compliance finding.

![WN11-CC-000039](images/WN11-CC-000039.png)

---

## WN11-CC-000085

Early Launch Antimalware Boot-Start Driver Initialization Policy compliance finding.

![WN11-CC-000085](images/WN11-CC-000085.png)

---

## WN11-SO-000025

Guest account rename compliance finding.

![WN11-SO-000025](images/WN11-SO-000025.png)

---

## WN11-SO-000030

Audit policy subcategory compliance finding.

![WN11-SO-000030](images/WN11-SO-000030.png)

---

# Remediation Methodology

The remediation process followed this workflow:

1. Perform baseline STIG scan using Tenable
2. Identify failed STIG findings
3. Research remediation requirements
4. Develop PowerShell remediation scripts
5. Apply registry and audit policy modifications
6. Execute `gpupdate /force`
7. Restart the Windows 11 virtual machine
8. Perform validation scans using Tenable
9. Confirm remediation success

---

# PowerShell Automation

PowerShell automation was used to:

* Configure Windows Event Log sizes
* Configure audit policy settings
* Disable WDigest Authentication
* Modify registry-based security controls
* Configure Early Launch Antimalware policy
* Rename the built-in Guest account
* Apply Group Policy updates

The remediation script was executed using PowerShell ISE with administrative privileges.

---

# Validation

After remediation:

* The Windows 11 virtual machine was restarted
* A follow-up Tenable compliance scan was performed
* STIG findings were validated against the updated system configuration
* Registry values and audit policies were manually verified

---

# Outcome

The assessment successfully demonstrated:

* Windows 11 STIG compliance auditing
* Vulnerability remediation
* PowerShell automation
* Registry-based hardening
* Audit policy configuration
* Compliance validation using Tenable

---


# Summary

This project demonstrates a practical Windows 11 DISA STIG remediation workflow using PowerShell automation and Tenable Vulnerability Management. The assessment focused on identifying failed compliance checks, implementing security hardening configurations, validating remediation success, and documenting the process using reproducible automation techniques.
