# Features and tools in Azure for governance and compliance

---

## Table of Contents
1. [Microsoft Purview](#microsoft-purview)  
2. [Azure Policy](#azure-policy)  
3. [Resource Locks](#resource-locks)  
4. [Service Trust Portal](#service-trust-portal)  

---

## Microsoft Purview

Microsoft Purview provides a **unified view of your data** 
across on-premises, multicloud, and SaaS environments for **data governance, risk, and compliance**.

### Key Features
- **Automated Data Discovery** – Automatically scan and catalog your data.  
- **Sensitive Data Classification** – Identify and classify sensitive information.  
- **End-to-End Data Lineage** – Track how data flows through your systems.

### Solution Areas
1. **Risk and Compliance**
   - Monitors Microsoft 365 services (Teams, OneDrive, Exchange).  
   - Helps:
     - Protect sensitive data across clouds, apps, and devices.  
     - Identify risks and meet regulatory requirements.  

2. **Unified Data Governance**
   - Manage data across **Azure, SQL, Hive, on-premises, and other clouds (e.g., Amazon S3)**.  
   - Benefits:
     - Map your entire data estate with classification and lineage.  
     - Identify sensitive data locations.  
     - Provide secure access for data consumers.  
     - Generate insights on data usage and storage.  
     - Manage access securely at scale.

---

## Azure Policy

Azure Policy ensures **resources remain compliant** with corporate standards 
by enforcing rules on configurations.

### Key Concepts
- **Policies:** Rules applied to resources to enforce compliance.  
- **Initiatives:** Groups of related policies for broader compliance goals.  
- **Scope:** Can be applied to resources, resource groups, subscriptions, etc. Policies **inherit** from higher levels.  
- **Built-in Definitions:** Available for Storage, Networking, Compute, Security Center, Monitoring.

### Features
- Prevents creation of noncompliant resources.  
- Evaluates existing resources for compliance.  
- Can **automatically remediate** noncompliant resources.  
- Integrates with **Azure DevOps** for CI/CD compliance.

### Example Initiative
- **Enable Monitoring in Azure Security Center**
  - Monitors unencrypted SQL Databases.  
  - Checks OS vulnerabilities.  
  - Ensures endpoint protection is installed.  
  - Contains over 100 policies under one initiative.

---

## Resource Locks

Prevent accidental deletion or modification of critical resources.

### Types of Locks
1. **Delete** – Users can read/modify, but cannot delete the resource.  
2. **ReadOnly** – Users can only read; cannot delete or modify.

### Key Points
- Can be applied at **resource, resource group, or subscription** level.  
- Locks are **inherited** by all child resources.  
- Managed via **Azure Portal, PowerShell, CLI, or ARM templates**.  
- To modify a locked resource:
  1. Remove the lock.  
  2. Make changes.  
  3. Reapply the lock if needed.

---

## Service Trust Portal

Provides access to Microsoft’s **security, privacy, and compliance documentation and tools**.

### Key Features
- **Implementation Details:** Shows Microsoft controls and processes for cloud services.  
- **Authentication:** Sign in with Microsoft cloud services account (Entra org account).  
- **NDA:** Accept Microsoft NDA for access to some compliance materials.

### Main Menu Categories
1. **Service Trust Portal** – Home page link.  
2. **My Library** – Save/pin documents; receive updates.  
3. **All Documents** – Single landing page for all documents; pin to My Library.
