# Threat Hunting and Advanced Hunting

## Overview

Microsoft Defender Advanced Hunting was used to perform proactive security investigation within the Enara Health Services environment.

The objective was to use available security telemetry and Kusto Query Language (KQL) to investigate activity beyond the information provided by individual alerts or incidents.

The threat-hunting work focused on two main activities:

- Cross-workload Advanced Hunting.
- A dedicated PowerShell threat hunt.

The hunting results were based on the telemetry actually available in the environment during the investigation.

## Threat Hunting Objectives

The threat-hunting activities were designed to:

- Review available Microsoft Defender security telemetry.
- Identify which security workloads were producing events.
- Use KQL to investigate security activity.
- Investigate PowerShell execution.
- Correlate PowerShell activity with available device and account information.
- Identify the number of observed PowerShell executions.
- Establish first-seen and last-seen activity where available.
- Use the hunting results as additional context during security investigation.

## Advanced Hunting Environment

Microsoft Defender Advanced Hunting was used as the primary investigation interface for querying the available security telemetry.

The investigation workflow was:

    Security Telemetry
            |
            v
    Microsoft Defender Advanced Hunting
            |
            v
    Kusto Query Language
            |
            v
    Query Results
            |
            v
    Activity Analysis
            |
            v
    Security Investigation

Advanced Hunting was used as an analyst-driven investigation capability rather than relying only on automatically generated security alerts.

## Cross-Workload Investigation

A cross-workload Advanced Hunting investigation was performed to determine what security telemetry was available across the Microsoft Defender environment.

The query returned:

**35 events**

The observed distribution was:

| Security Workload | Events |
|---|---:|
| Endpoint | 33 |
| Email | 2 |
| Cloud Apps | 0 |
| Identity | 0 |
| **Total** | **35** |

<img width="1600" height="788" alt="cross-workload-advanced-hunting-results" src="https://github.com/user-attachments/assets/a788a85c-9cda-43fa-aa55-27d317f647b3" />


The result showed that endpoint telemetry represented the majority of the events returned by the investigation.

Email telemetry was also present.

The selected query did not return Cloud Apps or Identity events.

These results were documented as observations about the available telemetry rather than assumptions about the overall configuration of each security workload.

## Endpoint Hunting Results

Endpoint telemetry accounted for:

**33 of the 35 events**

returned by the cross-workload investigation.

This made endpoint telemetry the primary source of events available during the selected investigation.

The endpoint data was subsequently used for more focused investigation, including the PowerShell threat hunt.

<img width="938" height="946" alt="advanced-hunting-powershell-summary" src="https://github.com/user-attachments/assets/0dd51a0e-49e5-4afb-9aa9-35e7952169ce" />


## Email Hunting Results

The cross-workload investigation returned:

**2 email events**

The email events formed part of the total 35 events returned by the query.

| Workload | Events |
|---|---:|
| Endpoint | 33 |
| Email | 2 |
| Cloud Apps | 0 |
| Identity | 0 |

The email telemetry was observed through the same Advanced Hunting investigation used to review the broader security environment.

## Cloud Apps and Identity Results

The selected cross-workload query returned:

- Cloud Apps: 0 events
- Identity: 0 events

These results were not interpreted as proof that the corresponding security services were non-functional.

They represented the telemetry returned by the specific investigation that was performed.

This distinction was important when validating the environment because security configuration and security telemetry are separate considerations.

## PowerShell Threat Hunt

A dedicated PowerShell threat hunt was performed using Microsoft Defender Advanced Hunting.

The purpose of the hunt was to identify PowerShell execution activity within the available endpoint telemetry.

The hunt was performed independently of simply reviewing the original endpoint incident.

The investigation workflow was:

    Endpoint Telemetry
            |
            v
    PowerShell Activity
            |
            v
    KQL Filtering
            |
            v
    Device / Account Analysis
            |
            v
    Execution Count
            |
            v
    Threat Hunting Results

<img width="948" height="944" alt="advanced-hunting-powershell-pid" src="https://github.com/user-attachments/assets/fa91672e-9399-4b93-9aec-15e0ffc745be" />


## PowerShell Hunt Results

