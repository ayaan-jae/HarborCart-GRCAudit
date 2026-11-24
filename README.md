<a id="top"></a>

<div align="center">

# HarborCart

### Cybersecurity GRC Audit

**One fictional company. Twenty control tests. A closer look at what the evidence actually says.**

<p>
  <img alt="ITGC Control Testing" src="https://img.shields.io/badge/ITGC-Control%20Testing-2454A6?style=flat-square&logo=checkmarx&logoColor=white">
  <img alt="NIST CSF 2.0" src="https://img.shields.io/badge/NIST-CSF%202.0-087E8B?style=flat-square&logo=securityscorecard&logoColor=white">
  <img alt="ISO/IEC 27001:2022" src="https://img.shields.io/badge/ISO%2FIEC-27001%3A2022-434B58?style=flat-square&logo=shield&logoColor=white">
  <img alt="Synthetic Data" src="https://img.shields.io/badge/Data-Synthetic-6A53A3?style=flat-square&logo=databricks&logoColor=white">
</p>

[The case](#the-case) &nbsp;|&nbsp; [My approach](#my-approach) &nbsp;|&nbsp; [Findings](#what-the-audit-found) &nbsp;|&nbsp; [Project files](#explore-the-project)

</div>

## The case

HarborCart is a fictional online retailer with a familiar problem: security policies look good on paper, but do the controls actually work?

I followed the evidence across employee access, AWS, GitHub, ServiceNow and Microsoft Sentinel to find out. This project shows how I tested controls, connected findings to business risk and turned the results into recommendations someone could act on.

<table>
  <tr>
    <td align="center" width="25%"><strong>20</strong><br />ITGC tests</td>
    <td align="center" width="25%"><strong>25</strong><br />Audit findings</td>
    <td align="center" width="25%"><strong>22</strong><br />NIST categories</td>
    <td align="center" width="25%"><strong>93</strong><br />ISO Annex A controls</td>
  </tr>
</table>

> **The takeaway:** Having a policy is not the same as proving the control worked.

## My approach

<div align="center">

**Policy** &nbsp;→&nbsp; **Evidence** &nbsp;→&nbsp; **Control test** &nbsp;→&nbsp; **Finding** &nbsp;→&nbsp; **Risk and action**

</div>

| I looked at | What I tested |
| :--- | :--- |
| **Identity and access** | Departures, MFA, administrator privileges and access reviews |
| **Development and change** | Pull request approvals, CI checks and production changes |
| **AWS security** | Public storage, encryption, credentials and vulnerabilities |
| **Detection and recovery** | Logs, alerts, incident handling, backups and restoration |
| **Governance** | Supplier reviews, privacy requests, training and physical access |

<details>
<summary><strong>See how the testing was done</strong></summary>

I started with the fictional company policies, identified the relevant system records and tested samples against the stated requirements. I assessed design and operating effectiveness separately, documented exceptions and mapped the results to NIST CSF 2.0, ISO/IEC 27001:2022 and the risk register.

The evidence includes sample events, not complete native logs. Where the records did not support a firm conclusion, I flagged the limitation.

</details>

## What the audit found

**25 findings. Three rated critical.** The report concludes that the selected ITGCs were not operating effectively within the tested scope.

| Severity | Findings |
| :--- | ---: |
| **Critical** | **3** |
| **High** | **10** |
| **Medium** | **10** |
| **Low** | **2** |

### Three findings that stood out

<details>
<summary><strong>FND-001 &nbsp; | &nbsp; Former employees still had access</strong></summary>

Four departed employees had enabled accounts, and the supplied records showed activity after their departure dates.

**Risk:** Unauthorized access to business systems and customer information.  
**Recommendation:** Disable the accounts, review activity and automate offboarding alerts.

The reported elapsed day figures need reconciliation.

</details>

<details>
<summary><strong>FND-002 &nbsp; | &nbsp; Powerful admin roles lacked safeguards</strong></summary>

Seven privileged roles were permanently assigned without recorded review. Two Global Administrator accounts lacked registered MFA in the supplied evidence.

**Risk:** A compromised account could expose the identity environment.  
**Recommendation:** Review standing privileges, require strong MFA and use time bound PIM access.

</details>

<details>
<summary><strong>FND-003 &nbsp; | &nbsp; Customer export storage was exposed</strong></summary>

A customer export resource was publicly accessible and unencrypted. The related potential privacy incident was not escalated within the policy timeframe.

**Risk:** Possible exposure of customer information.  
**Recommendation:** Restrict access, preserve logs, investigate and involve Legal and Privacy.

**Important:** The evidence does not prove data exfiltration. Actor attribution and extent of access require further verification.

</details>

## Framework snapshot

| NIST CSF 2.0 | ISO/IEC 27001:2022 |
| :--- | :--- |
| **6 functions and 22 categories** assessed | **93 Annex A controls** assessed |
| Main gaps in access, data protection, monitoring and incident response | 6 Yes, 42 Partial, 11 No, 33 Not evidenced, 1 Not applicable |
| Internal maturity scale from 0 to 4 | Implementation labels are not proof of effectiveness |

These assessments identify gaps. They are **not** NIST compliance scores or an ISO certification opinion.

## What I would prioritize

| When | Focus |
| :--- | :--- |
| **First 2 days** | Contain exposed storage, preserve logs and secure leaver and administrator access |
| **Within 7 days** | Restore cloud monitoring, review alerts and address critical weaknesses |
| **Within 30 days** | Strengthen change approvals, rotate aged credentials and test recovery |
| **Within 90 days** | Improve access reviews, supplier oversight, privacy processes and risk reporting |

These are recommendations, not completed fixes. Management validation, assigned owners and retesting are still required.

## Explore the project

Each file follows a stage of the audit. Start with the company brief, then follow the evidence through to the report.

| Open | What is inside |
| :--- | :--- |
| **[01 &nbsp; Company and policies](01-case-background/CompanyPolicy.docx)** | The fictional business, systems and control requirements |
| **[02 &nbsp; Evidence data](02-evidence/EvidenceData.xlsx)** | Simulated records from the systems in scope |
| **[03 &nbsp; Audit workpapers](03-audit-workpapers/WorkPapers.xlsx)** | Testing, exceptions, risk analysis and framework mapping |
| **[04 &nbsp; Final audit report](04-final-report/AuditReport.docx)** | Results, critical findings and proposed remediation |

<details>
<summary><strong>Scope, dates and evidence notes</strong></summary>

| Item | Detail |
| :--- | :--- |
| Assessment period | 1 November 2025 to 31 October 2026 |
| Evidence cutoff | 31 October 2026 |
| Systems | Microsoft Entra ID, AWS, GitHub Enterprise Cloud, ServiceNow and Microsoft Sentinel |
| Report status | Management validation pending |
| Evidence limitations | Synthetic records and event samples; some data needs reconciliation |

</details>

## Why I built this

I wanted to show more than a list of security controls. The interesting part is tracing a requirement to actual records, knowing when the evidence is incomplete and explaining the risk clearly enough for someone to make a decision.

That is what this case study is about.

> **Portfolio disclaimer:** HarborCart Commerce is entirely fictional. The policies, people, records and events are synthetic. This is a training project, not an audit, certification or assurance opinion about a real company.

<div align="center">

[Back to top](#top)

</div>
