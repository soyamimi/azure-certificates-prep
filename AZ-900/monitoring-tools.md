# Monitoring tools in Azure

---

## Table of Contents
1. [Azure Advisor](#azure-advisor)
2. [Azure Service Health](#azure-service-health)
3. [Azure Monitor](#azure-monitor)

---

## Azure Advisor

**Azure Advisor** is a personalized recommendation service 
that analyzes your Azure resources and provides guidance to improve:

- Reliability: Ensures continuity of mission-critical applications
- Security: Detects vulnerabilities and mitigates potential threats
- Performance: Optimizes the speed and efficiency of resources
- Operational Excellence: Encourages best practices for deployment and resource management
- Cost: Identifies areas to reduce and optimize spending

You can view, filter, and act on recommendations using:

- Azure Portal  
- Azure Advisor API  
- Alerts and notifications

---

## Azure Service Health

**Azure Service Health** keeps you informed about issues affecting:

- Global Azure services
- Azure services you use
- Your specific Azure resources

It includes three main components:

### 1. Azure Status
- Provides a global view of all Azure services and regions
- Publicly accessible
- Used to check large-scale outages

### 2. Service Health
- Offers a personalized view based on your subscriptions, regions, and services
- Includes alerts for outages, planned maintenance, and incidents

### 3. Resource Health
- Displays the status of individual resources (e.g., virtual machines, storage accounts)
- Detects availability issues
- Can trigger alerts through Azure Monitor

Additional features:
- Historical alerts for review
- Links to Microsoft support when workloads are impacted

---

## Azure Monitor

**Azure Monitor** is a comprehensive platform for collecting, analyzing, visualizing, and responding to telemetry from:

- Azure resources
- On-premises environments
- Other cloud providers

### Azure Log Analytics

- Used to query and analyze log data
- Supports Kusto Query Language (KQL)
- Enables sorting, filtering, trend analysis, and data exploration

### Azure Monitor Alerts

Alerts trigger when certain conditions or thresholds are met. Two alert types:

- Metric-based alerts: Near real-time, based on numeric thresholds
- Log-based alerts: Support complex logic across multiple data sources

Uses Action Groups to:
- Notify users
- Trigger automation or remediation actions

### Application Insights

Monitors performance and behavior of web applications running in:

- Azure
- On-premises environments
- Other clouds

Tracks key metrics such as:
- Request/response times and failures
- Dependency performance
- User sessions and page views
- CPU, memory, and network usage

Also supports synthetic transactions to monitor applications during low-traffic periods.
