# Validation Report

## Overview

This validation report summarizes the final state of the Microsoft Defender XDR security environment implemented for Enara Health Services.

The validation was performed using the security configuration, telemetry, investigation results, incident status, endpoint status, threat-hunting results, Attack Simulation Training results, and security posture information observed during the project.

The purpose of this report is to provide evidence that the implemented security capabilities were reviewed and validated based on the actual environment.

## Validation Scope

The final validation covered:

- Microsoft Entra ID identity security
- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Defender for Cloud Apps
- Microsoft Defender XDR
- Advanced Hunting
- PowerShell threat hunting
- Automated investigation
- Incident investigation
- Attack Simulation Training
- Endpoint health
- Security posture
- Secure Score

## Final Security State

The final environment showed:

| Security Area | Final Result |
|---|---|
| Active incidents | 0 |
| Active endpoint alerts | 0 |
| Active endpoints | 1 |
| Endpoint health | Active |
| Endpoint exposure level | 1 |
| Execution incident | Resolved |
| Automated investigation | Resolved |
| Attack Simulation Training | Completed |
| Advanced Hunting events | 35 |
| PowerShell executions identified | 7 |
| PowerShell summarized results | 2 |

<img width="1600" height="795" alt="defender-xdr-identity-security-overview" src="https://github.com/user-attachments/assets/7af6cbbf-cb06-4029-8f52-202efe84b7b8" />


## Identity Security Validation

Microsoft Entra ID was validated as the identity foundation of the environment.

The identity security assessment showed:

| Identity Security Metric | Result |
|---|---:|
| Entra ID human identities | 7 |
| Entra ID non-human identities | 8 |
| Human identities | 14 |
| Non-human identities | 8 |
| Entra ID coverage score | 100% |
| Protected identities | 1 |
| Identities requiring attention | 0 |
| Identities not protected | 0 |


The results provided evidence of the identity security state observed during final validation.

## Endpoint Security Validation

The Windows endpoint was validated through Microsoft Defender for Endpoint.

The final endpoint state was:

| Endpoint Metric | Result |
|---|---|
| Active devices | 1 |
| Health state | Active |
| Exposure level | 1 |
| Active alerts | 0 |
| Active incidents | 0 |
| First seen | August 7, 2026 |
| Last seen | August 10, 2026 |



The endpoint remained active after the completed investigation activities.

## Incident Validation

Two security investigation activities were reviewed during the project.

| Investigation | Severity | Score | Status | Active Alerts |
|---|---|---:|---|---|
| Execution incident on one endpoint | Medium | 36 | Resolved | 0 / 2 |
| Automated investigation started manually | Informational | 16 | Resolved | 0 / 1 |


After the investigation activities were completed:

**0 active incidents**

were present in the environment.

## Advanced Hunting Validation

Advanced Hunting was used to validate the security telemetry available within the Microsoft Defender environment.

The cross-workload investigation returned:

**35 events**

The observed distribution was:

| Security Workload | Events |
|---|---:|
| Endpoint | 33 |
| Email | 2 |
| Cloud Apps | 0 |
| Identity | 0 |
| **Total** | **35** |


The results demonstrated that endpoint telemetry represented the majority of the events returned by the selected investigation.

## PowerShell Threat Hunting Validation

A dedicated PowerShell threat hunt was completed using Advanced Hunting.

The investigation identified:

**7 PowerShell executions**

and produced:

**2 summarized results**

The available results included device and account context together with execution counts and observed timestamps.


The result provided evidence that the available endpoint telemetry could be queried and analyzed for specific activity patterns.

## Automated Investigation Validation

A manual automated investigation was initiated and subsequently resolved.

The observed result was:

| Attribute | Result |
|---|---|
| Investigation | Automated investigation started manually |
| Severity | Informational |
| Score | 16 |
| Status | Resolved |
| Active alerts | 0 / 1 |


This provided evidence that the automated investigation capability was exercised during the project.

## Attack Simulation Validation

The Attack Simulation Training exercise was completed successfully.

The simulation was:

**Phishing Awareness Reporting Test**

The observed results were:

| Simulation Result | Result |
|---|---:|
| Status | Completed |
| Messages successfully received | 1 / 1 |
| Messages read | 0 / 1 |
| Messages replied to | 0 / 1 |
| Messages forwarded | 0 / 1 |
| Users compromised | 0% |
| Users reported simulation | 0% |
| Users who had not experienced simulation | 83% |


