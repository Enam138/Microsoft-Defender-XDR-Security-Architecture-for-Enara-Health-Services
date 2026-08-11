# Endpoint Security Implementation

## Overview

Microsoft Defender for Endpoint was implemented as the endpoint detection and response layer within the Enara Health Services cloud security environment.

The objective was to establish endpoint visibility, collect security telemetry, investigate suspicious activity, support automated investigation, and provide an operational endpoint response capability through Microsoft Defender XDR.

The endpoint security workflow was designed around:

    Endpoint
        |
        v
    Defender for Endpoint
        |
        +---- Telemetry
        |
        +---- Detection
        |
        +---- Alert
        |
        +---- Device Timeline
        |
        +---- Investigation
        |
        +---- Advanced Hunting
        |
        +---- Automated Investigation
        |
        v
    Microsoft Defender XDR
        |
        v
    Incident Response


## Objectives

The endpoint security implementation was designed to achieve the following objectives:

- Onboard a Windows endpoint into Microsoft Defender for Endpoint.
- Confirm endpoint connectivity and telemetry.
- Monitor endpoint health and exposure.
- Investigate endpoint security alerts.
- Analyze endpoint activity using Device Timeline.
- Investigate PowerShell execution activity.
- Use Advanced Hunting for proactive endpoint investigation.
- Perform a dedicated PowerShell threat hunt.
- Validate automated investigation capabilities.
- Manage endpoint-related security incidents.
- Resolve investigated incidents.
- Validate the endpoint after incident response activities.


## Endpoint Onboarding

A Windows endpoint was onboarded into Microsoft Defender for Endpoint and became visible within the Defender portal.

The onboarding process established the endpoint as a security telemetry source for the environment.

After onboarding, I validated that the endpoint was actively communicating with Microsoft Defender and that endpoint activity was being reported.

<img width="935" height="944" alt="defender-endpoint-device-onboarded" src="https://github.com/user-attachments/assets/d5cbdf70-cac5-4f1a-a01c-fa4332691247" />



## Endpoint Inventory

The Defender for Endpoint device inventory was used to verify that the endpoint was successfully registered within the environment.

The device inventory provided visibility into the endpoint and served as the starting point for subsequent endpoint investigations.

The validation process included:

- Confirming the device appeared in the Defender portal.
- Reviewing the device identity.
- Reviewing device activity.
- Confirming the device was actively reporting.
- Reviewing endpoint health.
- Reviewing exposure level.

<img width="935" height="944" alt="defender-endpoint-device-onboarded" src="https://github.com/user-attachments/assets/be0980eb-68db-41ad-98e6-b4037d9782a8" />



## Endpoint Health

The endpoint health state was reviewed as part of the final validation.

The endpoint remained active and continued to provide telemetry during the investigation period.

The final observed endpoint state was:

| Endpoint Metric | Result |
|---|---|
| Health state | Active |
| Exposure level | 1 |
| Active alerts | 0 |
| Active incidents | 0 |
| First seen | August 7, 2026 |
| Last seen | August 10, 2026 |



The endpoint health state provided evidence that the device remained connected to the Defender security platform after the investigation activities were completed.


## Endpoint Detection and Response

Microsoft Defender for Endpoint was used to provide endpoint detection and response capabilities.

The endpoint security layer provided visibility into:

- Process activity
- Security alerts
- Device activity
- Device timeline events
- Suspicious execution
- Investigation context
- Automated investigation results

The endpoint therefore became the primary source of security telemetry used during the practical investigation activities.

The operational model was:

    Endpoint Activity
          |
          v
    Defender for Endpoint
          |
          v
    Detection
          |
          v
    Alert
          |
          v
    Investigation
          |
          +--------------------+
          |                    |
          v                    v
    Device Timeline      Advanced Hunting
          |                    |
          +----------+---------+
                     |
                     v
             Security Assessment
                     |
                     v
               Incident Response


## Endpoint Security Incident

During the implementation, an execution-related security incident was generated on the endpoint.

The incident was classified as:

| Attribute | Result |
|---|---|
| Incident type | Execution incident on one endpoint |
| Severity | Medium |
| Incident score | 36 |
| Status | Resolved |
| Active alerts | 0 of 2 |

<img width="1600" height="792" alt="mde-alert-investigation" src="https://github.com/user-attachments/assets/3e23b064-7e92-4771-bd07-4d70888133aa" />


The incident provided an opportunity to perform an end-to-end endpoint investigation rather than simply reviewing configuration settings.


## Endpoint Investigation Process

The endpoint investigation followed a structured security operations workflow.

The investigation process included:

1. Reviewing the generated alert.
2. Identifying the affected endpoint.
3. Reviewing the incident context.
4. Examining endpoint activity.
5. Reviewing the Device Timeline.
6. Identifying related execution activity.
7. Performing Advanced Hunting.
8. Investigating PowerShell activity.
9. Reviewing automated investigation results.
10. Managing the incident.
11. Resolving the incident.
12. Validating the endpoint after resolution.

