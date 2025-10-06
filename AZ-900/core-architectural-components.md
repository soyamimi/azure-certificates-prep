# Core architectural components of Azure

## Table of Contents
1. [Azure Physical Infrastructure](#azure-physical-infrastructure)
   - [Regions](#regions)
   - [Availability Zones](#availability-zones)
   - [Region Pairs](#region-pairs)
   - [Sovereign Regions](#sovereign-regions)
2. [Azure Management Infrastructure](#azure-management-infrastructure)
   - [Resources and Resource Groups](#resources-and-resource-groups)
   - [Azure Subscriptions](#azure-subscriptions)
   - [Azure Management Groups](#azure-management-groups)

---
## Azure Physical Infrastructure

Azure’s physical infrastructure is made up of **datacenters** distributed globally. 
These datacenters are grouped into **Regions** and **Availability Zones** to provide high availability, scalability, and fault tolerance.

Azure’s global network connects these datacenters using **low-latency, high-speed fiber-optic connections** to ensure performance and reliability.

---

## Regions
- **Region** : A geographical area containing one or more datacenters.
- Resources deployed in Azure are usually tied to a specific region.
- Regions are designed to:
  - Enable **data residency** and **compliance**.
  - Provide **redundancy** and **failover** options.
- Some services are **region-specific**, while others are **global services** (e.g., Microsoft Entra ID, Azure DNS, Azure Traffic Manager).

**Examples of Regions:**
- East US
- West Europe
- Southeast Asia

---

## Availability Zones
- Availability Zones are **physically separate datacenters** within a region.
- Each zone has **independent power, cooling, and networking**.
- Zones are connected with **private high-speed fiber networks**.
- Purpose: Increase availability and resilience for mission-critical workloads.

**Categories of Azure Services:**
1. **Zonal Services:** You pin the resource to a specific zone (e.g., Virtual Machines, Managed Disks).
2. **Zone-Redundant Services:** Azure replicates data automatically across zones (e.g., Zone-Redundant Storage, SQL Database).
3. **Non-Regional Services:** Always available globally and resilient to regional outages (e.g., Azure DNS).

**Usage Example:**
Deploying VMs in multiple zones within the same region ensures high availability if one zone fails.

**Note:** There may be **extra cost** for data transfer between zones.

---

### Region Pairs
- Each Azure region is paired with another region **at least 300 miles away** within the same geography.
- Purpose: Disaster recovery and fault tolerance across large-scale outages.
- Data replication between paired regions increases availability and durability.

**Examples:**
- West US ↔ East US
- Southeast Asia ↔ East Asia

**Advantages of Region Pairs:**
- During widespread outages, one region in each pair is prioritized for recovery.
- Planned updates are rolled out to one region at a time.
- Data remains within the same geography (except for Brazil South).

**Important:** Not all services automatically replicate data between region pairs — you must configure this for some workloads.

---

### Sovereign Regions
- Special Azure regions isolated from the global Azure network for **compliance and regulatory** purposes.

**Types of Sovereign Regions:**
1. **US Government Regions:** (e.g., US Gov Virginia, US DoD Central)
   - Operated by screened US personnel
   - For government agencies and partners
   - Includes additional compliance certifications
2. **China Regions:** (e.g., China East, China North)
   - Operated by 21Vianet
   - Physically and logically separate from global Azure

---

## Azure Management Infrastructure

The management infrastructure organizes how Azure resources are deployed, grouped, and governed.
It consists of:
- **Resources**
- **Resource Groups**
- **Subscriptions**
- **Management Groups**

---

### Resources and Resource Groups

**Resources**
- Basic building blocks of Azure (e.g., VM, Storage Account, Database).
- Anything you create or deploy in Azure.

**Resource Groups**
- Logical containers that hold related resources.
- Every resource must belong to a single resource group.
- Resource groups **cannot be nested**.
- Actions at the resource group level apply to all contained resources.
  - Example: Deleting a resource group deletes all its resources.

**Best Practices:**
- Group related resources by lifecycle, environment, or access control.
- Example: Create a single resource group for a temporary development environment to delete it easily later.

---

### Azure Subscriptions

**Definition:**
- A subscription is a **logical unit of management, billing, and access control** in Azure.
- Provides authenticated access to Azure products and services.

**Key Points:**
- An **Azure account** (identity in Microsoft Entra ID) can have one or more subscriptions.
- Subscriptions group resource groups for:
  - Billing management
  - Policy enforcement
  - Access control

**Subscription Boundaries:**
1. **Billing Boundary:**
   - Defines how billing is organized.
   - Separate invoices for each subscription.
   - Useful for managing departmental or project-level budgets.
2. **Access Control Boundary:**
   - Defines access management policies.
   - RBAC (Role-Based Access Control) applied at subscription level.

**Reasons to Create Additional Subscriptions:**
- Separate environments (production, development, testing)
- Reflect organizational structure (departments or teams)
- Manage billing and cost allocation

**Example:**
Create one subscription for production workloads and another for development/testing to separate cost tracking.

---

### Azure Management Groups

**Definition:**
- Provide a **hierarchical structure** above subscriptions for unified policy, compliance, and access control.
- Used in large-scale or enterprise environments with multiple subscriptions.

**Purpose:**
- Apply governance policies and RBAC access at scale.
- All subscriptions under a management group inherit those policies.

**Key Facts:**
- Up to **10,000 management groups** per directory.
- A management group hierarchy can be **six levels deep** (excluding root/subscription).
- Each subscription or management group can have **only one parent**.

**Use Cases:**
1. **Centralized Policy Enforcement:**
   - Apply a region restriction (e.g., allow only US West) at the management group level.
   - Automatically inherited by all descendant subscriptions.
2. **Unified Access Control:**
   - Assign RBAC roles at management group level for all child subscriptions and resources.