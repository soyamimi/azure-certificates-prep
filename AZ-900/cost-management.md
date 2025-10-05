# Cost management in Azure

---

## Table of Contents
1. [Azure Cost Concepts](#azure-cost-concepts)  
2. [Cost Influencing Factors](#cost-influencing-factors)  
3. [Azure Cost Management](#azure-cost-management)  
4. [Cost Alerts](#cost-alerts)  
5. [Budgets](#budgets)  
6. [Azure Resource Tags](#azure-resource-tags)

---

## Azure Cost Concepts

- Azure shifts costs from **CapEx** (building/maintaining infrastructure) to **OpEx** (pay-as-you-go).  
- Pay for what you **use**, when you **use it**.  
- Cost depends on multiple factors: **resource type, consumption, maintenance, geography, subscription type, and Azure Marketplace usage**.

---

## Cost Influencing Factors

### 1. Resource Type
- Pricing depends on **type, settings, and region**.  
- Example: Storage accounts vary by:
  - Type (Blob, File, etc.)  
  - Performance tier  
  - Access tier  
  - Redundancy settings  
  - Region  

### 2. Consumption
- **Pay-as-you-go:** Pay for resources used during the billing cycle.  
- **Reserved Capacity:** Commit to resources (1–3 years) → save up to **72%**.  
- Surges beyond reserved capacity are billed normally.

### 3. Maintenance
- Monitor resources to avoid paying for unused VMs, storage, or networking.  
- Organize resources in **resource groups**.

### 4. Geography
- Pricing varies by region due to **power, labor, taxes**.  
- Network traffic costs differ by **data transfer zones**.

### 5. Subscription Type
- Subscription types affect cost via allowances.  
- Example: Azure Free Trial offers free services for 12 months + 30-day credit.

### 6. Azure Marketplace
- Third-party solutions may add extra costs beyond Azure services.  
- All Marketplace products are **certified and compliant**.

---

## Azure Cost Management

- Monitors and controls Azure spending.  
- Key features:
  - **Cost Analysis:** Visualize costs by billing cycle, resource, or region.  
  - **Budgets & Alerts:** Track spending and get notified when thresholds are exceeded.  
  - **Automation:** Trigger actions when budget thresholds are hit.

---

## Cost Alerts

<details>
<summary>Types of Alerts</summary>

1. **Budget Alerts**
   - Triggered when spending/usage reaches a predefined limit.  
   - Can notify via portal and email.  

2. **Credit Alerts**
   - Notifies when Azure credits (EA) reach 90% or 100%.  

3. **Department Spending Quota Alerts**
   - Triggered when departmental spending hits fixed thresholds (e.g., 50%, 75%).

</details>

---

## Budgets

- Set limits based on **subscription, resource group, or service type**.  
- **Budget alerts** notify when thresholds are reached.  
- Advanced budgets can **automate resource suspension or modification** when exceeded.

---

## Azure Resource Tags

<details>
<summary>What Are Tags?</summary>

- **Name-value pairs** that add metadata to resources.  
- Help with **organization, cost management, operations, security, governance, and automation**.  
- Tags are **not inherited** from subscriptions or resource groups.

</details>

### Key Benefits
- **Resource Management:** Locate resources by workload, environment, owner, or department.  
- **Cost Management:** Group resources for budgeting, chargebacks, and reporting.  
- **Operations:** Identify critical resources to support SLAs.  
- **Security:** Classify resources (public, confidential).  
- **Governance:** Ensure regulatory compliance (e.g., ISO 27001).  
- **Automation:** Enable automated tasks for tagged resources.

### Managing Tags
- Use **Azure Portal, PowerShell, CLI, ARM templates, or REST API**.  
- **Azure Policy** can enforce tags or reapply missing tags.  

### Example Tag Structure

| Name        | Value Example                                |
|------------|---------------------------------------------|
| AppName     | Name of the application                      |
| CostCenter  | Internal cost code                            |
| Owner       | Person responsible                            |
| Environment | Prod / Dev / Test                             |
| Impact      | Mission-critical / High / Low                 |
