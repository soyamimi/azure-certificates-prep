# Cloud service types

## 1. Infrastructure as a Service (IaaS)
- **Definition**
  - Provides maximum control over cloud resources
  - Cloud provider manages: hardware, network connectivity, physical security
  - User manages: OS, network, storage, databases, applications
- **Shared Responsibility Model**
  - Provider: physical infrastructure and internet access
  - User: OS installation, configuration, patching, updates, security
- **Scenarios**
  - **Lift-and-shift migration**: Move existing on-premises workloads to cloud infrastructure
  - **Testing and development**: Rapidly replicate and manage dev/test environments with full control

## 2. Platform as a Service (PaaS)
- **Definition**
  - Middle ground between IaaS and SaaS
  - Provider manages: physical infrastructure, OS, middleware, development tools, business intelligence services
  - Reduces the need to maintain development infrastructure
- **Shared Responsibility Model**
  - Provider: infrastructure, OS, databases, development tools
  - User: may manage network settings, connectivity, application security, and directory infrastructure
- **Scenarios**
  - **Development framework**: Build cloud-based applications with built-in software components
  - **Analytics/Business Intelligence**: Tools to analyze data, predict outcomes, improve decision-making

## 3. Software as a Service (SaaS)
- **Definition**
  - Fully developed application provided as a service
  - Examples: email, messaging apps, financial software
  - Least flexible but easiest to deploy
- **Shared Responsibility Model**
  - Provider: physical security, infrastructure, network, application development and patching
  - User: data, devices, and user access
- **Scenarios**
  - Email and messaging
  - Business productivity applications
  - Finance and expense tracking
