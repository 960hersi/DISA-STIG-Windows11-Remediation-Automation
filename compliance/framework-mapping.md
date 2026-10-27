# How my controls relate to ISO NIST and SOC 2

I am learning **control mapping**: explaining how one safeguard may support different security requirements. A connection does not mean that a whole requirement is met.

## References
| Reference | What it covers | How I use it |
|---|---|---|
| ISO/IEC 27001:2022 Annex A and ISO/IEC 27002:2022 | Security management requirements and control guidance | Suggest controls related to logging, configuration and malware protection |
| NIST CSF 2.0, February 2024 | Cybersecurity outcomes organizations work toward | Link my technical settings to relevant outcomes |
| SOC 2 Trust Services Criteria, 2017 with revised points of focus 2022 | Criteria used in SOC 2 examinations | Suggest how settings may support security criteria |

SOC 2 means System and Organization Controls here, not a security operations centre.

## My proposed mappings
- CTL-01 to CTL-05 and CTL-10: ISO A.8.15, NIST PR.PS-04 and SOC 2 CC7.2. Logging settings help make events available. I still need to check event generation, monitoring and retention.
- CTL-06 and CTL-07: ISO A.8.9, NIST PR.PS-01 and SOC 2 CC6.1. These settings contribute to secure configuration. Hiding a menu does not prevent every way to run a command.
- CTL-08: ISO A.8.7, NIST PR.PS-05 and SOC 2 CC6.8. A boot setting may support malware protection but does not prove that protection works.
- CTL-09: ISO A.8.9, NIST PR.PS-01 and SOC 2 CC6.1. Renaming Guest changes configuration; it does not disable the account or prove access is restricted.

These are proposed connections that need review, not exact equivalents. I need to check the full requirements before approving them. Full licensed ISO requirements have not been reviewed or copied here.

Recording issues and tracking fixes may support NIST ID.RA-01 and ID.RA-06. Documenting changes may support ISO A.8.32 and SOC 2 CC8.1. A written process still needs evidence that it was followed.

## Sources
- [ISO 27001](https://www.iso.org/standard/27001)
- [ISO 27002](https://www.iso.org/standard/75652.html)
- [NIST CSF 2.0](https://csrc.nist.gov/pubs/cswp/29/the-nist-cybersecurity-framework-csf-20/final)
- [AICPA SOC resources](https://www.aicpa-cima.com/resources/landing/system-and-organization-controls-soc-suite-of-services)
- [DISA STIG downloads](https://public.cyber.mil/stigs/downloads/)

