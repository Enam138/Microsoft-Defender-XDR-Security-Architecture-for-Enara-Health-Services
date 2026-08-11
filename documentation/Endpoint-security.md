# Endpoint Security Implementation

## Overview

Microsoft Defender for Endpoint was used to provide endpoint security visibility, detection, investigation, and response within the Enara Health Services environment.

The implementation was validated using an active Windows endpoint and the security activity generated within the Microsoft Defender environment.

The endpoint became the primary source of the security telemetry used for the investigation and threat-hunting activities documented in this project.

## Endpoint Security Objectives

The endpoint security work focused on:

- Having an active endpoint visible in Microsoft Defender.
- Reviewing endpoint health and exposure.
- Investigating endpoint security activity.
- Reviewing the endpoint execution incident.
- Reviewing the endpoint device activity.
- Using Advanced Hunting to investigate available telemetry.
- Investigating PowerShell activity.
- Reviewing the automated investigation.
- Resolving the investigated incidents.
- Confirming the final endpoint security state.

## Endpoint Status

The environment contained one active endpoint during the final validation.

The endpoint information observed during validation was:

| Endpoint Attribute | Observed Result |
|---|---|
| Active devices | 1 |
| Health state | Active |
| Exposure level | 1 |
| Active alerts | 0 |
| Active incidents | 0 |
| First seen | August 7, 2026 |
| Last seen | August 10, 2026 |


The endpoint remained active during the validation period and continued to provide security visibility within Microsoft Defender.

## Endpoint Investigation

During the implementation, an execution-related security incident was identified on the endpoint.

The incident information observed was:

| Attribute | Result |
|---|---|
| Incident | Execution incident on one endpoint |
| Severity | Medium |
| Score | 36 |
| Status | Resolved |
| Active alerts | 0 / 2 |


The incident provided an opportunity to investigate endpoint activity through the Microsoft Defender security operations workflow.

The investigation included reviewing the incident information and examining the associated endpoint activity.

## Automated Investigation

A manual automated investigation was also initiated from the Microsoft Defender environment.

The resulting investigation was:

| Attribute | Result |
|---|---|
| Investigation | Automated investigation started manually |
| Severity | Informational |
| Score | 16 |
| Status | Resolved |
| Active alerts | 0 / 1 |


The automated investigation was reviewed as part of the overall endpoint investigation process.

## Advanced Hunting

Microsoft Defender Advanced Hunting was used to examine the security telemetry available within the environment.

The query returned a total of:

**35 events**

The results were distributed across the available security workloads as follows:

| Security Workload | Events |
|---|---:|
| Endpoint | 33 |
| Email | 2 |
| Cloud Apps | 0 |
| Identity | 0 |
| **Total** | **35** |

<img width="1600" height="788" alt="cross-workload-advanced-hunting-results" src="https://github.com/user-attachments/assets/cd911025-70a0-4960-b5eb-d70900e62ff7" />


The results showed that endpoint telemetry represented the majority of the events returned by the query.

Email telemetry was also present, while the selected query returned no events from Cloud Apps or Identity.

This result was used as an observation about the telemetry available in the environment rather than as evidence that those security workloads were incorrectly configured.

## PowerShell Investigation

PowerShell activity was investigated using Microsoft Defender Advanced Hunting.

The investigation identified:

**7 PowerShell executions**

The results were summarized using the available endpoint and account information.

The investigation produced:

**2 summarized results**

The analysis included the available information for:

- Endpoint
- Account
- PowerShell execution count
- First observed activity
- Last observed activity

<img width="1600" height="793" alt="kql-detection-time-window-investigation" src="https://github.com/user-attachments/assets/5ee1ec29-ab76-4262-8505-5de38cffac4a" />


This investigation demonstrated the use of Kusto Query Language to search available endpoint telemetry and identify PowerShell activity.

## PowerShell Threat Hunt

A dedicated PowerShell threat hunt was performed using Advanced Hunting.

The objective was to search the available endpoint telemetry for PowerShell activity rather than relying only on the previously identified endpoint incident.

The hunting process was:

    Endpoint Telemetry
            |
            v
    Advanced Hunting
            |
            v
    KQL Query
            |
            v
    PowerShell Activity
            |
            v
    Results Analysis

The hunt identified seven PowerShell executions and produced two summarized results.

<img width="938" height="946" alt="advanced-hunting-powershell-summary" src="https://github.com/user-attachments/assets/b00e3e80-d166-41de-a4cd-bd3ab2ca0362" />


## Incident Resolution

The endpoint execution incident and the manually initiated automated investigation were both resolved.

The final incident state observed during validation was:

| Security Activity | Final Status |
|---|---|
| Execution incident | Resolved |
| Automated investigation | Resolved |
| Active incidents | 0 |
| Active endpoint alerts | 0 |


The final state confirmed that there were no active incidents remaining after the investigation activities.

## Endpoint Final Validation

The endpoint was reviewed again after the investigation and response activities.

The final state showed:

- Health state: **Active**
- Exposure level: **1**
- Active alerts: **0**
- Active incidents: **0**
- Active devices: **1**


This provided the final validation point for the endpoint security implementation.

## Endpoint Security Results

The endpoint security implementation produced the following measurable results:

| Metric | Result |
|---|---:|
| Active endpoints | 1 |
| Endpoint health | Active |
| Exposure level | 1 |
| Active endpoint alerts | 0 |
| Active incidents | 0 |
| Advanced Hunting events | 35 |
| Endpoint events | 33 |
| Email events | 2 |
| Cloud Apps events | 0 |
| Identity events | 0 |
| PowerShell executions identified | 7 |
| PowerShell summarized results | 2 |
| Execution incident | Resolved |
| Automated investigation | Resolved |

## Security Engineering Observations

The endpoint investigation demonstrated the importance of validating security activity through multiple sources rather than relying on a single alert.

The execution incident provided the initial investigation point.

Advanced Hunting was then used to examine the available telemetry more broadly, while the PowerShell hunt provided additional visibility into endpoint activity.

The automated investigation provided another layer of investigation within the Microsoft Defender environment.

The final endpoint validation confirmed that the endpoint remained active and that no active incidents or alerts remained.

## Endpoint Security Conclusion

The endpoint security implementation successfully provided an operational endpoint security and investigation capability within the project environment.

The implementation demonstrated practical use of:

- Microsoft Defender for Endpoint
- Microsoft Defender XDR
- Advanced Hunting
- Kusto Query Language
- Endpoint investigation
- PowerShell threat hunting
- Automated investigation
- Incident management
- Security validation

The endpoint investigation progressed from security activity to investigation, threat hunting, automated investigation, incident resolution, and final endpoint validation.

The resulting evidence forms part of the broader Microsoft Defender XDR security operations architecture implemented for Enara Health Services.
