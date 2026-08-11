# Identity Security Implementation

## Overview

Microsoft Entra ID was implemented as the identity and access security foundation of the Enara Health Services cloud environment.

The identity security implementation focused on establishing stronger authentication, controlling access to cloud resources, managing privileged identities, and providing visibility into the identity security posture.

The implementation was designed around the principle of least privilege and layered identity protection.

The resulting identity security model is:

    User / Administrator
            |
            v
    Microsoft Entra ID
            |
            +---- Multi-Factor Authentication
            |
            +---- Conditional Access
            |
            +---- Role-Based Access Control
            |
            +---- Privileged Identity Management
            |
            v
    Identity Security Monitoring
            |
            v
    Microsoft Defender XDR


## Objectives

The identity security implementation was designed to achieve the following objectives:

- Establish Microsoft Entra ID as the primary cloud identity provider.
- Strengthen authentication using Multi-Factor Authentication.
- Apply identity-based access controls using Conditional Access.
- Reduce unnecessary privileged access through Privileged Identity Management.
- Apply role-based access control.
- Review identity security posture through Microsoft Defender.
- Validate identity protection coverage.
- Establish identity as a foundational security boundary within the cloud architecture.


## Microsoft Entra ID Environment

The project environment used Microsoft Entra ID as the central identity service.

The tenant provided the identity layer used by the Microsoft security ecosystem and served as the foundation for authentication and authorization.

The identity environment included both human and non-human identities.

The final identity inventory observed during validation included:

| Identity Category | Count |
|---|---:|
| Entra ID human identities | 7 |
| Entra ID non-human identities | 8 |
| Human identities | 14 |
| Non-human identities | 8 |

The identity counts were reviewed as part of the broader Microsoft Defender identity security assessment.


## Identity Security Architecture

Identity security was positioned at the beginning of the overall security architecture.

    User
      |
      v
    Authentication
      |
      v
    Microsoft Entra ID
      |
      +-------------------------+
      |                         |
      v                         v
    MFA                  Conditional Access
      |                         |
      +------------+------------+
                   |
                   v
          Authorization
                   |
                   v
          Privileged Access
                   |
                   v
                  PIM
                   |
                   v
          Security Monitoring


This architecture ensures that identity controls are applied before users and administrators gain access to protected cloud resources.


## Multi-Factor Authentication

Multi-Factor Authentication was incorporated into the identity security model to provide an additional authentication layer beyond the user's primary credentials.

The purpose of MFA was to reduce the security impact of compromised passwords by requiring an additional verification mechanism during authentication.

The MFA configuration was reviewed as part of the identity security implementation.

The security objective was:

    Primary Credentials
            |
            v
    Additional Verification
            |
            v
       Authentication
            |
            v
       Resource Access


### Security Benefit

MFA provides protection against several credential-based attack scenarios, particularly situations where an attacker obtains a user's password but does not possess the additional authentication factor.

The implementation therefore established MFA as an important control within the identity security layer.



## Conditional Access

Conditional Access was implemented as an identity-based access control mechanism.

Rather than treating successful password authentication as sufficient authorization, Conditional Access provides a framework for evaluating access requests against defined conditions and security requirements.

The implementation was reviewed around the following security concepts:

- User identity
- Application being accessed
- Authentication context
- Access requirements
- Security controls
- Policy enforcement

The conceptual access workflow is:

    Access Request
          |
          v
    Microsoft Entra ID
          |
          v
    Conditional Access
          |
          +---- Evaluate Identity
          |
          +---- Evaluate Application
          |
          +---- Evaluate Conditions
          |
          +---- Apply Access Control
          |
          v
    Allow / Require Additional Control / Block


### Security Benefit

Conditional Access provides an additional security boundary around cloud access.

It allows access decisions to be based on security context rather than relying exclusively on credentials.


## Privileged Identity Management

Privileged Identity Management was incorporated into the identity security architecture to strengthen the management of privileged roles.

Privileged identities represent a higher-risk area because compromise of an administrative account can provide an attacker with significantly greater access to cloud resources.

The PIM implementation therefore focused on visibility and control over privileged role assignments.

The operational model is:

    Privileged Role
          |
          v
    PIM Management
          |
          +---- Role Assignment
          |
          +---- Activation
          |
          +---- Access Control
          |
          v
    Administrative Activity


### Security Objective

The objective of PIM is to reduce unnecessary standing privileged access and provide greater control and visibility over administrative permissions.

The privileged-access configuration was reviewed during the identity security implementation.

<img width="946" height="859" alt="xdr-admin-role" src="https://github.com/user-attachments/assets/172e545d-0ceb-4e81-a78a-6335eb8a93ea" />



## Role-Based Access Control

Role-Based Access Control was used as part of the identity security model.

RBAC provides a structured method for assigning permissions according to defined administrative responsibilities rather than granting users broad access by default.

