# Microsoft Defender for Cloud Apps Implementation

## Overview

Microsoft Defender for Cloud Apps was implemented as the cloud application security component of the Enara Health Services security environment.

The implementation focused on the Defender for Cloud Apps capabilities that were available within the tenant and were actually configured or reviewed during the project.

The Cloud Apps security layer was also considered as part of the broader Microsoft Defender XDR architecture.

The implementation included work around:

- Defender for Cloud Apps
- App Governance
- Cloud Discovery
- Defender for Endpoint integration
- Cloud application security visibility
- Available application security controls

## Objectives

The Defender for Cloud Apps implementation was designed to:

- Establish cloud application security visibility.
- Review the available cloud application security capabilities.
- Configure App Governance.
- Review Cloud Discovery.
- Configure the available Defender for Endpoint integration.
- Understand how cloud application security contributes to the broader Microsoft Defender XDR environment.
- Validate the available Cloud Apps security information.

## Defender for Cloud Apps

Microsoft Defender for Cloud Apps was used as the cloud application security layer within the project environment.

The position of the service within the overall security architecture was:

    Cloud Applications
            |
            v
    Microsoft Defender for Cloud Apps
            |
            +---- Cloud Discovery
            |
            +---- App Governance
            |
            +---- Application Security
            |
            +---- Defender for Endpoint Integration
            |
            v
    Microsoft Defender XDR

<img width="944" height="945" alt="app-governance-before-enable" src="https://github.com/user-attachments/assets/1d133da3-19cf-4190-b966-b6c1a640f2bd" />


## App Governance

App Governance was reviewed and configured within Microsoft Defender for Cloud Apps.

The capability provided a dedicated area for managing and monitoring applications connected to the organization's cloud environment.

The App Governance configuration formed part of the cloud application security implementation.



## Cloud Discovery

Cloud Discovery was reviewed as part of the Defender for Cloud Apps implementation.

Cloud Discovery provides visibility into cloud application usage and can be used to identify applications being used within an organization.

The Cloud Discovery capability was configured and reviewed within the environment.

<img width="937" height="945" alt="app-governance-enabled" src="https://github.com/user-attachments/assets/0d2dba9a-493f-4034-a228-0d8a4a5c4049" />


During the Advanced Hunting investigation performed in the project, the selected cross-workload query returned:

**0 Cloud Apps events**

The complete result was:

| Security Workload | Events |
|---|---:|
| Endpoint | 33 |
| Email | 2 |
| Cloud Apps | 0 |
| Identity | 0 |
| Total | 35 |

This result was documented as an observation about the available telemetry during the investigation.

It was not treated as evidence that Defender for Cloud Apps itself was incorrectly configured.

## Defender for Endpoint Integration

The available integration between Microsoft Defender for Endpoint and Microsoft Defender for Cloud Apps was reviewed during the implementation.

This integration was relevant to the overall security architecture because endpoint activity and cloud application security can contribute to a broader security investigation.

The integration was reviewed as part of the Cloud Apps configuration.

<img width="941" height="944" alt="cloud-apps-mde-integration" src="https://github.com/user-attachments/assets/c0da469d-3e6a-43dc-a80f-8ed5f4126515" />


The integration was not represented as a separate security platform.

Instead, it formed part of the relationship between endpoint security and cloud application security within the broader Microsoft Defender ecosystem.

## Cloud Application Security Architecture

The Cloud Apps component was positioned within the overall architecture as follows:

    Cloud Application Activity
              |
              v
    Defender for Cloud Apps
              |
              +---- Application Visibility
              |
              +---- Cloud Discovery
              |
              +---- App Governance
              |
              +---- Available Integrations
              |
              v
    Microsoft Defender XDR
              |
              v
    Security Investigation

This architecture allows cloud application security to contribute to the wider security operations workflow.

## Cloud Apps and Advanced Hunting

Advanced Hunting was also used to examine the available security telemetry across the Defender environment.

The selected investigation returned:

**0 Cloud Apps events**

This result was recorded alongside the other workload results:

- Endpoint: 33
- Email: 2
- Cloud Apps: 0
- Identity: 0
- Total: 35

<img width="1600" height="788" alt="cross-workload-advanced-hunting-results" src="https://github.com/user-attachments/assets/a33d112d-3256-4ceb-886d-5fd1bcdc8906" />


The absence of Cloud Apps events in this particular result was treated as a limitation of the available telemetry for the selected investigation rather than as an indication that the Defender for Cloud Apps service was unavailable.

## Cloud Application Security Validation

The Defender for Cloud Apps implementation was reviewed through the available configuration and security views.

The validation focused on:

- Defender for Cloud Apps availability.
- App Governance configuration.
- Cloud Discovery configuration.
- Defender for Endpoint integration.
- Available cloud application security visibility.
- Cloud Apps telemetry available through Advanced Hunting.

The implementation was therefore validated through both configuration evidence and the telemetry available within the environment.

## Observed Results

The Cloud Apps implementation produced the following observed results:

| Area | Observed Result |
|---|---|
| Defender for Cloud Apps | Available |
| App Governance | Configured / reviewed |
| Cloud Discovery | Configured / reviewed |
| Defender for Endpoint integration | Reviewed / configured |
| Cloud Apps events in selected Advanced Hunting query | 0 |

<img width="945" height="940" alt="defender-cloud-apps-integration-enabled" src="https://github.com/user-attachments/assets/e336529a-8979-44f8-beb8-9b2a6b809829" />


## Environmental Limitation

The project environment did not produce Cloud Apps events in the selected Advanced Hunting investigation.

Because the purpose of the project was to document the actual implementation, no artificial cloud application activity was introduced simply to create additional telemetry.

The absence of Cloud Apps events was therefore retained as an environmental observation.

This is important when evaluating a security implementation because configuration and telemetry are separate considerations.

A security service can be configured and available while the environment does not generate enough activity for a particular query or dashboard to return meaningful results.

## Security Engineering Decision

The Defender for Cloud Apps implementation was kept aligned with the actual cloud environment.

The service was not presented as having generated security detections or application discovery results that were not observed.

Instead, the documentation distinguishes between:

- Capabilities that were configured.
- Capabilities that were reviewed.
- Telemetry that was actually observed.
- Results that were not available during validation.

This ensures that the final architecture accurately represents the implemented environment.

## Final Cloud Application Security State

The Defender for Cloud Apps component formed part of the completed Enara Health Services security architecture.

The implementation included:

- Defender for Cloud Apps.
- App Governance configuration.
- Cloud Discovery configuration and review.
- Defender for Endpoint integration.
- Cloud application security visibility.
- Review of available Cloud Apps telemetry through Advanced Hunting.

The final investigation returned zero Cloud Apps events within the selected Advanced Hunting results.

The Cloud Apps implementation was therefore documented according to the actual configuration and telemetry available within the project environment rather than assuming application activity that was not observed.
