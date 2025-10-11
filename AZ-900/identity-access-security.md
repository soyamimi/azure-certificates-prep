# Azure Identity Access, and Security

## 1. Azure Directory Services
- **Microsoft Entra ID**
  - Cloud-based identity and access management service
  - Manages user identities, authentication, single sign-on (SSO), application management, device management
  - Integrates with on-premises Active Directory using **Microsoft Entra Connect**
- **Microsoft Entra Domain Services**
  - Managed domain services: domain join, group policy, LDAP, Kerberos/NTLM authentication
  - Supports lift-and-shift of legacy applications to Azure
  - One-way synchronization from Entra ID to Domain Services

## 2. Azure Authentication Methods
- **Authentication Overview**
  - Establishes identity of a person, service, or device
  - Types: Passwords, SSO, Multifactor Authentication (MFA), Passwordless
- **Single Sign-On (SSO)**
  - One identity, multiple applications
  - Simplifies user management and access revocation
- **Multifactor Authentication (MFA)**
  - Extra factor: something you know, have, or are
  - Microsoft Entra MFA options: Phone call, App notification
- **Passwordless Authentication**
  - Windows Hello for Business (PC-based biometrics/PIN)
  - Microsoft Authenticator App (phone-based)
  - FIDO2 Security Keys (hardware-based)

## 3. Azure External Identities
- **Concept:** Access by users, devices, services outside the organization
- **Capabilities**
  - B2B Collaboration: Invite guest users, enforce access controls
  - B2B Direct Connect: Two-way trust with other tenants (e.g., Teams shared channels)
  - Azure AD B2C: Customer-facing app identity and access management
- External users “bring their own identity” and IT manages access via Entra ID

## 4. Azure Conditional Access
- Uses **signals** to determine access:
  - User identity, location, device, application
- Decision outcomes:
  - Allow, Block, Require MFA
- Scenarios:
  - Require MFA for admins or high-risk locations
  - Limit access to approved apps or managed devices

## 5. Azure Role-Based Access Control (RBAC)
- **Principle of Least Privilege**
- **Roles and Scopes**
  - Built-in and custom roles
  - Scopes: Management group → Subscription → Resource Group → Resource
- **Hierarchical Inheritance**
  - Parent scope assignments propagate to child resources
- **Enforcement**
  - Through Azure Resource Manager (portal, CLI, PowerShell)
  - Allow model: permissions granted by role assignments

## 6. Zero Trust Model
- **Principles**
  - Verify explicitly: Authenticate and authorize based on all available data
  - Least privilege access: Just-in-Time (JIT) and Just-Enough-Access (JEA)
  - Assume breach: Minimize blast radius, segment access, end-to-end encryption
- **Key Concept:** Access decisions are based on identity and context, not network location

## 7. Defense-in-Depth
- **Layered security approach** protecting data at the center
- **Layers**
  1. Physical security
  2. Identity and access
  3. Perimeter (DDoS, firewalls)
  4. Network (segmentation, restricted connectivity)
  5. Compute (VM access, endpoint protection)
  6. Application (secure coding, secret storage)
  7. Data (confidentiality, integrity, availability)

## 8. Microsoft Defender for Cloud
- **Purpose:** Cloud security posture management and threat protection
- **Coverage:** Azure-native, hybrid, multicloud (AWS, GCP)
- **Core Functions**
  1. **Assess** – Security posture, vulnerability scans, secure score
  2. **Secure** – Harden resources with Azure Security Benchmark
  3. **Defend** – Threat detection, security alerts, advanced protection
- **Advanced Features**
  - Adaptive application controls, Just-in-Time VM access
  - Integration with Microsoft Defender for Endpoint