The results demonstrate completion of the simulation and the activity recorded by the platform.

The 83% coverage observation was retained as a limitation of the simulation coverage rather than interpreting the exercise as an organization-wide assessment.

## Cloud Application Security Validation

Microsoft Defender for Cloud Apps was reviewed as part of the final security environment.

The implementation included the Cloud Apps capabilities that were actually configured and reviewed during the project.

The selected Advanced Hunting investigation returned:

**0 Cloud Apps events**


The absence of Cloud Apps events in the selected investigation was recorded as an observation about available telemetry.

No artificial activity was generated solely to create additional Cloud Apps events.

## Secure Score Validation

Microsoft Defender Secure Score was reviewed as part of the final security posture assessment.

The observed scores were:

| Security Area | Score |
|---|---:|
| Overall Secure Score | 48.86% |
| Identity | 56.60% |
| Endpoint | 49.15% |
| Applications | 43.51% |

<img width="1360" height="941" alt="defender-xdr-final-security-posture" src="https://github.com/user-attachments/assets/46fbf8d6-2518-4c1e-9ab1-ea8044e1828c" />


The Secure Score was treated as a security posture baseline and improvement indicator.

The score was not used as the sole measurement of whether the project implementation was successful.

## Final Validation Summary

The complete validation results were consolidated below.

| Validation Area | Result |
|---|---|
| Microsoft Entra ID | Validated |
| Identity coverage | 100% |
| Microsoft Defender for Endpoint | Validated |
| Endpoint health | Active |
| Endpoint exposure level | 1 |
| Microsoft Defender for Office 365 | Implemented / reviewed |
| Microsoft Defender for Cloud Apps | Implemented / reviewed |
| Microsoft Defender XDR | Operational |
| Advanced Hunting | Completed |
| Cross-workload events | 35 |
| PowerShell executions identified | 7 |
| PowerShell summarized results | 2 |
| Automated investigation | Resolved |
| Execution incident | Resolved |
| Attack Simulation Training | Completed |
| Active incidents | 0 |
| Active alerts | 0 |
| Overall Secure Score | 48.86% |

## Evidence-Based Validation Approach

The project was validated using observable evidence rather than relying exclusively on configuration status.

The validation process followed:

    Configuration
          |
          v
    Security Activity
          |
          v
    Telemetry
          |
          v
    Investigation
          |
          v
    Security Results
          |
          v
    Final Validation

This approach ensured that the final assessment was based on what was actually visible and measurable within the environment.

## Environmental Limitations

The final validation also documented limitations identified during implementation.

### Endpoint Coverage

The final environment contained one active endpoint.

Therefore, the project did not attempt to demonstrate multi-endpoint correlation or large-scale endpoint investigation.

### Cloud Apps Telemetry

The selected Advanced Hunting investigation returned zero Cloud Apps events.

The result was documented as observed telemetry rather than artificially generating application activity.

### Identity Telemetry

The selected Advanced Hunting investigation returned zero Identity events.

This was treated as a result of the specific telemetry query and environment rather than automatically interpreted as a failure of the identity security implementation.

### Attack Simulation Coverage

The completed phishing-awareness simulation showed that 83% of users had not experienced the simulation.

Therefore, the simulation results should not be interpreted as a complete organization-wide awareness assessment.

### Security Score

The overall Secure Score was 48.86%.

The score represents the security posture observed during validation and provides an improvement baseline rather than a binary measure of project completion.

## Final Assessment

The validation activities demonstrated that the implemented environment was operational across the major security capabilities included in the project.

The environment supported:

- Identity security
- Endpoint security
- Email security
- Cloud application security
- Security telemetry
- Advanced Hunting
- PowerShell threat hunting
- Automated investigation
- Incident investigation
- Incident resolution
- Attack Simulation Training
- Security posture assessment

The final incident state showed:

**0 active incidents**

and:

**0 active endpoint alerts**

The active endpoint remained healthy with an exposure level of 1.

The completed Advanced Hunting activities produced measurable telemetry, including 35 cross-workload events and 7 identified PowerShell executions.

The project therefore reached its intended validation stage based on the capabilities and evidence available within the environment.

## Final Project Status

**Status: Completed**

The Microsoft Defender XDR Security Architecture for Enara Health Services was implemented, investigated, validated, and documented.

The final validation reflects the actual configuration, telemetry, security investigations, results, and environmental limitations observed during the project.
