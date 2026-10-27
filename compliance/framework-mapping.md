# Framework mapping rationale
## Versions and interpretation
- ISO/IEC 27001:2022 Annex A candidate references align to ISO/IEC 27002:2022 guidance. A.8.15 logging, A.8.9 configuration management and A.8.7 malware protection are proposed topic mappings. Check applicability and full requirements using an authorized copy of the standards before approving mappings. Full licensed wording was not reviewed or reproduced.
- NIST CSF 2.0 (CSWP 29, February 2024): PR.PS-01 configuration practices, PR.PS-04 logging availability and PR.PS-05 unauthorized software prevention. These are partial contributions to outcomes, not one-to-one equivalences.
- SOC 2: 2017 Trust Services Criteria with revised points of focus 2022; proposed CC6.1 logical protection, CC6.8 malicious-software protection and CC7.2 monitoring relationships. Confirm full criteria before approval. SOC means System and Organization Controls here.
No ISO management-system clauses, complete SOC 2 criteria, or full NIST outcomes are satisfied merely by applying registry values.

## Mapping decisions
CTL-01 through CTL-05 and CTL-10 contribute to logging. Log capacity and audit settings do not establish central monitoring, alert response, protected retention or operating effectiveness.
CTL-06 and CTL-07 contribute narrowly to configuration and logical-protection objectives. Context-menu suppression does not prevent use of all alternate execution paths.
CTL-08 contributes to malware protection through boot configuration. It does not establish active EDR coverage or software allowlisting.
CTL-09 is mapped narrowly to configuration: changing the Guest name does not demonstrate identity lifecycle management, account disabling or least privilege.
Each CSV row includes rationale and a limitation. All mappings require review.

## Governance controls outside the script
The findings workflow supports NIST ID.RA-01 and ID.RA-06 concepts (recording vulnerabilities and tracking risk response). Proposed change records relate to ISO A.8.32 and SOC 2 CC8.1; those processes are documented exercises until executed and evidenced. Exception decisions relate to risk treatment and cannot be delegated to an automated pass/fail result.

## Sources
- [ISO 27001 overview](https://www.iso.org/standard/27001)
- [ISO 27002 official standard information](https://www.iso.org/standard/75652.html)
- [NIST CSF 2.0 official publication](https://csrc.nist.gov/pubs/cswp/29/the-nist-cybersecurity-framework-csf-20/final)
- [AICPA SOC resources and Trust Services Criteria](https://www.aicpa-cima.com/resources/landing/system-and-organization-controls-soc-suite-of-services)
- [DISA STIG downloads](https://public.cyber.mil/stigs/downloads/)
Sources identify governing references; proposed crosswalks are the author's analysis, not mappings endorsed by those organizations.