The PowerShell hunt identified:

**7 PowerShell executions**

The results were summarized into:

**2 results**

The investigation included the available information for:

- Device
- Account
- PowerShell execution count
- First observed activity
- Last observed activity

<img width="948" height="944" alt="advanced-hunting-powershell-pid" src="https://github.com/user-attachments/assets/1f6394e2-ad04-40c6-94a1-3ddcdc3e102c" />


The results demonstrated that Advanced Hunting could be used to identify and summarize PowerShell activity from the available endpoint telemetry.

## PowerShell Investigation Data

The PowerShell investigation was structured around the available endpoint activity.

The resulting information allowed the activity to be reviewed according to:

| Investigation Field | Purpose |
|---|---|
| Device | Identify the endpoint associated with the activity |
| Account | Identify the associated account |
| Execution count | Measure observed PowerShell activity |
| First seen | Establish earliest observed activity |
| Last seen | Establish latest observed activity |

The hunt therefore provided additional context beyond simply identifying that PowerShell had been executed.

## Kusto Query Language

Kusto Query Language was used to query and analyze the available security telemetry.

The PowerShell investigation used KQL to identify relevant activity and organize the results into a form that could be reviewed during the security investigation.

The use of KQL allowed the investigation to move from manually reviewing individual events to querying and summarizing security telemetry systematically.

The investigation demonstrated practical use of KQL for:

- Filtering telemetry.
- Identifying relevant activity.
- Grouping results.
- Counting activity.
- Correlating device information.
- Correlating account information.
- Reviewing time-based activity.

<img width="936" height="941" alt="cross-workload-hunting-summary" src="https://github.com/user-attachments/assets/ec0e0be4-4ceb-4361-9fb8-8e43e8d1549c" />


## Threat Hunting and Incident Investigation

The threat-hunting activity complemented the endpoint incident investigation.

The security workflow was:

    Endpoint Security Activity
            |
            v
    Security Incident
            |
            v
    Endpoint Investigation
            |
            v
    Advanced Hunting
            |
            v
    PowerShell Threat Hunt
            |
            v
    Activity Analysis
            |
            v
    Security Assessment

This allowed the investigation to move beyond the original alert and examine available endpoint telemetry more broadly.

## Threat Hunting Results Summary

The completed hunting activities produced the following measurable results:

| Hunting Activity | Result |
|---|---:|
| Cross-workload events | 35 |
| Endpoint events | 33 |
| Email events | 2 |
| Cloud Apps events | 0 |
| Identity events | 0 |
| PowerShell executions | 7 |
| PowerShell summarized results | 2 |

These results represent the actual telemetry returned during the investigations performed within the project environment.

## Telemetry Limitations

The hunting results were dependent on the telemetry available within the environment.

The cross-workload investigation returned no Cloud Apps or Identity events.

This did not lead to artificial generation of events simply to increase the apparent hunting coverage.

Instead, the observed results were retained as part of the project evidence.

This approach ensured that the threat-hunting documentation reflected the actual security data available during the implementation.

## Security Engineering Observations

The Advanced Hunting activities demonstrated several practical security operations principles.

First, automated alerts are not the only source of security intelligence.

Second, security telemetry can be investigated proactively using KQL.

Third, endpoint telemetry can be searched for specific behaviors such as PowerShell execution.

Fourth, the availability of telemetry directly affects the scope of a threat hunt.

Finally, the absence of results from a particular workload should be investigated in context rather than automatically interpreted as a security-control failure.

## Final Threat Hunting Assessment

The threat-hunting implementation demonstrated practical use of Microsoft Defender Advanced Hunting and Kusto Query Language within the Enara Health Services environment.

The completed investigation activities produced:

- 35 cross-workload events.
- 33 endpoint events.
- 2 email events.
- 0 Cloud Apps events.
- 0 Identity events.
- 7 PowerShell executions.
- 2 summarized PowerShell results.

The PowerShell investigation provided additional endpoint context and demonstrated the ability to move from security telemetry to focused behavioral investigation.

The threat-hunting work therefore formed an important part of the broader Microsoft Defender XDR security operations workflow implemented in this project.