The workflow can be represented as:

    Alert
      |
      v
    Incident
      |
      v
    Endpoint Identification
      |
      v
    Device Timeline
      |
      v
    Advanced Hunting
      |
      v
    Automated Investigation
      |
      v
    Analyst Assessment
      |
      v
    Incident Resolution
      |
      v
    Endpoint Validation


## Device Timeline Investigation

The Defender for Endpoint Device Timeline was used to examine endpoint activity surrounding the security incident.

The timeline provided chronological context for activity associated with the endpoint and allowed related events to be reviewed during the investigation.

This was particularly useful for understanding the activity surrounding the execution-related incident.



The Device Timeline investigation allowed the analysis to move beyond the initial alert and examine the surrounding endpoint activity.


## PowerShell Investigation

PowerShell activity was investigated as part of the endpoint security analysis.

The objective was to determine whether PowerShell execution was occurring within the environment and identify the associated endpoint and account context.

Advanced Hunting was used to query the available endpoint telemetry.

The investigation identified:

**7 PowerShell executions**

The resulting analysis included:

- Device name
- Account
- PowerShell execution count
- First observed timestamp
- Last observed timestamp

<img width="938" height="946" alt="advanced-hunting-powershell-summary" src="https://github.com/user-attachments/assets/0477189e-b7d7-4c0a-82a0-c59b2ec49b69" />


This demonstrated how endpoint telemetry can be transformed into a structured investigation dataset using Kusto Query Language.


## Advanced Hunting

Microsoft Defender Advanced Hunting was used to investigate endpoint telemetry beyond the automatically generated alerts.

The objective was to identify activity patterns that could provide additional security context during the investigation.

The Advanced Hunting process followed:

    Endpoint Telemetry
          |
          v
    Advanced Hunting
          |
          v
    KQL Query
          |
          v
    Event Filtering
          |
          v
    Activity Correlation
          |
          v
    Security Assessment


## Cross-Workload Hunting

A cross-workload query was used to determine what security telemetry was available across the Microsoft Defender environment.

The query returned:

**35 events**

The results were distributed as follows:

| Security Workload | Events |
|---|---:|
| Endpoint | 33 |
| Email | 2 |
| Cloud Apps | 0 |
| Identity | 0 |
| **Total** | **35** |

<img width="936" height="941" alt="cross-workload-hunting-summary" src="https://github.com/user-attachments/assets/2505097b-ed5d-4ee7-a53f-8f7f61d046b4" />


The results demonstrated that endpoint telemetry represented the largest available source of events within the selected query window.

Email telemetry was also present, while the query did not return Cloud Apps or Identity events.

The absence of events from a workload was treated as a telemetry observation rather than automatically being interpreted as a configuration failure.


## Kusto Query Language

Kusto Query Language was used as the primary query language for Advanced Hunting.

KQL was used to:

- Filter security telemetry.
- Restrict events to a defined time period.
- Identify endpoint activity.
- Identify PowerShell execution.
- Group activity by device.
- Associate activity with user accounts.
- Count executions.
- Determine first-seen activity.
- Determine last-seen activity.

The use of KQL allowed the investigation to move from manually reviewing individual events to systematically analyzing endpoint telemetry.


## PowerShell Threat Hunt

A dedicated PowerShell threat hunt was performed using Advanced Hunting.

The purpose of the hunt was to proactively identify PowerShell execution activity within the available endpoint telemetry.

The hunt was not limited to the original security alert.

Instead, the query was used to search the broader endpoint telemetry for PowerShell activity.

The hunting workflow was:

    Endpoint Telemetry
          |
          v
    PowerShell Activity
          |
          v
    KQL Filtering
          |
          v
    Device Correlation
          |
          v
    Account Correlation
          |
          v
    Execution Count
          |
          v
    First / Last Seen
          |
          v
    Threat Assessment


<img width="948" height="944" alt="advanced-hunting-powershell-pid" src="https://github.com/user-attachments/assets/3ea16c8a-1b54-4ed6-834b-fee9ca57d681" />


## PowerShell Hunt Results

The PowerShell hunt identified seven executions within the available telemetry.

The results were summarized by device and account.

The analysis provided:

| Investigation Attribute | Result |
|---|---|
| PowerShell executions | 7 |
| Summarized results | 2 |
| Device correlation | Completed |
| Account correlation | Completed |
| First-seen activity | Identified |
| Last-seen activity | Identified |

<img width="1600" height="773" alt="mde-powershell-detection-alerts" src="https://github.com/user-attachments/assets/81dacbf7-42a6-48d8-92b6-c7085318508f" />


The result demonstrated the ability to use endpoint telemetry for proactive threat hunting rather than relying exclusively on Defender-generated alerts.


