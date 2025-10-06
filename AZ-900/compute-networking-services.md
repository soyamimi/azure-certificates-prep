# Azure compute and networking services

## Table of Contents
1. [Azure Virtual Machines](#azure-virtual-machines)
   - [Scale VMs in Azure](#scale-vms-in-azure)
   - [Virtual Machine Scale Sets](#virtual-machine-scale-sets)
   - [Virtual Machine Availability Sets](#virtual-machine-availability-sets)
2. [Azure Virtual Desktop](#azure-virtual-desktop)
3. [Azure Containers](#azure-containers)
   - [Azure Container Instances](#azure-container-instances)
   - [Azure Container Apps](#azure-container-apps)
   - [Azure Kubernetes Service (AKS)](#azure-kubernetes-service-aks)
4. [Azure Functions (Serverless Computing)](#azure-functions-serverless-computing)
5. [Application Hosting Options](#application-hosting-options)
   - [Azure App Service](#azure-app-service)
6. [Azure Virtual Networking](#azure-virtual-networking)
7. [Azure Virtual Private Networks (VPNs)](#azure-virtual-private-networks-vpns)
8. [Azure ExpressRoute](#azure-expressroute)
9. [Azure DNS](#azure-dns)

---

## Azure Virtual Machines

Azure Virtual Machines (VMs) provide **Infrastructure as a Service (IaaS)**
— giving you complete control over the operating system, configuration, and installed software.

**Use Cases:**
- Full control over the OS
- Running custom software
- Hosting configurations and testing environments

**Key Points:**
- VMs eliminate the need to buy or maintain physical hardware.
- You still manage updates, patching, and configurations.
- You can use pre-configured images to quickly provision new VMs.

---

### Scale VMs in Azure

You can run:
- **Single VMs** for development or small tasks.
- **Groups of VMs** for redundancy and scalability.

Azure offers tools like **Scale Sets** and **Availability Sets** to manage large deployments.

---

### Virtual Machine Scale Sets

Scale sets manage identical, load-balanced VMs automatically.

**Benefits:**
- Centralized management and updates.
- Auto-scaling based on demand or schedule.
- Built-in load balancing.

**Ideal for:**
- Compute-intensive apps
- Big data and containerized workloads

---

### Virtual Machine Availability Sets

Availability sets ensure high availability by spreading VMs across **update domains** and **fault domains**.

- **Update Domain:** VMs updated/rebooted together during maintenance.
- **Fault Domain:** VMs grouped by power source and network switch.

Availability Sets are free — you only pay for the VMs.


---

## Azure Virtual Desktop

**Azure Virtual Desktop (AVD)** is a cloud-based desktop and app virtualization service.

**Key Features:**
- Access Windows from anywhere via browser or app.
- Supports multi-session Windows 10/11.
- Centralized security via Microsoft Entra ID (Azure AD).
- MFA and RBAC for secure access.
- Data and apps run in Azure, not on user devices.

Azure Virtual Desktop reduces data leakage risk because data never leaves Azure.

---

## Azure Containers

Containers package apps and dependencies together for lightweight, consistent deployment.

**Key Advantages:**
- Fast, scalable, and portable
- No OS management required
- Ideal for microservices and DevOps pipelines

---

### Azure Container Instances

- Easiest way to run containers in Azure.
- Fully managed **Platform as a Service (PaaS)**.
- No need to manage VMs or orchestrators.

---

### Azure Container Apps

- PaaS for hosting containerized applications.
- Supports auto-scaling and load balancing.
- Ideal for serverless microservices.

---

### Azure Kubernetes Service (AKS)

AKS provides **container orchestration** — managing container deployment, scaling, and lifecycle.

**Use AKS when:**
- You have many containers to manage.
- You need orchestration or scaling logic.


---

## Azure Functions (Serverless Computing)

**Azure Functions** let you run event-driven code without managing servers.

**Key Benefits:**
- Pay only for execution time.
- Auto-scales based on demand.
- Supports triggers (HTTP, timers, events).
- Can be **stateless** or **Durable (stateful)**.


---

## Application Hosting Options

Azure offers several hosting options depending on control and simplicity needs.

- **VMs:** Full control, manual maintenance.
- **Containers:** Lightweight, portable, scalable.
- **App Service:** Managed hosting, auto-scaling, and CI/CD support.

---

### Azure App Service

- Build and host web apps, APIs, and backends.
- Supports Windows/Linux and multiple languages.
- Integrates with GitHub, Azure DevOps, and CI/CD pipelines.
- Auto-scaling and load balancing included.

---

## Azure Virtual Networking

Azure Virtual Networks (VNets) connect Azure resources securely.

**Capabilities:**
- Isolation and segmentation
- Internet and internal communications
- Integration with on-prem networks
- Route and filter network traffic

**Components:**
- **Subnets:** Logical segmentation of networks
- **NSGs:** Control inbound/outbound traffic
- **Route Tables:** Define traffic flow
- **Peering:** Connect VNets privately across regions

VNet peering keeps traffic on Microsoft’s backbone, not the public Internet.

---

## Azure Virtual Private Networks (VPNs)

A VPN provides a **secure, encrypted tunnel** between networks over the Internet.

### VPN Gateways
Enable:
- Site-to-site (datacenter to Azure)
- Point-to-site (device to Azure)
- Network-to-network (VNet to VNet)

**Types:**
- **Policy-based:** Uses static IP address pairs.
- **Route-based:** Uses routing protocols (preferred for dynamic networks).

**High Availability:**
- Active/Standby (default)
- Active/Active (for redundancy)
- ExpressRoute failover
- Zone-redundant gateways

---

## Azure ExpressRoute

ExpressRoute provides a **private, dedicated connection** between on-premises infrastructure and Azure.

**Benefits:**
- Doesn’t use public Internet
- Higher reliability and speed
- Consistent latency and secure connectivity

**Connectivity Models:**
- Cloud Exchange Colocation
- Point-to-Point Ethernet
- Any-to-Any Network
- Directly via ExpressRoute sites

ExpressRoute connections are private — data does not traverse the public Internet.

---

## Azure DNS

Azure DNS hosts and manages your **domain name system (DNS)** records in Azure.

**Features:**
- High reliability and global performance
- Integrated Azure RBAC and activity logs
- Supports **public** and **private** DNS zones
- Supports **alias records** for dynamic resource mapping

**Limitations:**
- Azure DNS doesn’t sell domains — use App Service domains or third-party registrars.

---

### Summary 

| Service         | Type       | Key Feature                   | 
|-----------------|------------|-------------------------------|
| Azure VMs       | IaaS       | Full control over OS          | 
| Virtual Desktop | PaaS       | Secure remote desktops        | 
| Containers      | PaaS       | Lightweight app deployment    | 
| Azure Functions | Serverless | Event-based execution         | 
| App Service     | PaaS       | Host web/API/mobile apps      | 
| Virtual Network | Core Infra | Secure resource communication | 
| VPN Gateway     | Network    | Encrypted connection          | 
| ExpressRoute    | Network    | Private connectivity          | 
| Azure DNS       | Core Infra | Manage DNS in Azure           | 