The implementation considered the principle of least privilege when reviewing role assignments.

The security model is:

    Identity
       |
       v
    Assigned Role
       |
       v
    Defined Permissions
       |
       v
    Required Resource Access


This approach reduces unnecessary permissions and helps establish clearer administrative boundaries within the cloud environment.


## Identity Security Monitoring

Identity security was also evaluated through Microsoft Defender's identity security capabilities.

The purpose of the monitoring layer was to provide visibility into the identity environment and identify identities that may require additional security attention.

The final identity security assessment showed:

| Identity Security Metric | Result |
|---|---:|
| Entra ID coverage score | 100% |
| Protected identities | 1 |
| Identities requiring attention | 0 |
| Unprotected identities | 0 |

<img width="1600" height="795" alt="defender-xdr-identity-security-overview" src="https://github.com/user-attachments/assets/69375bf0-6f6a-4ad6-accd-3c9819813f85" />



## Identity Security Validation

The identity implementation was validated using the available Microsoft Entra ID and Microsoft Defender security views.

The validation process included:

1. Reviewing the tenant identity environment.
2. Reviewing available user and group information.
3. Reviewing authentication security controls.
4. Reviewing Multi-Factor Authentication.
5. Reviewing Conditional Access.
6. Reviewing privileged access controls.
7. Reviewing identity security coverage.
8. Reviewing protected and unprotected identities.
9. Confirming the final identity security state.

The final validation produced:

**100% Entra ID coverage**

with:

- 1 protected identity
- 0 identities requiring attention
- 0 identities classified as not protected

This provided measurable evidence that the identity layer was being represented within the Defender security posture.



## Identity Security and Microsoft Defender XDR

Identity security was not treated as an isolated Microsoft Entra ID configuration.

The identity layer formed part of the broader Microsoft Defender XDR architecture.

The relationship can be represented as:

    Microsoft Entra ID
            |
            v
    Identity Security
            |
            v
    Authentication Context
            |
            v
    Microsoft Defender XDR
            |
            +---- Detection
            |
            +---- Investigation
            |
            +---- Threat Hunting
            |
            +---- Incident Response


This approach allows identity information to contribute to broader security investigations where relevant telemetry is available.


## Cloud-Native Identity Architecture

The identity architecture was deliberately maintained as cloud-native.

The environment did not contain a traditional on-premises Active Directory infrastructure.

Rather than introducing a Windows Server domain controller solely to support an additional security capability, Microsoft Entra ID was retained as the primary identity platform.

The final identity architecture was therefore:

    Cloud Environment
          |
          v
    Microsoft Entra ID
          |
          +---- Authentication
          |
          +---- MFA
          |
          +---- Conditional Access
          |
          +---- PIM
          |
          +---- RBAC
          |
          v
    Microsoft Defender XDR


This architectural decision ensured that the project remained aligned with the infrastructure that was actually available.


## Defender for Identity Consideration

Traditional Microsoft Defender for Identity sensor deployment was not performed.

The reason was architectural rather than a configuration failure.

Defender for Identity is designed around identity signals associated with traditional Active Directory environments, while this project was implemented as a cloud-native Microsoft Entra ID environment.

Introducing traditional Active Directory infrastructure solely to demonstrate Defender for Identity would have changed the architecture and introduced infrastructure that was not required for the project's actual security objectives.

The limitation was therefore documented as part of the final architecture.



## Identity Security Controls Summary

| Control | Purpose | Implementation State |
|---|---|---|
| Microsoft Entra ID | Cloud identity foundation | Implemented |
| Multi-Factor Authentication | Strong authentication | Implemented |
| Conditional Access | Identity-based access control | Implemented |
| Privileged Identity Management | Privileged access management | Implemented |
| RBAC | Least-privilege access control | Implemented |
| Identity Security Monitoring | Identity posture visibility | Validated |
| Defender for Identity | Traditional AD identity monitoring | Not implemented due to architecture |

## Identity Security Validation Evidence

The following evidence was collected during the implementation:

| Evidence | Purpose |
|---|---|
| Entra ID users and groups | Identity inventory |
| MFA configuration | Authentication security |
| Conditional Access policies | Access control |
| PIM configuration | Privileged access management |
| Defender identity overview | Identity security posture |
| Final identity validation | Security coverage verification |



## Security Engineering Assessment

The identity implementation established Microsoft Entra ID as the first security boundary within the Enara Health Services cloud environment.

The combination of MFA, Conditional Access, RBAC, and PIM provided multiple layers of identity protection.

The implementation also demonstrated an important cloud security engineering principle: security architecture should be designed around the infrastructure that actually exists.

By retaining Microsoft Entra ID as the primary identity platform and documenting the absence of traditional Active Directory infrastructure, the final architecture remained accurate and cloud-native.

The identity layer therefore provides the foundation for the broader security architecture documented throughout this project.
