# Microsoft Defender XDR Security Architecture for Enara Health Services

<p align="center">

![Microsoft Defender XDR](https://img.shields.io/badge/Microsoft%20Defender%20XDR-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Microsoft Entra ID](https://img.shields.io/badge/Microsoft%20Entra%20ID-5E5CE6?style=for-the-badge&logo=microsoft&logoColor=white)
![Defender for Endpoint](https://img.shields.io/badge/Defender%20for%20Endpoint-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Defender for Office 365](https://img.shields.io/badge/Defender%20for%20Office%20365-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Defender for Cloud Apps](https://img.shields.io/badge/Defender%20for%20Cloud%20Apps-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![KQL](https://img.shields.io/badge/KQL-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Cloud Security](https://img.shields.io/badge/Cloud%20Security-Engineering-2E7D32?style=for-the-badge)
![Security Operations](https://img.shields.io/badge/Security%20Operations-SOC-6A1B9A?style=for-the-badge)

</p>

## Project Overview

I designed and implemented this project to gain hands-on experience engineering a cloud-native security environment using Microsoft Defender XDR.

The project was developed around a healthcare organization scenario, **Enara Health Services**, with the goal of building an integrated security architecture capable of protecting cloud identities, endpoints, email and collaboration workloads, and cloud applications.

Rather than stopping at the configuration of individual Microsoft security services, I built the environment around the security operations lifecycle:

> **Identity → Protection → Detection → Investigation → Threat Hunting → Response → Validation**

The implementation involved configuring Microsoft Entra ID security controls, onboarding a Windows endpoint into Microsoft Defender for Endpoint, configuring Microsoft Defender for Office 365 protections, implementing Microsoft Defender for Cloud Apps capabilities, and using Microsoft Defender XDR as the centralized security operations and investigation platform.

After establishing the security controls, I used the environment to perform actual security investigations.

I investigated an endpoint execution incident involving PowerShell activity, reviewed the affected device, examined the device timeline, performed Advanced Hunting using Kusto Query Language (KQL), conducted a dedicated PowerShell threat hunt, reviewed automated investigation activity, and managed the resulting incidents through resolution.

I also implemented a controlled phishing-awareness simulation using Attack Simulation Training to validate the security-awareness capabilities of the environment.

One of the important aspects of the implementation was working with the limitations of a cloud-native environment.

Some Microsoft Defender capabilities depend on infrastructure or telemetry that was not available in the tenant. Instead of introducing unnecessary infrastructure or generating artificial security data, I documented these limitations and redesigned the final architecture to represent the environment that was actually implemented and validated.

The resulting environment demonstrates an end-to-end cloud security and security operations workflow:

> **Microsoft Entra ID → Security Workloads → Security Telemetry → Microsoft Defender XDR → Investigation → Threat Hunting → Incident Response → Validation**

## Project Objectives

I designed the project around the following objectives:

- Establish Microsoft Entra ID as the primary cloud identity security foundation.
- Configure identity security controls including Multi-Factor Authentication, Conditional Access, and Privileged Identity Management.
- Onboard a Windows endpoint into Microsoft Defender for Endpoint.
- Validate endpoint telemetry and security monitoring.
- Investigate endpoint security alerts and incidents.
- Analyze endpoint activity using the Defender device timeline.
- Configure Microsoft Defender for Office 365 security protections.
- Implement Microsoft Defender for Cloud Apps security and governance capabilities.
- Integrate Microsoft Defender for Endpoint with Defender for Cloud Apps.
- Enable App Governance and relevant cloud application security controls.
- Establish Microsoft Defender XDR as the centralized security operations platform.
- Perform Advanced Hunting using KQL.
- Conduct cross-workload threat hunting.
- Develop and execute a dedicated PowerShell threat hunt.
- Review automated security investigation capabilities.
- Investigate and resolve security incidents.
- Implement and evaluate Attack Simulation Training.
- Validate endpoint health and the final security posture.
- Document environmental limitations and architectural decisions.
- Redesign the final architecture based on the capabilities actually implemented.

## Project Scope

The implementation covered four primary security domains:

### Identity Security

Microsoft Entra ID was used to provide:

- Identity management
- Authentication and access controls
- Multi-Factor Authentication
- Conditional Access
- Privileged Identity Management
- Identity security visibility

### Endpoint Security

Microsoft Defender for Endpoint was used for:

- Endpoint onboarding
- Endpoint telemetry
- Detection
- Alert investigation
- Device timeline analysis
- Automated investigation
- Threat hunting
- Incident response
- Endpoint health validation

### Email Security

Microsoft Defender for Office 365 was used for:

- Anti-phishing protection
- Impersonation protection
- Safe Links
- Safe Attachments
- Email security investigation
- Attack Simulation Training

### Cloud Application Security

Microsoft Defender for Cloud Apps was used for:

- Cloud application security
- Cloud Discovery configuration
- App Governance
- Conditional Access App Control
- Defender for Endpoint integration
- Application security visibility


## Technologies and Services

| Technology / Service | Purpose |
|---|---|
| Microsoft Defender XDR | Centralized security operations, detection, investigation, and incident management |
| Microsoft Entra ID | Cloud identity and access security |
| Microsoft Defender for Endpoint | Endpoint detection and response |
| Microsoft Defender for Office 365 | Email and collaboration protection |
| Microsoft Defender for Cloud Apps | Cloud application security and governance |
| Microsoft 365 | Cloud productivity and collaboration workloads |
| Advanced Hunting | Security telemetry investigation and threat hunting |
| Kusto Query Language (KQL) | Security query and threat hunting language |
| Attack Simulation Training | Security-awareness validation |
| Conditional Access | Identity-based access control |
| Privileged Identity Management | Privileged access management |
| Microsoft Information Protection | Information protection integration |
| App Governance | Cloud application governance |
| Device Timeline | Endpoint activity investigation |
| Automated Investigation | Automated security investigation |


## Architecture

The final architecture was designed around Microsoft Defender XDR as the centralized security operations and investigation layer.

The design follows a layered cloud security model in which identity, endpoint, email, and cloud application controls provide protection across different areas of the environment, while Microsoft Defender XDR provides centralized visibility, investigation, threat hunting, incident management, and response capabilities.

The architecture was finalized after implementation to ensure that it accurately represents the environment that was actually deployed and validated.

### Final Architecture Diagram

<img width="1536" height="1024" alt="archites" src="https://github.com/user-attachments/assets/c6004ae9-bac4-4f14-8bd1-26b59cba90ec" />


The architecture is organized around four primary security layers:

    Microsoft Entra ID
            |
            v
    Identity and Access Security
            |
            +----------------------------+
            |                            |
            v                            v
    Defender for Endpoint        Defender for Office 365
            |                            |
            +-------------+--------------+
                          |
                          v
                Defender for Cloud Apps
                          |
                          v
                 Microsoft Defender XDR
                          |
              +-----------+-----------+
              |                       |
              v                       v
       Advanced Hunting       Incident Investigation
              |                       |
              v                       v
       Threat Hunting         Automated Investigation
              |                       |
              +-----------+-----------+
                          |
                          v
                 Incident Response
                          |
                          v
                   Final Validation

### Architecture Design

The architecture was designed around the principle that each security workload should provide a specific defensive capability while contributing telemetry and security context to the broader Microsoft Defender XDR environment.

Microsoft Entra ID provides the identity security foundation.

Microsoft Defender for Endpoint provides endpoint detection, investigation, and response.

Microsoft Defender for Office 365 provides email and collaboration security.

Microsoft Defender for Cloud Apps provides cloud application visibility and governance.

Microsoft Defender XDR provides the centralized security operations layer used to investigate alerts, incidents, devices, and available security telemetry.

The resulting security model is:

    Identity
       |
       v
    Access Control
       |
       v
    Workload Protection
       |
       v
    Security Telemetry
       |
       v
    Detection
       |
       v
    Investigation
       |
       v
    Threat Hunting
       |
       v
    Incident Response
       |
       v
    Validation

## Security Architecture Principles

### Identity-Centric Security

Microsoft Entra ID was established as the primary identity and access security layer.

Identity was treated as a foundational security boundary rather than simply an administrative component. Authentication, access control, privileged access, and identity visibility were incorporated into the overall security architecture.

The implemented identity controls included:

- Multi-Factor Authentication
- Conditional Access
- Privileged Identity Management
- Role-based access control
- Identity security monitoring

<img width="1600" height="795" alt="defender-xdr-identity-security-overview" src="https://github.com/user-attachments/assets/7817359d-8576-4266-b79a-59d8a40fc47f" />


### Layered Workload Protection

The environment was protected through multiple Microsoft security workloads rather than relying on a single security product.

Microsoft Defender for Endpoint was used to protect and monitor the Windows endpoint.

Microsoft Defender for Office 365 was used to establish email security controls.

Microsoft Defender for Cloud Apps was used to provide cloud application security and governance capabilities.

Microsoft Defender XDR provided the centralized security operations layer across the available workloads.

This created a defense-in-depth architecture in which security controls operate at different points of the attack surface.

### Centralized Security Operations

Microsoft Defender XDR was used as the central investigation and incident-management platform.

The operational workflow was structured around:

    Detection
        |
        v
    Alert Triage
        |
        v
    Investigation
        |
        v
    Threat Hunting
        |
        v
    Response
        |
        v
    Resolution
        |
        v
    Validation

This allowed the environment to be operated as an integrated security operations platform rather than as a collection of independent security services.

### Telemetry-Driven Security

A key part of the implementation was determining whether the configured security controls were producing usable security telemetry.

I did not treat a connector, integration, or security setting being enabled as sufficient evidence of successful implementation.

Instead, I validated the environment by examining:

- Generated alerts
- Security incidents
- Endpoint activity
- Device timeline data
- Advanced Hunting results
- PowerShell activity
- Automated investigation results
- Attack Simulation results
- Endpoint health
- Final security posture

This provided evidence that the implemented capabilities were producing observable security outcomes within the available environment.

### Evidence-Based Validation

The implementation was validated using observable evidence rather than configuration status alone.

Evidence included:

- Security alerts
- Defender incidents
- Device activity
- Advanced Hunting results
- Automated investigation results
- Attack Simulation results
- Endpoint health
- Active incident state
- Security posture metrics

This approach provided measurable evidence that the implemented controls were functioning within the capabilities of the environment.

## Security Data Flow

The security data flow begins with identity and workload activity and progresses through detection, investigation, threat hunting, response, and validation.

### Identity and Access Flow

Microsoft Entra ID provides the identity context for users, administrators, privileged accounts, and cloud applications.

    User / Administrator
            |
            v
    Microsoft Entra ID
            |
            +---- Multi-Factor Authentication
            |
            +---- Conditional Access
            |
            +---- Privileged Identity Management
            |
            v
    Identity Security

<!-- Screenshot: 03-identity-security-controls.png -->

The identity layer establishes the access-control foundation for the cloud environment and provides identity context for subsequent security monitoring and investigation.

### Endpoint Security Flow

The Windows endpoint was onboarded into Microsoft Defender for Endpoint and used as the primary endpoint security telemetry source.

Endpoint activity was then available for detection, investigation, device timeline analysis, automated investigation, Advanced Hunting, and threat hunting.

    Windows Endpoint
           |
           v
    Microsoft Defender for Endpoint
           |
           +---- Endpoint Detection
           |
           +---- Security Alerts
           |
           +---- Device Timeline
           |
           +---- Automated Investigation
           |
           +---- Advanced Hunting
           |
           v
    Microsoft Defender XDR

<img width="1600" height="792" alt="defender-endpoint-settings" src="https://github.com/user-attachments/assets/91c7e92d-6f6b-475d-af7d-0c6fe96c1d3d" />


The endpoint security layer became particularly important during the investigation of the PowerShell-related execution incident.

### Email Security Flow

Microsoft Defender for Office 365 provided the email security layer.

    Email and Collaboration Workloads
                    |
                    v
         Defender for Office 365
                    |
                    +---- Anti-Phishing
                    |
                    +---- Impersonation Protection
                    |
                    +---- Safe Links
                    |
                    +---- Safe Attachments
                    |
                    +---- Email Investigation
                    |
                    v
           Microsoft Defender XDR


The email security configuration was also used as the foundation for the Attack Simulation Training exercise later in the implementation.

### Cloud Application Security Flow

Microsoft Defender for Cloud Apps provided the cloud application security and governance layer.

    Cloud Applications
            |
            v
    Defender for Cloud Apps
            |
            +---- Cloud Discovery
            |
            +---- App Governance
            |
            +---- Conditional Access App Control
            |
            +---- Defender for Endpoint Integration
            |
            v
    Microsoft Defender XDR

<img width="945" height="940" alt="defender-cloud-apps-integration-enabled" src="https://github.com/user-attachments/assets/1db7e24d-3727-49dd-9592-0100d65cd92a" />


Cloud application security was validated based on the capabilities and telemetry available within the tenant.

## Security Control Mapping

The major security requirements were mapped to the Microsoft security capabilities implemented in the environment.

| Security Requirement | Implemented Capability | Security Function |
|---|---|---|
| Identity protection | Microsoft Entra ID | Identity and access security |
| Strong authentication | Multi-Factor Authentication | Authentication security |
| Conditional access enforcement | Conditional Access | Access control |
| Privileged access protection | Privileged Identity Management | Privileged identity security |
| Endpoint protection | Microsoft Defender for Endpoint | Endpoint detection and response |
| Endpoint investigation | Device Timeline | Endpoint behavioral investigation |
| Email protection | Microsoft Defender for Office 365 | Email threat protection |
| Cloud application security | Microsoft Defender for Cloud Apps | SaaS visibility and governance |
| Centralized investigation | Microsoft Defender XDR | XDR security operations |
| Threat hunting | Advanced Hunting | Proactive detection and investigation |
| Security query | Kusto Query Language | Security telemetry analysis |
| Automated investigation | Microsoft Defender XDR | Investigation automation |
| Security awareness | Attack Simulation Training | Security-awareness validation |
| Incident response | Microsoft Defender XDR | Incident management and response |

## Cloud-Native Architecture Decision

One of the most important architectural decisions during the implementation was maintaining the environment as cloud-native.

The environment was built around Microsoft Entra ID rather than introducing traditional on-premises Active Directory infrastructure.

This decision was based on the actual environment available during implementation.

A traditional Active Directory domain controller was not present, and introducing one solely to support a specific Defender capability would have added infrastructure that was outside the requirements of the implemented architecture.

The resulting identity architecture was therefore:

    Cloud-Native Environment
            |
            v
    Microsoft Entra ID
            |
            v
    Cloud Identity Security
            |
            v
    Microsoft Defender XDR
            |
            +---- Endpoint Security
            |
            +---- Email Security
            |
            +---- Cloud Application Security
            |
            +---- Threat Hunting
            |
            +---- Incident Investigation
            |
            +---- Incident Response

This decision also meant that traditional Defender for Identity sensor deployment was not performed.

The capability was treated as an environmental limitation rather than being represented as an implemented component.

## Architecture Validation

The final architecture was reviewed against the capabilities that were actually implemented and validated.

| Component | Implementation State |
|---|---|
| Microsoft Entra ID | Implemented |
| Microsoft Defender for Endpoint | Implemented |
| Microsoft Defender for Office 365 | Implemented |
| Microsoft Defender for Cloud Apps | Implemented |
| Microsoft Defender XDR | Implemented |
| Advanced Hunting | Implemented |
| PowerShell Threat Hunting | Implemented |
| Automated Investigation | Validated |
| Attack Simulation Training | Completed |
| Incident Investigation | Validated |
| Incident Response | Validated |
| Endpoint Health Validation | Completed |

The final architecture therefore represents the implemented environment rather than a theoretical Microsoft security reference architecture.

## Implementation Approach

The implementation followed a progressive cloud security engineering approach.

### Phase 1 — Environment Assessment

I first assessed the available tenant capabilities, security workloads, identity environment, endpoint availability, and available Defender functionality.

This allowed the implementation to be planned around the actual environment instead of assuming that every Microsoft security feature would be available.

### Phase 2 — Identity Security

The identity layer was established using Microsoft Entra ID.

Security controls including MFA, Conditional Access, role-based access, and Privileged Identity Management were configured and reviewed.

### Phase 3 — Endpoint Security

A Windows endpoint was onboarded into Microsoft Defender for Endpoint.

The endpoint was then used to validate security telemetry, investigate activity, perform timeline analysis, and support threat-hunting activities.

### Phase 4 — Email Security

Microsoft Defender for Office 365 security controls were configured and reviewed.

This established the email protection layer and provided the foundation for the later security-awareness simulation.

### Phase 5 — Cloud Application Security

Microsoft Defender for Cloud Apps was configured to provide cloud application visibility and governance capabilities.

The available integration with Defender for Endpoint was also configured.

### Phase 6 — XDR Operations

Microsoft Defender XDR was then used as the centralized security operations layer.

The environment was used to investigate incidents, review alerts, perform Advanced Hunting, and analyze available telemetry across security workloads.

### Phase 7 — Threat Hunting and Investigation

The available telemetry was used to conduct proactive investigation.

This included:

- Cross-workload Advanced Hunting
- PowerShell threat hunting
- Endpoint investigation
- Device timeline analysis
- Automated investigation

### Phase 8 — Incident Response

Security incidents generated during the implementation were investigated and managed through the Defender XDR incident workflow.

The incidents were reviewed, investigated, and resolved.

### Phase 9 — Security Validation

The final environment was validated using:

- Active incident status
- Active alert status
- Endpoint health
- Exposure level
- Security telemetry
- Advanced Hunting results
- Attack Simulation results
- Secure Score
- Security workload configuration

### Phase 10 — Final Architecture Review

Finally, the architecture was reviewed against the actual implementation.

Components that depended on unavailable infrastructure or telemetry were documented as limitations rather than being presented as completed capabilities.

The overall implementation lifecycle was:

    Environment Assessment
            |
            v
    Identity Security
            |
            v
    Endpoint Security
            |
            v
    Email Security
            |
            v
    Cloud Application Security
            |
            v
    XDR Operations
            |
            v
    Detection and Investigation
            |
            v
    Threat Hunting
            |
            v
    Incident Response
            |
            v
    Security Validation
            |
            v
    Final Architecture Review



## Identity Security Implementation

Microsoft Entra ID was implemented as the identity foundation of the environment.

The objective was to establish identity security controls that reduce the risk associated with compromised credentials, excessive privileges, and unauthorized access to cloud resources.

The identity implementation focused on authentication security, access control, privileged access management, and identity visibility.

### Microsoft Entra ID Configuration

The tenant's default directory was used as the identity boundary for the environment.

I reviewed the available identities and configured the required identity security controls within the available Microsoft Entra capabilities.

The implementation included:

- User identity management
- Group-based access management
- Role-based access control
- Multi-Factor Authentication
- Conditional Access
- Privileged Identity Management
- Identity security monitoring


### Multi-Factor Authentication

Multi-Factor Authentication was incorporated into the identity security model to provide an additional authentication factor beyond the user's primary credentials.

This reduces the impact of credential compromise by requiring an additional verification mechanism before access is granted.

The MFA configuration was reviewed as part of the overall identity security validation.


### Conditional Access

Conditional Access was used as an identity-based access control mechanism.

The implementation was designed around the principle that access decisions should consider the security context of the authentication request rather than relying solely on valid credentials.

The Conditional Access configuration was reviewed to ensure that the required identity security controls were available and applied within the tenant.


### Privileged Identity Management

Privileged Identity Management was incorporated to strengthen the management of privileged roles.

The objective was to reduce unnecessary standing privilege and provide greater visibility and control over privileged access.

The implementation included reviewing privileged role assignments and the available PIM controls.

<img width="946" height="859" alt="xdr-admin-role" src="https://github.com/user-attachments/assets/49204226-df33-4919-a310-0dc90972241d" />


### Identity Security Validation

The identity security implementation was validated through the Microsoft Defender identity security view.

The final environment showed:

| Identity Security Metric | Result |
|---|---:|
| Entra ID human identities | 7 |
| Entra ID non-human identities | 8 |
| Human identities | 14 |
| Non-human identities | 8 |
| Entra ID coverage score | 100% |
| Protected identities | 1 |
| Needs attention | 0 |
| Not protected | 0 |

<img width="1600" height="795" alt="defender-xdr-identity-security-overview" src="https://github.com/user-attachments/assets/bf1e0aa4-ebaf-4f9f-9763-a0836b9c8a8d" />


The identity security results demonstrated that the available Entra ID identities were being represented within the Defender identity security layer.

## Endpoint Security Implementation

Microsoft Defender for Endpoint was implemented as the endpoint detection and response layer.

A Windows endpoint was onboarded into Defender for Endpoint and used as the primary endpoint telemetry source for the security investigation activities performed during the project.

The endpoint security implementation covered:

- Device onboarding
- Endpoint telemetry
- Endpoint detection
- Alert investigation
- Device timeline analysis
- Automated investigation
- Advanced Hunting
- PowerShell threat hunting
- Incident response
- Endpoint health validation

### Endpoint Onboarding

The Windows endpoint was onboarded into Microsoft Defender for Endpoint.

After onboarding, the device became visible within the Defender portal and began generating endpoint security telemetry.

The onboarding process was validated by confirming that the endpoint appeared within the Defender device inventory and that recent activity was being reported.

<img width="935" height="944" alt="defender-endpoint-device-onboarded" src="https://github.com/user-attachments/assets/00566934-f640-4ced-b69b-d60d024b2ccb" />


### Endpoint Security Status

The onboarded endpoint was monitored through the Microsoft Defender portal.

The device remained active and continued to report telemetry during the investigation period.

The final endpoint state showed:

| Endpoint Metric | Result |
|---|---|
| Health state | Active |
| Exposure level | 1 |
| Active alerts | 0 |
| Active incidents | 0 |
| First seen | August 7, 2026 |
| Last seen | August 10, 2026 |


### Endpoint Detection

The endpoint generated security activity that was investigated through Microsoft Defender XDR.

One of the significant investigation paths involved an execution-related incident on the endpoint.

The incident was classified as Medium severity and was subsequently investigated and resolved.

The investigation demonstrated the operational workflow from endpoint detection through investigation and incident resolution.


## Endpoint Investigation

After the endpoint alert was identified, I moved beyond the initial alert and investigated the affected device.

The investigation focused on understanding the activity surrounding the detection rather than treating the alert as an isolated event.

The investigation workflow included:

1. Reviewing the security alert.
2. Identifying the affected endpoint.
3. Reviewing the incident context.
4. Examining the device timeline.
5. Identifying related endpoint activity.
6. Performing Advanced Hunting.
7. Investigating PowerShell execution.
8. Reviewing automated investigation activity.
9. Managing the resulting incident.
10. Validating the endpoint after resolution.

This provided practical experience with the Defender for Endpoint investigation workflow.

### Device Timeline Analysis

The Defender device timeline was used to examine activity associated with the endpoint over time.

The timeline provided additional context around the detected activity and allowed related endpoint events to be reviewed chronologically.

This was particularly useful when investigating the PowerShell-related activity because the timeline provided visibility beyond the individual alert.


### PowerShell Activity Investigation

PowerShell activity was investigated using Microsoft Defender Advanced Hunting.

The objective was to identify PowerShell executions across the available endpoint telemetry and establish which devices and accounts were associated with the activity.

The resulting analysis identified:

**7 PowerShell executions**

The results were grouped using:

- Device name
- Account
- Number of PowerShell executions
- First observed timestamp
- Last observed timestamp

<img width="938" height="946" alt="advanced-hunting-powershell-summary" src="https://github.com/user-attachments/assets/e760de6e-78ad-411f-8bf7-c2e9259bf868" />


The hunting results demonstrated how endpoint telemetry can be transformed into a structured investigation dataset using KQL.

## Advanced Hunting

Microsoft Defender Advanced Hunting was used to perform proactive security analysis beyond the alerts automatically generated by the platform.

The environment was queried across available security workloads to determine what telemetry was available for investigation.

The cross-workload analysis returned **35 events**.

| Security Workload | Events |
|---|---:|
| Endpoint | 33 |
| Email | 2 |
| Cloud Apps | 0 |
| Identity | 0 |
| **Total** | **35** |

<img width="1600" height="788" alt="cross-workload-advanced-hunting-results" src="https://github.com/user-attachments/assets/51c36ec8-096f-401d-8793-fa069c5ecf71" />


The results demonstrated that endpoint and email telemetry were available for centralized investigation.

The absence of Cloud Apps and Identity events in this particular query was treated as a telemetry observation rather than as a configuration failure.

This distinction is important in a security engineering environment because the presence of a configured security workload does not guarantee that the workload will continuously generate queryable events.

## Kusto Query Language

Kusto Query Language was used as the primary query language for Advanced Hunting.

The queries were used to:

- Identify security events
- Filter telemetry by time range
- Investigate endpoint activity
- Identify PowerShell execution
- Group activity by device
- Associate activity with user accounts
- Establish first-seen and last-seen timestamps
- Count security events

A structured PowerShell hunting query was used to summarize executions by device and account.

The resulting output provided:

- Device name
- Account
- PowerShell execution count
- First observed execution
- Last observed execution

<img width="948" height="944" alt="advanced-hunting-powershell-pid" src="https://github.com/user-attachments/assets/d36cdd10-6942-4807-964d-b18ab9f2cb11" />


The use of KQL allowed the investigation to move from manually reviewing individual events to systematically analyzing security telemetry.

## Threat Hunting

Threat hunting was performed independently of the initial endpoint detection.

The purpose was to proactively search the available telemetry for PowerShell execution patterns that could require further investigation.

The hunting workflow was:

    Security Telemetry
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
    Device and Account Correlation
            |
            v
    Investigation
            |
            v
    Security Assessment

The hunt produced two summarized device/account results and identified seven PowerShell executions.

<img width="1600" height="773" alt="mde-powershell-detection-alerts" src="https://github.com/user-attachments/assets/40fea0c5-f7f3-4bf4-8dd3-8f3d4aece174" />


## Automated Investigation

Microsoft Defender XDR automated investigation capabilities were also evaluated during the project.

An automated investigation was manually initiated to examine security activity associated with the environment.

The investigation was subsequently represented within the Defender incident workflow.

The resulting informational incident was resolved after review.

| Investigation | Severity | Status |
|---|---|---|
| Automated investigation started manually | Informational | Resolved |


The automated investigation demonstrated how Defender can support analysts by performing investigation activities and presenting the resulting security context within the incident workflow.

## Incident Investigation and Response

Two security incidents were investigated during the implementation.

| Incident | Severity | Priority | Status |
|---|---|---:|---|
| Execution incident on one endpoint | Medium | 36 | Resolved |
| Automated investigation started manually | Informational | 16 | Resolved |

The incident response process included:

- Alert triage
- Incident review
- Endpoint investigation
- Device timeline analysis
- Advanced Hunting
- Automated investigation
- Security assessment
- Incident management
- Resolution
- Final validation


At the completion of the investigation and response activities:

**0 active incidents**

were present in the environment.

## Microsoft Defender for Office 365 Implementation

Microsoft Defender for Office 365 was implemented as the email and collaboration security layer.

The implementation focused on establishing available email protection capabilities and validating their configuration.

The security controls reviewed included:

- Anti-phishing protection
- Impersonation protection
- Safe Links
- Safe Attachments
- Email security policies
- Email investigation capabilities
- Attack Simulation Training


### Email Security Configuration

The available Defender for Office 365 security policies were reviewed and configured according to the security requirements of the environment.

The configuration was designed to reduce the risk of:

- Credential phishing
- Malicious links
- Malicious attachments
- User impersonation
- Email-based social engineering


The configured controls established the email security layer that was later used to support the phishing-awareness validation exercise.

## Microsoft Defender for Cloud Apps Implementation

Microsoft Defender for Cloud Apps was implemented as the cloud application security and governance layer.

The implementation included:

- Cloud Discovery
- App Governance
- Conditional Access App Control
- Defender for Endpoint integration
- Application security visibility
- Cloud application governance


### Defender for Endpoint Integration

The integration between Microsoft Defender for Endpoint and Microsoft Defender for Cloud Apps was configured.

This integration connects endpoint security context with cloud application security capabilities and allows endpoint information to contribute to cloud application visibility.

The integration was reviewed during the final configuration validation.

<img width="941" height="944" alt="cloud-apps-mde-integration" src="https://github.com/user-attachments/assets/0e6b8824-8713-44f1-8413-bb29c26f54c3" />


### App Governance

App Governance was configured within Defender for Cloud Apps.

The capability provides visibility and governance for cloud applications and application access within the environment.

The configuration was reviewed as part of the cloud application security implementation.

<img width="937" height="945" alt="app-governance-enabled" src="https://github.com/user-attachments/assets/24865e3a-ebc8-45cf-8dfd-12143cd14cca" />


### Cloud Discovery

Cloud Discovery was configured within Defender for Cloud Apps.

The feature provides visibility into cloud applications being used within an organization and can be used to identify Shadow IT and evaluate application risk.

During the implementation, the environment did not generate meaningful Cloud Discovery application telemetry.

Rather than artificially generating traffic to populate the Cloud Discovery dashboard, the limitation was documented as part of the final project.


This provides an important distinction between configuring a security capability and validating that the capability is receiving sufficient telemetry to produce meaningful results.

## Microsoft Defender XDR Operations

Microsoft Defender XDR served as the central security operations platform throughout the implementation.

The platform was used to:

- Review security alerts
- Investigate incidents
- Investigate endpoint activity
- Review automated investigations
- Perform Advanced Hunting
- Conduct threat hunting
- Manage incidents
- Validate security posture

The operational workflow was:

    Security Event
          |
          v
    Defender Detection
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
          +--------------------+
          |                    |
          v                    v
    Device Timeline      Advanced Hunting
          |                    |
          +---------+----------+
                    |
                    v
          Security Assessment
                    |
                    v
             Incident Response
                    |
                    v
                Resolution
                    |
                    v
                Validation

<img width="941" height="945" alt="-xdr-incident-resolved-security-testing" src="https://github.com/user-attachments/assets/755d6109-b3e3-4db3-8d3c-252b4bec23f5" />


The use of a centralized XDR workflow allowed security activity from the available Microsoft security workloads to be investigated through a common operational platform.

## Security Operations Validation

The security operations implementation was validated using actual investigation results.

The environment produced:

| Security Operations Metric | Result |
|---|---:|
| Advanced Hunting events | 35 |
| Endpoint events | 33 |
| Email events | 2 |
| PowerShell executions identified | 7 |
| Incidents investigated | 2 |
| Incidents resolved | 2 |
| Active incidents after response | 0 |
| Active endpoint alerts | 0 |

These results provided measurable evidence that the environment could support security monitoring, investigation, threat hunting, and incident response activities.



## Attack Simulation Training

Attack Simulation Training was implemented to validate the organization's security-awareness capabilities and provide a controlled test of user interaction with a simulated phishing scenario.

The objective was not to create a real malicious campaign, but to evaluate whether the configured Microsoft security environment could support controlled phishing-awareness testing and provide measurable results.

### Phishing Awareness Simulation

A simulation named:

**Phishing Awareness Reporting Test**

was created and completed through Microsoft Defender's Attack Simulation Training capability.

The simulation used the email delivery platform and was configured as a controlled social-engineering awareness exercise.


The completed simulation showed:

| Simulation Attribute | Result |
|---|---|
| Simulation name | Phishing Awareness Reporting Test |
| Type | How-to Guide |
| Category | Social Engineering |
| Delivery platform | Email |
| Status | Completed |

### Simulation Results

The completed simulation provided measurable user-activity results.

The simulation report showed:

- 0% of users compromised
- 0% of users reported the simulation
- 1 of 1 message successfully received
- 0 of 1 messages read
- 0 of 1 messages replied to
- 0 of 1 messages forwarded


The simulation therefore completed successfully from a delivery perspective while producing no reported user interaction with the simulated message.

This result was treated as a security-awareness observation rather than being interpreted as a platform failure.

### Simulation Coverage

The Attack Simulation Training dashboard also provided visibility into simulation coverage.

At the time of validation:

**83% of users had not experienced the simulation.**


This highlighted an important operational consideration: completing a simulation does not necessarily mean that the entire organization has been exposed to the exercise.

Simulation coverage should therefore be monitored separately from simulation completion.

## Security Posture and Secure Score

Microsoft Defender Secure Score was reviewed as part of the final security posture assessment.

The purpose of reviewing Secure Score was to establish a measurable view of the security posture across the available Microsoft security workloads.

The observed overall Secure Score was:

**48.86%**

The workload-level scores were:

| Security Area | Score |
|---|---:|
| Identity | 56.60% |
| Endpoint | 49.15% |
| Applications | 43.51% |
| Overall Secure Score | 48.86% |


The Secure Score was treated as a posture indicator rather than as the sole measure of project completion.

A score below 100% does not mean that the security environment is non-functional. It indicates that additional security improvement actions remain available within the environment.

The score also provided a practical way to identify areas where additional hardening could improve the security posture.

## Security Posture Validation

The final security posture was reviewed across the major Defender security areas.

The validation included:

- Identity security
- Endpoint security
- Email security
- Cloud application security
- Incident status
- Endpoint health
- Exposure level
- Security telemetry
- Automated investigation
- Attack Simulation Training
- Advanced Hunting
- Secure Score

The environment showed:

| Validation Area | Final State |
|---|---|
| Active incidents | 0 |
| Active endpoint alerts | 0 |
| Active endpoint | 1 |
| Endpoint health | Active |
| Endpoint exposure level | 1 |
| Secure Score | 48.86% |
| Identity score | 56.60% |
| Endpoint score | 49.15% |
| Application score | 43.51% |
| Attack simulation | Completed |
| Automated investigation | Completed and resolved |
| PowerShell threat hunt | Completed |
| Advanced Hunting | Completed |


The final state demonstrated that the environment had reached an operational security baseline with no unresolved active incidents at the time of validation.

## Incident Lifecycle Validation

The incident lifecycle was validated from detection through resolution.

The process followed:

    Security Activity
            |
            v
    Detection
            |
            v
    Alert Generation
            |
            v
    Incident Creation
            |
            v
    Analyst Investigation
            |
            +--------------------+
            |                    |
            v                    v
    Device Investigation    Advanced Hunting
            |                    |
            +---------+----------+
                      |
                      v
              Automated Investigation
                      |
                      v
                Risk Assessment
                      |
                      v
                Incident Response
                      |
                      v
                   Resolution
                      |
                      v
                  Validation

This workflow demonstrated the practical use of Microsoft Defender XDR as an operational security platform rather than simply a security dashboard.

## Threat Hunting Validation

The threat-hunting implementation was validated through Advanced Hunting and KQL.

The PowerShell investigation produced two summarized results and identified seven PowerShell executions.

The analysis provided visibility into:

- Device
- User account
- Execution count
- First observed activity
- Last observed activity


The hunting activity demonstrated the ability to move from automated detections into analyst-driven investigation.

This is an important component of a mature security operations workflow because not every security-relevant activity will necessarily generate a high-confidence alert.

## Endpoint Security Validation

The endpoint security layer was validated through the Defender device inventory, device timeline, incidents, Advanced Hunting, and endpoint health state.

The final endpoint remained active and reported telemetry.

The validation confirmed:

- Endpoint onboarding
- Endpoint visibility
- Endpoint telemetry
- Security alert processing
- Device timeline availability
- Automated investigation
- Advanced Hunting
- Incident investigation
- Endpoint health monitoring


The endpoint therefore served as the primary operational security telemetry source throughout the project.

## Identity Security Validation

Identity security was validated through Microsoft Entra ID and the Defender identity security view.

The environment showed:

- Entra ID human identities
- Entra ID non-human identities
- Human identity coverage
- Identity security coverage
- Protected identities
- Identity protection status

The identity security dashboard reported:

**100% Entra ID coverage score**

and:

**1 protected identity, 0 requiring attention, and 0 not protected.**


This provided evidence that the identity layer had been integrated into the broader security posture assessment.

## Cloud Application Security Validation

The Defender for Cloud Apps implementation was reviewed across the available security capabilities.

The following areas were validated:

- Cloud Discovery
- App Governance
- Conditional Access App Control
- Defender for Endpoint integration
- Cloud application security visibility


The environment did not generate significant Cloud Discovery telemetry during the validation period.

This was documented as an environmental limitation rather than being represented as a successful discovery dataset.

## Email Security Validation

The email security implementation was reviewed through the available Microsoft Defender for Office 365 security controls and the completed Attack Simulation Training exercise.

The email security layer provided the foundation for:

- Anti-phishing controls
- Impersonation protection
- Safe Links
- Safe Attachments
- Security-awareness testing
- Email investigation


The successful completion of the phishing-awareness simulation provided additional evidence that the email-security environment could support controlled security-awareness testing.

## Troubleshooting and Engineering Decisions

Several implementation challenges were encountered during the project.

Rather than treating these issues as failures, they were analyzed to determine whether they represented configuration problems, telemetry limitations, licensing limitations, or architectural constraints.

### Limited Security Telemetry

Some Defender views did not initially display the expected data.

For example, certain filters such as Product Name and Threat Type did not provide meaningful results.

The investigation showed that the absence of values was related to the available telemetry rather than necessarily indicating that the security service itself was incorrectly configured.

The solution was to validate the underlying telemetry through Advanced Hunting and other available Defender views.

This reinforced the principle:

**Validate telemetry before assuming that a security control is malfunctioning.**

### Cloud Application Telemetry

Defender for Cloud Apps was configured, but the tenant did not generate meaningful Cloud Discovery application data during the validation period.

Instead of artificially generating cloud application traffic solely to populate the dashboard, the limitation was documented.

This preserved the integrity of the project evidence.

### Defender for Identity Limitation

Traditional Defender for Identity functionality was not implemented because the environment did not contain the required traditional Active Directory infrastructure.

The architecture was therefore maintained as a cloud-native Microsoft Entra ID environment.

This prevented unnecessary infrastructure from being introduced solely to satisfy a theoretical architecture requirement.

### Attack Simulation Coverage

The phishing simulation completed successfully, but the simulation coverage report showed that 83% of users had not experienced the simulation.

This demonstrated that simulation completion and organizational coverage are separate metrics.

The result was documented rather than interpreted as a complete organization-wide awareness assessment.

## Environmental Limitations

The project was implemented within the capabilities and telemetry available in the tenant.

The following limitations were identified:

| Area | Limitation | Engineering Response |
|---|---|---|
| Defender for Identity | No traditional Active Directory environment | Maintained cloud-native Entra ID architecture |
| Cloud Discovery | Limited application telemetry | Documented telemetry limitation |
| Identity hunting | No relevant events in selected query | Validated available identity telemetry separately |
| Cloud Apps hunting | No relevant events in selected query | Validated configuration independently |
| Attack simulation coverage | 83% of users had not experienced simulation | Documented coverage limitation |
| Secure Score | 48.86% | Treated as posture baseline and improvement indicator |
| Endpoint count | One active endpoint | Used available endpoint for investigation and validation |

These limitations were incorporated into the final architecture and documentation rather than being hidden.

## Security Engineering Decisions

Several decisions were made during implementation to ensure that the project remained technically credible.

### Decision 1 — Use the Existing Cloud Identity Architecture

Microsoft Entra ID was retained as the primary identity provider instead of introducing unnecessary on-premises identity infrastructure.

### Decision 2 — Validate Actual Telemetry

Security controls were not considered fully validated simply because their configuration pages showed that they were enabled.

Telemetry, alerts, investigations, and query results were used as evidence.

### Decision 3 — Investigate Real Security Activity

The project used actual endpoint activity and generated security events to demonstrate investigation workflows instead of relying entirely on theoretical scenarios.

### Decision 4 — Use KQL for Proactive Investigation

Advanced Hunting was used to move beyond automated alerts and perform analyst-driven security investigation.

### Decision 5 — Document Limitations

Unavailable infrastructure, insufficient telemetry, and incomplete simulation coverage were documented rather than artificially manipulated.

### Decision 6 — Validate the Final Architecture Against Reality

The final architecture was adjusted to reflect the capabilities that were actually implemented.

This prevents the project from presenting an architecture that exists only on paper.

## Project Outcomes

The project successfully established a cloud-native Microsoft security environment capable of supporting identity security, endpoint protection, email security, cloud application security, centralized investigation, threat hunting, and incident response.

The major outcomes were:

- Microsoft Entra ID established as the cloud identity security foundation.
- Identity security controls implemented and validated.
- Windows endpoint onboarded into Microsoft Defender for Endpoint.
- Endpoint telemetry successfully collected.
- Endpoint execution incident investigated and resolved.
- Device timeline used for investigation.
- Advanced Hunting used for proactive analysis.
- PowerShell threat hunting successfully completed.
- Seven PowerShell executions identified during hunting.
- Two summarized hunting results produced.
- Automated investigation manually initiated and resolved.
- Microsoft Defender for Office 365 security controls configured.
- Phishing-awareness simulation completed.
- Microsoft Defender for Cloud Apps capabilities configured.
- Defender for Endpoint integration with Defender for Cloud Apps configured.
- Microsoft Defender XDR used as the centralized security operations platform.
- Final environment validated with zero active incidents.
- Final endpoint remained active and healthy.
- Secure Score established as a measurable security posture baseline.
- Environmental limitations documented.
- Final architecture aligned with the actual implemented environment.

## Final Security Operations Model

The completed environment demonstrates the following security operations model:

    Microsoft Entra ID
            |
            v
    Identity Security
            |
            v
    Security Workloads
            |
            +------------------+
            |                  |
            v                  v
       Endpoint              Email
       Security             Security
            |                  |
            +--------+---------+
                     |
                     v
            Cloud Application
                Security
                     |
                     v
          Microsoft Defender XDR
                     |
          +----------+----------+
          |          |          |
          v          v          v
       Detection  Hunting  Investigation
          |          |          |
          +----------+----------+
                     |
                     v
              Incident Response
                     |
                     v
                 Resolution
                     |
                     v
                 Validation

This architecture provides a practical foundation for operating a cloud security environment using Microsoft's integrated security ecosystem.

## Skills Demonstrated

This project demonstrates practical experience across multiple areas of cloud security engineering and security operations.

### Cloud Security Engineering

- Cloud-native security architecture
- Microsoft security service integration
- Identity-centric security design
- Defense-in-depth architecture
- Security posture assessment
- Security control validation
- Environmental constraint analysis

### Identity Security

- Microsoft Entra ID
- Multi-Factor Authentication
- Conditional Access
- Privileged Identity Management
- Role-based access control
- Identity security monitoring

### Endpoint Security

- Microsoft Defender for Endpoint
- Endpoint onboarding
- Endpoint telemetry analysis
- Device timeline investigation
- Endpoint incident response
- Automated investigation

### Security Operations

- Microsoft Defender XDR
- Alert triage
- Incident investigation
- Incident management
- Security validation
- Threat hunting

### Threat Detection and Hunting

- Advanced Hunting
- Kusto Query Language
- PowerShell threat hunting
- Security telemetry analysis
- Cross-workload investigation
- Event correlation

### Email and Cloud Application Security

- Microsoft Defender for Office 365
- Anti-phishing protection
- Safe Links
- Safe Attachments
- Impersonation protection
- Microsoft Defender for Cloud Apps
- Cloud Discovery
- App Governance
- Conditional Access App Control

### Security Awareness

- Attack Simulation Training
- Phishing-awareness testing
- Simulation analysis
- User security-awareness validation

## Professional Relevance

This project demonstrates more than the ability to configure individual Microsoft security products.

It demonstrates the ability to approach cloud security as an engineering discipline.

The implementation required understanding how identity, endpoint, email, and cloud application controls interact; how security telemetry is generated and investigated; how detections become incidents; how analysts use KQL to investigate activity; how automated investigations support response; and how security posture can be measured and improved.

The project also demonstrates the ability to work within real-world constraints.

When a capability could not be fully implemented because of infrastructure or telemetry limitations, I evaluated the dependency, identified the architectural impact, documented the limitation, and adapted the design rather than presenting an inaccurate implementation.

This is an important part of practical cloud security engineering because enterprise environments rarely provide every capability in an ideal configuration.

## Project Completion Criteria

The project was considered complete after the following areas had been implemented and validated:

- Identity security foundation established
- Endpoint security implemented
- Email security implemented
- Cloud application security configured
- Microsoft Defender XDR operationalized
- Security telemetry validated
- Advanced Hunting completed
- PowerShell threat hunt completed
- Automated investigation validated
- Security incidents investigated and resolved
- Attack Simulation Training completed
- Endpoint health validated
- Identity security validated
- Secure Score reviewed
- Environmental limitations documented
- Final architecture reviewed
- Security operations workflow validated

The project therefore represents a completed cloud security engineering and security operations implementation based on the capabilities available within the environment.



## Repository Structure

The repository is organized to separate architecture documentation, implementation evidence, security configuration, investigation artifacts, and project documentation.

The structure is designed to make the project easy to review and reproduce while keeping the implementation evidence organized by security domain.

    Microsoft-Defender-XDR-Security-Architecture-for-Enara-Health-Services/
    │
    ├── README.md
    │
    ├── architecture/
    │   ├── defender-xdr-architecture.png
    │   └── cloud-native-identity-architecture.png
    │
    ├── documentation/
    │   ├── Identity-Security.md
    │   ├── Endpoint-Security.md
    │   ├── Email-Security.md
    │   ├── Cloud-Application-Security.md
    │   ├── Threat-Hunting.md
    │   ├── Incident-Response.md
    │   └── Validation-Report.md
    │
    ├── screenshots/
    │   ├── identity/
    │   ├── endpoint/
    │   ├── defender-xdr/
    │   ├── advanced-hunting/
    │   ├── threat-hunting/
    │   ├── office-365/
    │   ├── cloud-apps/
    │   ├── attack-simulation/
    │   └── secure-score/
    │
    └── queries/
        ├── powershell-hunting.kql
        └── advanced-hunting.kql

The repository structure separates implementation evidence from the main project narrative while keeping the security investigation artifacts accessible for technical review.

## Validation Evidence

The implementation was validated using screenshots and observable results captured directly from the Microsoft security environment.

The evidence was organized around the major security capabilities implemented during the project.

### Identity Security Evidence

The identity evidence demonstrates the configuration and validation of the Microsoft Entra ID security layer.

Key evidence includes:

- Microsoft Entra ID users and groups
- Multi-Factor Authentication configuration
- Conditional Access policies
- Privileged Identity Management
- Defender identity security overview
- Identity protection status


### Endpoint Security Evidence

Endpoint evidence demonstrates the onboarding, monitoring, investigation, and validation of the Windows endpoint.

Key evidence includes:

- Defender for Endpoint device inventory
- Endpoint health state
- Exposure level
- Endpoint security alerts
- Device timeline
- Execution incident
- Automated investigation
- Final endpoint validation


### Advanced Hunting Evidence

Advanced Hunting evidence demonstrates the use of Kusto Query Language to investigate security telemetry.

Key evidence includes:

- Cross-workload security telemetry
- PowerShell hunting query
- PowerShell execution results
- Device and account correlation
- First-seen and last-seen activity
- Threat-hunting results


### Incident Investigation Evidence

Incident-response evidence demonstrates the progression from security detection to investigation and resolution.

Key evidence includes:

- Endpoint execution incident
- Incident severity
- Incident status
- Automated investigation
- Resolved incidents
- Final active-incident state


### Email Security Evidence

Email-security evidence demonstrates the configuration of Microsoft Defender for Office 365 and the security-awareness capabilities available within the environment.

Key evidence includes:

- Defender for Office 365 overview
- Email security policies
- Anti-phishing configuration
- Safe Links
- Safe Attachments
- Attack Simulation Training


### Cloud Application Security Evidence

Cloud application security evidence demonstrates the implementation of Microsoft Defender for Cloud Apps.

Key evidence includes:

- Defender for Cloud Apps dashboard
- Defender for Endpoint integration
- App Governance
- Cloud Discovery
- Cloud application security validation


### Attack Simulation Evidence

The Attack Simulation Training evidence demonstrates the controlled phishing-awareness exercise performed during the project.

Key evidence includes:

- Completed simulation
- Simulation configuration
- Delivery status
- User activity
- Simulation impact
- Simulation coverage


### Security Posture Evidence

The final security posture evidence demonstrates the overall state of the implemented environment.

Key evidence includes:

- Microsoft Defender Secure Score
- Identity security score
- Endpoint security score
- Application security score
- Active incidents
- Endpoint health
- Exposure level
- Final security posture


## Evidence-Based Validation Summary

The collected evidence supports the following implementation outcomes:

| Security Area | Validation Evidence | Result |
|---|---|---|
| Identity Security | Entra ID and Defender identity views | Validated |
| MFA | Authentication security configuration | Configured |
| Conditional Access | Conditional Access policies | Configured |
| Privileged Access | PIM configuration | Validated |
| Endpoint Security | Defender for Endpoint | Validated |
| Endpoint Telemetry | Device activity and timeline | Available |
| Endpoint Investigation | Execution incident | Completed |
| Automated Investigation | Defender investigation | Completed |
| Advanced Hunting | KQL queries and results | Completed |
| PowerShell Hunting | Seven executions identified | Completed |
| Email Security | Defender for Office 365 | Configured |
| Cloud Application Security | Defender for Cloud Apps | Configured |
| Attack Simulation | Phishing Awareness Reporting Test | Completed |
| Incident Response | Security incidents | Resolved |
| Final Incident State | Defender XDR | 0 active incidents |
| Endpoint State | Defender for Endpoint | Active |
| Security Posture | Defender Secure Score | 48.86% |

The evidence was used to validate the implementation rather than simply documenting configuration screens.

This distinction is important because a cloud security implementation should demonstrate both configuration and operational evidence.

## Lessons Learned

This project provided practical experience in designing, implementing, investigating, and validating a cloud-native security environment.

### Security Configuration Is Not the Same as Security Validation

One of the most important lessons was that enabling a security feature does not automatically prove that the feature is producing useful security outcomes.

Throughout the project, I validated configurations against actual telemetry, alerts, incidents, investigation results, and security posture information.

This changed the implementation approach from:

**Configure → Assume Working**

to:

**Configure → Generate Telemetry → Investigate → Validate**

### Telemetry Availability Matters

Security platforms depend heavily on the telemetry available to them.

Some workloads may be correctly configured while still producing little or no data because there is insufficient activity, an unavailable data source, or an environmental limitation.

This was observed during the investigation of Cloud Apps and Identity telemetry.

The appropriate engineering response was to investigate the telemetry source rather than immediately treating the absence of results as a configuration failure.

### Cloud Security Requires Architectural Decisions

The project demonstrated that Microsoft security products cannot always be implemented independently of the surrounding architecture.

For example, Defender for Identity has dependencies associated with traditional identity infrastructure.

Because this environment was cloud-native and centered on Microsoft Entra ID, I chose not to introduce unnecessary Active Directory infrastructure simply to represent a capability that was not required by the actual environment.

### Threat Hunting Complements Automated Detection

The endpoint investigation demonstrated the difference between automated detection and analyst-driven threat hunting.

The Defender platform generated security activity that could be investigated through incidents.

Advanced Hunting then provided a way to proactively search telemetry for PowerShell execution patterns.

This demonstrated how threat hunting can complement automated security detection.

### Incident Response Requires Context

An alert by itself does not provide the complete security picture.

The investigation required reviewing:

- The affected endpoint
- Device timeline
- User context
- Related activity
- PowerShell execution
- Automated investigation results
- Incident context

This reinforced the importance of correlating multiple pieces of evidence before reaching an investigation conclusion.

### Security Posture Is Continuous

The Secure Score of 48.86% demonstrated that security posture should be treated as an ongoing improvement process.

A project can have successfully implemented security controls while still having additional security improvement recommendations available.

The objective is therefore not simply to reach a particular score, but to understand the remaining security gaps and prioritize appropriate improvements.

### Documentation Is Part of Security Engineering

The project also demonstrated the importance of documenting implementation decisions and limitations.

Recording why a capability was not implemented is just as important as documenting what was implemented.

This makes the architecture easier to understand, prevents inaccurate claims, and provides a clear basis for future improvements.

## Future Improvements

The current implementation provides a strong cloud-native security foundation, but several improvements could be introduced in a larger production environment.

### Expand Endpoint Coverage

The current environment was validated using one active endpoint.

A production implementation would onboard additional Windows, macOS, Linux, and mobile endpoints where supported.

This would provide broader telemetry and improve endpoint detection coverage.

### Expand Identity Coverage

Additional users, privileged identities, service identities, and workload identities could be incorporated into the identity security model.

The identity environment could also be expanded with more granular Conditional Access policies and stronger privileged-access governance.

### Improve Cloud Application Telemetry

Additional cloud application activity could be introduced to provide more meaningful Cloud Discovery telemetry.

This would allow the organization to identify Shadow IT, evaluate application risk, and establish more detailed cloud application governance policies.

### Expand Attack Simulation Coverage

The phishing-awareness program could be expanded to cover a larger percentage of users and multiple simulation scenarios.

Future simulations could evaluate:

- Credential phishing
- Malicious links
- Attachment-based attacks
- Impersonation
- Social engineering
- Reporting behavior

### Increase Detection Coverage

Additional analytics and detection rules could be implemented to improve coverage across:

- Endpoint threats
- Identity threats
- Email threats
- Cloud application activity
- Suspicious PowerShell
- Credential access
- Persistence
- Lateral movement

### Expand Threat Hunting

The PowerShell hunt could be extended into a broader threat-hunting program covering common adversary behaviors.

Future hunts could investigate:

- Suspicious PowerShell
- Command and scripting interpreter activity
- Credential access
- Persistence mechanisms
- Lateral movement
- Defense evasion
- Suspicious authentication
- Cloud application anomalies

### Improve Automation

Additional automation could be introduced to reduce manual analyst workload.

Potential automation areas include:

- Alert enrichment
- Incident tagging
- User investigation
- Device investigation
- Threat intelligence enrichment
- Automated notification
- Response actions

### Strengthen Security Posture

The Secure Score baseline of 48.86% provides a starting point for continued security improvement.

Future work would prioritize the available recommendations based on:

- Risk reduction
- Business impact
- Implementation complexity
- Identity exposure
- Endpoint exposure
- Application exposure

## Final Project Assessment

The completed implementation demonstrates a practical cloud security engineering workflow using the Microsoft security ecosystem.

The project progressed from identity and workload protection through telemetry collection, detection, investigation, threat hunting, incident response, security awareness testing, and final validation.

The most important outcome was not simply the configuration of Microsoft Defender products.

The project demonstrated the ability to:

- Design a cloud-native security architecture
- Implement Microsoft security controls
- Integrate security workloads
- Validate security telemetry
- Investigate endpoint activity
- Use KQL for threat hunting
- Analyze PowerShell activity
- Perform automated investigation
- Manage security incidents
- Validate endpoint security
- Test security awareness
- Assess security posture
- Identify environmental limitations
- Make architecture decisions based on available infrastructure
- Document security engineering decisions

The final environment provides a practical foundation for cloud security operations and demonstrates how Microsoft security services can be combined to create a layered security architecture.

## Conclusion

The Microsoft Defender XDR Security Architecture for Enara Health Services project demonstrates an end-to-end approach to cloud security engineering and security operations.

The implementation established Microsoft Entra ID as the identity security foundation, deployed endpoint protection through Microsoft Defender for Endpoint, configured email security through Microsoft Defender for Office 365, implemented cloud application security through Microsoft Defender for Cloud Apps, and used Microsoft Defender XDR as the centralized security operations platform.

Beyond configuration, the environment was actively used for security investigation.

I investigated endpoint execution activity, analyzed device timelines, used Advanced Hunting and KQL to investigate PowerShell activity, performed a dedicated threat hunt, reviewed automated investigation results, investigated and resolved security incidents, and validated the final endpoint state.

The project also included a completed phishing-awareness simulation and a review of the overall Microsoft Defender security posture.

The final environment reached a state with:

- 0 active incidents
- 0 active endpoint alerts
- 1 active endpoint
- Active endpoint health
- Exposure level of 1
- 35 events identified during cross-workload hunting
- 7 PowerShell executions identified
- 2 security incidents investigated and resolved
- Completed Attack Simulation Training
- 48.86% overall Secure Score
- 56.60% Identity score
- 49.15% Endpoint score
- 43.51% Application score

The project also reinforced an important principle of cloud security engineering: security architecture must reflect the environment that actually exists.

Where infrastructure or telemetry was unavailable, I documented the limitation, evaluated its architectural impact, and avoided introducing unnecessary components or generating artificial evidence simply to make the environment appear more complete.

The result is a cloud-native Microsoft security environment that demonstrates practical experience across identity security, endpoint detection and response, email security, cloud application security, security operations, threat hunting, incident response, and security posture management.

This project represents my practical application of cloud security engineering principles to a realistic healthcare security environment and provides a foundation for further development toward a production-grade Microsoft security architecture.


## Author

**Sampson Manyo**

Cloud Security | Security Operations | Microsoft Security | Threat Detection & Response

This project represents hands-on implementation and validation of Microsoft cloud security technologies, with emphasis on cloud security architecture, identity security, endpoint detection and response, security operations, threat hunting, incident investigation, and security posture management.

## Project Documentation

This README documents the architecture, implementation approach, security controls, investigation activities, validation results, engineering decisions, and limitations encountered during the project.

All screenshots and supporting documentation included in this repository are based on the actual implementation and validation activities performed within the project environment.

## Disclaimer

This project was developed as a controlled security engineering and learning environment.

The healthcare organization name **Enara Health Services** is used as a project scenario and does not represent an actual production healthcare organization.

No real patient information, production credentials, sensitive organizational data, or unauthorized systems were used as part of this implementation.

All security testing and simulation activities were performed within the controlled project environment.

## Project Status

**Status: Completed**

The Microsoft Defender XDR Security Architecture for Enara Health Services project has been implemented, investigated, validated, documented, and reviewed against the capabilities available within the project environment.

The final architecture reflects the actual implemented security controls, available telemetry, investigation results, and documented environmental limitations.