## Automated Investigation

Microsoft Defender automated investigation capabilities were evaluated during the endpoint investigation.

An automated investigation was manually initiated to analyze the available security activity.

The investigation produced an informational result that was subsequently resolved.

| Investigation | Severity | Status | Active Alerts |
|---|---|---|---|
| Automated investigation started manually | Informational | Resolved | 0 of 1 |


The automated investigation demonstrated how Defender can support analysts by performing additional investigation activities and presenting the results through the security operations workflow.


## Incident Response

The endpoint incident was managed through the Microsoft Defender XDR incident workflow.

The response process included:

- Alert review
- Incident triage
- Endpoint identification
- Device Timeline investigation
- Advanced Hunting
- PowerShell investigation
- Automated investigation
- Security assessment
- Incident management
- Resolution
- Endpoint validation

The endpoint execution incident was ultimately resolved.


At the completion of the investigation activities:

**0 active incidents**

were present in the environment.


## Endpoint Security Validation

The endpoint implementation was validated through multiple Defender views rather than relying on a single configuration screen.

Validation included:

- Device inventory
- Device health
- Exposure level
- Security alerts
- Device Timeline
- Incident investigation
- Advanced Hunting
- Automated investigation
- Endpoint status

The final endpoint state was:

| Validation Area | Result |
|---|---|
| Device visibility | Confirmed |
| Endpoint health | Active |
| Exposure level | 1 |
| Active alerts | 0 |
| Active incidents | 0 |
| Device Timeline | Available |
| Advanced Hunting | Completed |
| PowerShell hunting | Completed |
| Automated investigation | Completed |
| Incident response | Completed |



## Endpoint Security and Microsoft Defender XDR

Defender for Endpoint was not operated as an isolated endpoint product.

The endpoint security layer was integrated into the broader Microsoft Defender XDR security operations workflow.

The relationship can be represented as:

    Windows Endpoint
          |
          v
    Defender for Endpoint
          |
          +---- Telemetry
          |
          +---- Detection
          |
          +---- Device Timeline
          |
          +---- Investigation
          |
          v
    Microsoft Defender XDR
          |
          +---- Advanced Hunting
          |
          +---- Automated Investigation
          |
          +---- Incident Management
          |
          v
    Incident Response


This architecture allowed endpoint activity to become part of the broader security investigation process.


## Security Engineering Decisions

### Use the Endpoint as a Telemetry Source

The Windows endpoint was used not only as a protected asset but also as a source of security telemetry for investigation and threat hunting.

This allowed the project to demonstrate the operational value of endpoint detection and response.

### Validate Telemetry Before Investigation

Before drawing conclusions from the absence or presence of security events, the available telemetry was reviewed.

This prevented configuration assumptions from being treated as security evidence.

### Combine Automated Detection with Threat Hunting

The investigation did not stop at the generated incident.

Advanced Hunting and a dedicated PowerShell hunt were used to investigate activity beyond the initial detection.

### Use Device Timeline for Context

The Device Timeline was used to provide chronological context around the endpoint activity.

This helped establish a broader picture of what was occurring on the endpoint.

### Validate After Response

The endpoint was checked again after the investigation and resolution activities.

This confirmed that the device remained active and that no active endpoint alerts or incidents remained.


## Endpoint Security Limitations

The endpoint implementation was validated using the available endpoint infrastructure within the environment.

The project environment contained one active endpoint during the final validation period.

This limited the scale of endpoint correlation and prevented the project from demonstrating multi-endpoint attack propagation or lateral movement across a larger fleet.

The limitation was documented rather than artificially introducing additional endpoints solely to increase the apparent scope of the project.

A production implementation would onboard a broader endpoint fleet to provide greater telemetry coverage and improve detection and investigation capabilities.


## Final Endpoint Assessment

The endpoint security implementation successfully established Microsoft Defender for Endpoint as the endpoint detection and response layer of the Enara Health Services security architecture.

The implementation demonstrated:

- Endpoint onboarding
- Endpoint visibility
- Endpoint health monitoring
- Security telemetry collection
- Alert investigation
- Device Timeline analysis
- Advanced Hunting
- KQL-based investigation
- PowerShell threat hunting
- Automated investigation
- Incident management
- Incident resolution
- Final endpoint validation

The endpoint investigation also provided practical evidence of the complete detection-to-response workflow:

    Endpoint Activity
          |
          v
    Detection
          |
          v
    Alert
          |
          v
    Investigation
          |
          v
    Device Timeline
          |
          v
    Advanced Hunting
          |
          v
    Threat Hunting
          |
          v
    Automated Investigation
          |
          v
    Incident Response
          |
          v
    Resolution
          |
          v
    Endpoint Validation

The final endpoint state confirmed that the device remained active, had an exposure level of 1, and had no active alerts or incidents at the time of final validation.
