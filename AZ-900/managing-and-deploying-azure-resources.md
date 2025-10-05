# Features and tools for managing and deploying Azure resources

---

## Table of Contents
1. [Tools for Interacting with Azure](#tools-for-interacting-with-azure)
2. [Azure Arc](#azure-arc)   
3. [Azure Resource Manager (ARM)](#azure-resource-manager-arm) 
4. [ARM Templates](#arm-templates)   

---

## Tools for Interacting with Azure

### Azure Portal
- Web-based **GUI** to manage Azure resources.
- No command-line skills needed.
- Features:
  - Build & monitor simple to complex deployments
  - Create custom dashboards
  - Accessible and continuously updated
  - Highly available across all datacenters

### Azure Cloud Shell
- Browser-based shell accessible via Azure Portal.
- Pre-authenticated with your Azure account.
- Supports:
  - **Azure PowerShell**
  - **Azure CLI (Bash)**
- No local installation needed.

### Azure PowerShell
- Uses **cmdlets** to interact with Azure via REST API.
- Ideal for:
  - Automation
  - Infrastructure tasks
  - Deployment scripts
- Available via:
  - Cloud Shell
  - Windows, Linux, macOS (local install)

### Azure CLI
- Functionally similar to Azure PowerShell.
- Uses **Bash-style commands**.
- Supports:
  - Automation
  - Complex orchestration
  - One-off resource operations
- Available via:
  - Cloud Shell
  - Windows, Linux, macOS (local install)

---

## Azure Arc

Manage hybrid and multi-cloud resources using Azure tools.

### What Azure Arc Enables
- Projects non-Azure resources into Azure Resource Manager (ARM).
- Manages:
  - On-premises servers
  - Kubernetes clusters
  - Databases
  - Multi-cloud VMs
- Unified governance across hybrid + multi-cloud

### Key Benefits
- Use Azure services outside Azure.
- Apply Azure security, compliance, and policies universally.
- Support both IT operations and DevOps models.
- Create **custom locations** via Kubernetes extensions.

### Supported Resources (Outside Azure)
- Servers
- Kubernetes clusters
- SQL Server
- Azure data services
- Virtual machines (preview)

---

## Azure Resource Manager (ARM)

ARM is the **control plane** for all Azure resources.

### How It Works
- Every Azure action (via Portal, CLI, API, SDK) goes through ARM.
- Authenticates, authorizes, and executes requests using a unified API.

### Key Benefits
- **Template-based deployment** (JSON ARM templates)
- **Group-based management** of resources
- **Consistent redeployment**
- **Dependency ordering**
- RBAC built-in
- Tagging support
- Cost tracking via tags

---

## ARM Templates

**Definition:**  
Declarative JSON files that define your infrastructure and configurations.

### Advantages
- Automate deployments with consistency
- Treat infrastructure as code (IaC)
- Simplify large or repeated deployments
- Enable version control and collaboration

### Bicep 
A domain-specific language (DSL) for deploying Azure resources using infrastructure as code (IaC). 
It’s designed to make working with Azure Resource Manager (ARM) templates easier, cleaner, and more readable.
