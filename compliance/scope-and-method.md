# What I am checking and how

## What is included
I am checking the ten settings in my existing PowerShell script on a Windows 11 Azure lab VM. Before testing, I need to record a safe VM name, Windows version, test date, STIG version and Tenable audit-file version.

## My approach
1. Read the requirement in the STIG version I am using.
2. Write down the expected setting.
3. Check the script and the actual VM setting.
4. Save dated command output or scan results.
5. Explain what that evidence shows and what it cannot show.
6. Fix problems and test again.

Three main questions: would the control help with the risk, is it configured, and does it actually work? A single test cannot show it worked throughout a SOC 2 Type II reporting period.

## Results I will use
- **Not checked yet:** I have not reviewed enough evidence.
- **Pass:** Dated evidence meets the specific test and the reviewer is recorded.
- **Fail:** Evidence shows the requirement is not met.
- **Partly meets the test:** Some required parts work and others do not.
- **Not applicable:** The control does not apply, with a recorded reason and reviewer.

Missing evidence is not a pass or fail. An approved exception does not turn a failed control into a pass.

## Responsibilities and follow-up
I am the project author. Owner, reviewer and approver fields stay unassigned until someone takes the role. If I review my own work, I will say so rather than call it independent assurance.

For practice, I can rate likelihood and impact from 1 to 3, explain them and multiply: 1-2 Low, 3-4 Medium, 6-9 High. This is a lab method, not a DISA category or CVSS score. The current issues use follow-up priority because they are missing information, not confirmed new vulnerabilities.

To close an issue, I need the fix, retest evidence, date and reviewer. An authorized risk owner decides whether to accept an exception.

Keep original evidence private. Remove usernames, IPs, tenant information and secrets from public copies. Record what was removed and hash original and edited copies separately.
