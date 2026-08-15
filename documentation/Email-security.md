# Microsoft Defender for Office 365 Implementation

## Overview

Microsoft Defender for Office 365 was included in the Enara Health Services security environment as the email and collaboration security layer.

The implementation focused on the Microsoft Defender for Office 365 capabilities that were available in the tenant and were actually configured and validated during the project.

The email security layer also provided the foundation for the Attack Simulation Training exercise that was completed during the implementation.

## Email Security Objectives

The email security work focused on:

- Reviewing the available Microsoft Defender for Office 365 security capabilities.
- Configuring the available email protection controls.
- Reviewing the available security policies.
- Validating the Defender for Office 365 environment.
- Using Attack Simulation Training to perform a controlled phishing-awareness exercise.
- Reviewing the results of the completed simulation.

## Microsoft Defender for Office 365

Microsoft Defender for Office 365 was used as part of the broader Microsoft Defender security architecture.

The email security layer was positioned alongside the endpoint and cloud application security workloads.

    Email and Collaboration
            |
            v
    Microsoft Defender for Office 365
            |
            v
    Email Security
            |
            v
    Microsoft Defender XDR
            |
            +---- Investigation
            |
            +---- Incidents
            |
            +---- Security Operations

<img width="940" height="941" alt="e5-license-inventory" src="https://github.com/user-attachments/assets/fa0aad9a-9703-4a09-812e-ffe3afa265b9" />


## Email Security Configuration

The available Microsoft Defender for Office 365 security configuration was reviewed as part of the project.

The implementation focused on the available email security protections within the tenant.

The configured and reviewed security areas included the Microsoft Defender for Office 365 protection capabilities that were available within the environment.

<img width="939" height="936" alt="m365-e5-trial-active" src="https://github.com/user-attachments/assets/a2651cf6-da70-447f-81f2-6afaa835b727" />


## Email Security and Security Operations

The email security layer was considered as part of the broader Microsoft Defender XDR environment rather than as an isolated service.

The overall security model was:

    Email Activity
          |
          v
    Defender for Office 365
          |
          v
    Security Telemetry
          |
          v
    Microsoft Defender XDR
          |
          +---- Detection
          |
          +---- Investigation
          |
          +---- Incident Management

The available email telemetry was also visible during Advanced Hunting.

During the cross-workload investigation performed in the project, the query returned:

**2 email events**

These events formed part of the total 35 events returned by the investigation.

| Security Workload | Events |
|---|---:|
| Endpoint | 33 |
| Email | 2 |
| Cloud Apps | 0 |
| Identity | 0 |
| Total | 35 |

<img width="1600" height="788" alt="cross-workload-advanced-hunting-results" src="https://github.com/user-attachments/assets/53ce4b2e-eb03-415f-9c7b-f498bba0219a" />


This provided evidence that email-related telemetry was available within the Microsoft Defender investigation environment.

## Attack Simulation Training

Attack Simulation Training was used to perform a controlled phishing-awareness exercise.

The simulation was designed to evaluate the security-awareness capabilities available within the Microsoft Defender environment.

The completed simulation was named:

**Phishing Awareness Reporting Test**

The simulation status was:

**Completed**

<img width="946" height="946" alt="attack-simulation-scheduled" src="https://github.com/user-attachments/assets/d0ad36e2-fe18-456e-a378-7cf202222277" />



## Phishing Awareness Simulation Results

The completed simulation produced the following observed results:

| Simulation Result | Observed Result |
|---|---:|
| Simulation status | Completed |
| Messages successfully received | 1 of 1 |
| Messages read | 0 of 1 |
| Messages replied to | 0 of 1 |
| Messages forwarded | 0 of 1 |
| Users compromised | 0% |
| Users reported the simulation | 0% |

<img width="945" height="942" alt="attack-simulation-final-results" src="https://github.com/user-attachments/assets/d8b9825f-9fa6-408b-ad85-a9dff5e862b0" />


The simulation completed successfully, while the available results showed no reported user interaction with the simulated message.

The result was documented as part of the security-awareness validation rather than being interpreted beyond what the simulation data demonstrated.

## Attack Simulation Coverage

The simulation coverage information was also reviewed.

The observed result showed that:

**83% of users had not experienced the simulation.**

<img width="945" height="942" alt="attack-simulation-final-results" src="https://github.com/user-attachments/assets/0dc88fbe-14b8-4ec3-a2bd-040a40ae16ce" />


This result demonstrated that simulation completion and user coverage are separate measurements.

The simulation itself was completed, but the coverage information indicated that the exercise had not reached the entire available user population.

## Email Security Validation

The email security implementation was validated using the available Microsoft Defender for Office 365 views and the completed Attack Simulation Training exercise.

The validation demonstrated:

- Microsoft Defender for Office 365 was available within the security environment.
- Email-related security telemetry was available during Advanced Hunting.
- The phishing-awareness simulation was successfully completed.
- The simulation generated measurable delivery and interaction results.
- Simulation coverage was visible within the Defender environment.

## Observed Results

The email security work produced the following measurable results during the project:

| Metric | Result |
|---|---:|
| Email events identified during Advanced Hunting | 2 |
| Attack Simulation status | Completed |
| Messages successfully received | 1 / 1 |
| Messages read | 0 / 1 |
| Messages replied to | 0 / 1 |
| Messages forwarded | 0 / 1 |
| Users compromised | 0% |
| Users reporting simulation | 0% |
| Users who had not experienced simulation | 83% |

## Email Security Limitations

The documentation of this project is intentionally limited to the capabilities and results that were actually observed within the tenant.

The Attack Simulation results showed that the simulation was completed, but 83% of users had not experienced the simulation.

Therefore, the simulation should not be interpreted as an organization-wide phishing-awareness assessment.

Similarly, the Advanced Hunting query returned only two email events within the selected investigation results.

These observations represent the telemetry and coverage available within the project environment at the time of validation.

## Security Engineering Assessment

The Microsoft Defender for Office 365 implementation contributed the email security layer to the broader Enara Health Services security architecture.

The implementation also demonstrated how email security can be connected to security operations through Microsoft Defender XDR and investigated alongside other available security telemetry.

The completed Attack Simulation Training exercise provided an additional validation point for the security-awareness component of the environment.

The results were documented based on the actual simulation output and available telemetry rather than assuming complete organizational coverage.

## Final Email Security State

The email security implementation was considered validated based on the capabilities and evidence available within the project environment.

The final observed state included:

- Microsoft Defender for Office 365 available within the environment.
- Email security configuration reviewed.
- Email telemetry identified through Advanced Hunting.
- Two email events returned during the cross-workload investigation.
- Attack Simulation Training completed.
- One of one simulated messages successfully received.
- Zero users compromised.
- Zero users reported the simulation.
- Eighty-three percent of users had not experienced the simulation.

The email security layer therefore formed a validated component of the broader Microsoft Defender XDR security architecture implemented for Enara Health Services.
