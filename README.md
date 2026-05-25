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

---

# Individual STIG Findings

## WN11-AU-000500

Application event log size compliance failure.

<img width="1907" height="708" alt="WN11-AU-000500" src="https://github.com/user-attachments/assets/34358763-0d4a-426a-9281-440123f63973" />

---

## WN11-AU-000505

Security event log size compliance failure.

<img width="1918" height="650" alt="WN11-AU-000505" src="https://github.com/user-attachments/assets/0e240064-00f8-4e7e-853b-a497d54acc3c" />

---

## WN11-AU-000510

System event log size compliance failure.

<img width="1919" height="661" alt="WN11-AU-000510" src="https://github.com/user-attachments/assets/16610385-d34e-4f7a-82b6-8fc2e574367c" />

---

## WN11-AU-000005

Audit Credential Validation failures compliance finding.

<img width="1916" height="618" alt="WN11-AU-000005" src="https://github.com/user-attachments/assets/1b932622-bc53-4a05-ad5b-6c36dc445d12" />

---

## WN11-AU-000010

Audit Credential Validation successes compliance finding.

<img width="1919" height="646" alt="WN11-AU-000010" src="https://github.com/user-attachments/assets/b865a29e-38bd-453d-a337-c383cf74b7dc" />

---

## WN11-CC-000038

WDigest Authentication compliance finding.

<img width="1919" height="631" alt="WN11-CC-000038" src="https://github.com/user-attachments/assets/d38690dd-1137-4ab1-b508-40db4d5c0574" />

---

## WN11-CC-000039

Run as different user context menu compliance finding.

<img width="1919" height="623" alt="WN11-CC-000039" src="https://github.com/user-attachments/assets/e379e4b1-b7d9-4084-b881-11b38a53ab8d" />

---

## WN11-CC-000085

Early Launch Antimalware Boot-Start Driver Initialization Policy compliance finding.

<img width="1919" height="661" alt="WN11-CC-000085" src="https://github.com/user-attachments/assets/862f55c0-1645-40b4-aaa1-d8bac81fec91" />

---

## WN11-SO-000025

Guest account rename compliance finding.

<img width="1919" height="652" alt="WN11-SO-000025" src="https://github.com/user-attachments/assets/13489acc-c4f8-4513-9ebc-6af14cc3b66c" />

---

## WN11-SO-000030

Audit policy subcategory compliance finding.

<img width="1918" height="643" alt="WN11-SO-000030" src="https://github.com/user-attachments/assets/4dadfa0b-58b4-458b-acac-b8eb0ff6a1ef" />

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

<img width="1917" height="916" alt="DISASTIG" src="https://github.com/user-attachments/assets/7a262295-bb98-42ce-83e6-125997614a92" />

---


# Summary

This project demonstrates a practical Windows 11 DISA STIG remediation workflow using PowerShell automation and Tenable Vulnerability Management. The assessment focused on identifying failed compliance checks, implementing security hardening configurations, validating remediation success, and documenting the process using reproducible automation techniques.
