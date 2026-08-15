# Incident Response and Investigation

## Overview

Microsoft Defender XDR was used to investigate and manage the security incidents generated during the Enara Health Services implementation.

The incident-response activities focused on reviewing security alerts, investigating the affected endpoint, analyzing available telemetry, reviewing automated investigation results, and resolving the resulting incidents.

The incident-response workflow was:

    Security Activity
            |
            v
    Alert
            |
            v
    Incident
            |
            v
    Investigation
            |
            +-------------------+
            |                   |
            v                   v
    Endpoint Investigation   Advanced Hunting
            |                   |
            +---------+---------+
                      |
                      v
             Automated Investigation
                      |
                      v
              Security Assessment
                      |
                      v
                 Resolution
                      |
                      v
                  Validation


## Incident Response Objectives

The incident-response work focused on:

- Reviewing security incidents generated within Microsoft Defender.
- Identifying the affected endpoint.
- Reviewing incident severity and available alert information.
- Investigating endpoint activity.
- Using Device Timeline during investigation.
- Using Advanced Hunting to examine available telemetry.
- Investigating PowerShell activity.
- Reviewing automated investigation results.
- Resolving investigated incidents.
- Confirming the final incident state.


## Incidents Investigated

Two security investigation activities were completed during the implementation.

| Security Activity | Severity | Score | Status | Active Alerts |
|---|---|---:|---|---|
| Execution incident on one endpoint | Medium | 36 | Resolved | 0 / 2 |
| Automated investigation started manually | Informational | 16 | Resolved | 0 / 1 |

<img width="941" height="945" alt="-xdr-incident-resolved-security-testing" src="https://github.com/user-attachments/assets/4c5533d3-bae3-40c6-8fc6-b110c09b083f" />



## Execution Incident Investigation

The primary endpoint investigation involved an execution-related incident on one endpoint.

The observed incident information was:

- Severity: Medium
- Score: 36
- Status: Resolved
- Active alerts: 0 of 2


The incident was used as the starting point for a broader endpoint investigation.

The investigation did not stop at the incident summary.

Additional endpoint activity was reviewed to provide context around the security event.


## Endpoint Investigation

The affected endpoint was examined as part of the incident investigation.

The investigation included reviewing the endpoint's available activity and security information.

The Device Timeline was used to examine activity associated with the endpoint.

<img width="943" height="938" alt="xdr-incident-correlation-graph" src="https://github.com/user-attachments/assets/92c8afe3-dbcb-4288-aff3-0ec89a41a3d5" />


The timeline provided additional context for the investigation and allowed endpoint activity to be reviewed in chronological order.


## Advanced Hunting During Investigation

Advanced Hunting was used to examine the security telemetry available in the environment.

The cross-workload investigation returned:

**35 events**

The results were:

| Security Workload | Events |
|---|---:|
| Endpoint | 33 |
| Email | 2 |
| Cloud Apps | 0 |
| Identity | 0 |
| **Total** | **35** |

<img width="1600" height="788" alt="cross-workload-advanced-hunting-results" src="https://github.com/user-attachments/assets/6e50fd3d-94cd-4c68-ad82-01e445bb030e" />


The endpoint represented the majority of the telemetry returned by the investigation.

The results were used as additional context during the security investigation.


## PowerShell Investigation

PowerShell activity was investigated using Advanced Hunting.

The investigation identified:

**7 PowerShell executions**

The results were summarized into:

**2 results**

The available investigation information included:

- Device
- Account
- PowerShell execution count
- First observed activity
- Last observed activity

<img width="938" height="946" alt="advanced-hunting-powershell-summary" src="https://github.com/user-attachments/assets/6521c669-9cdf-4d16-990e-83eec4beddf5" />


This provided additional visibility into endpoint activity beyond the initial incident.


## Automated Investigation

A manual automated investigation was initiated within Microsoft Defender.

The resulting investigation was classified as:

- Informational
- Score: 16
- Status: Resolved
- Active alerts: 0 of 1



The automated investigation formed part of the overall incident investigation workflow.

Its result was reviewed before the investigation activity was considered resolved.


## Incident Resolution

The investigated security activities were resolved after review.

The final state was:

| Investigation | Final Status |
|---|---|
| Execution incident | Resolved |
| Automated investigation | Resolved |
| Active incidents | 0 |
| Active alerts | 0 |



The final Defender environment showed:

**0 active incidents**

at the time of validation.


## Incident Response Workflow

The practical incident-response workflow used during the project was:

    Detection
       |
       v
    Incident Review
       |
       v
    Identify Affected Endpoint
       |
       v
    Review Device Activity
       |
       v
    Device Timeline
       |
       v
    Advanced Hunting
       |
       v
    PowerShell Investigation
       |
       v
    Automated Investigation
       |
       v
    Analyst Review
       |
       v
    Resolution
       |
       v
    Final Validation


This workflow provided a structured approach to investigating the security activity observed within the environment.


## Final Incident Validation

After the investigations were completed, the environment was reviewed to confirm the final incident state.

The final validation showed:

| Validation Area | Result |
|---|---|
| Execution incident | Resolved |
| Automated investigation | Resolved |
| Active incidents | 0 |
| Active alerts | 0 |
| Active endpoint | 1 |
| Endpoint health | Active |
| Endpoint exposure level | 1 |




## Incident Response Results

The completed incident-response activities produced the following measurable results:

| Metric | Result |
|---|---:|
| Security investigation activities | 2 |
| Execution incident severity | Medium |
| Execution incident score | 36 |
| Automated investigation severity | Informational |
| Automated investigation score | 16 |
| Advanced Hunting events | 35 |
| Endpoint events | 33 |
| Email events | 2 |
| PowerShell executions identified | 7 |
| PowerShell summarized results | 2 |
| Resolved investigations | 2 |
| Active incidents after investigation | 0 |
| Active alerts after investigation | 0 |


## Security Engineering Observations

The incident investigation demonstrated that an alert should be treated as the starting point of an investigation rather than the conclusion.

The execution incident was investigated through additional endpoint activity, Device Timeline analysis, Advanced Hunting, PowerShell investigation, and automated investigation.

This provided multiple sources of context before the incident was resolved.

The investigation also demonstrated the importance of validating the final state after response activities.

Rather than assuming that resolution completed the workflow, the environment was reviewed again and confirmed to have:

- 0 active incidents.
- 0 active alerts.
- An active endpoint.
- An endpoint exposure level of 1.


## Incident Response Limitations

The incident-response documentation is limited to the investigation activities and results actually observed within the project environment.

The project did not attempt to simulate additional incidents simply to increase the number of documented cases.

The two investigation activities documented here represent the security activities that were actually generated, investigated, and resolved during the implementation.


## Final Incident Response Assessment

The Microsoft Defender XDR incident-response workflow was successfully exercised within the Enara Health Services environment.

The implementation demonstrated practical experience with:

- Incident review
- Alert investigation
- Endpoint investigation
- Device Timeline analysis
- Advanced Hunting
- KQL-based investigation
- PowerShell investigation
- Automated investigation
- Incident resolution
- Final security validation

The final state of the environment showed:

**0 active incidents**

and

**0 active alerts**

after the completed investigation activities.

This provided measurable evidence that the implemented Microsoft Defender security environment could support an end-to-end investigation and incident-response workflow.
