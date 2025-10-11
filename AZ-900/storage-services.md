# Azure Storage Services

## Table of Contents
1. [Azure Storage Account Overview](#azure-storage-account-overview)
   - [Storage Account Types](#storage-account-types)
   - [Storage Account Endpoints](#storage-account-endpoints)
2. [Azure Storage Redundancy](#azure-storage-redundancy)
   - [Redundancy in the Primary Region](#redundancy-in-the-primary-region)
   - [Redundancy in a Secondary Region](#redundancy-in-a-secondary-region)
   - [Read Access to Secondary Region](#read-access-to-secondary-region)
3. [Azure Storage Services](#azure-storage-services)
   - [Azure Blobs](#azure-blobs)
   - [Blob Storage Tiers](#blob-storage-tiers)
   - [Azure Files](#azure-files)
   - [Azure Queues](#azure-queues)
   - [Azure Disks](#azure-disks)
   - [Azure Tables](#azure-tables)
4. [Azure Data Migration Options](#azure-data-migration-options)
   - [Azure Migrate](#azure-migrate)
   - [Azure Data Box](#azure-data-box)
5. [Azure File Movement Options](#azure-file-movement-options)
   - [AzCopy](#azcopy)
   - [Azure Storage Explorer](#azure-storage-explorer)
   - [Azure File Sync](#azure-file-sync)

---

## Azure Storage Account

A storage account provides a **unique namespace** for your Azure Storage data 
that is **secure, highly available, durable, and scalable**. Data can be accessed from anywhere over HTTP or HTTPS.

### Storage Account Types

| Type                | Supported Services              | Redundancy Options                   | Usage                                                                          |
|---------------------|---------------------------------|--------------------------------------|--------------------------------------------------------------------------------|
| Standard GPv2       | Blob, Queue, Table, Azure Files | LRS, GRS, RA-GRS, ZRS, GZRS, RA-GZRS | Standard storage for most scenarios. NFS support requires premium file shares. |
| Premium Block Blobs | Blob                            | LRS, ZRS                             | High transaction or low-latency scenarios.                                     |
| Premium File Shares | Azure Files                     | LRS, ZRS                             | Enterprise or high-performance file shares with SMB and NFS.                   |
| Premium Page Blobs  | Page Blobs only                 | LRS                                  | High-performance page blob storage.                                            |

### Storage Account Endpoints

- **Unique namespace**: Every storage account must have a globally unique name (3–24 lowercase letters or numbers).  
- **Endpoint format**: `[accountname].blob.core.windows.net` (similar for file, queue, table services).

---

## Azure Storage Redundancy

Redundancy protects data from hardware failures, outages, and disasters. It ensures **availability and durability**.

### Redundancy in the Primary Region

Data is **always replicated three times** in the primary region.

- **Locally Redundant Storage (LRS)**: 3 copies in a single data center; durability: 11 nines. Lowest cost but less resilient to data center disasters.  
- **Zone-Redundant Storage (ZRS)**: 3 copies across availability zones; durability: 12 nines. High availability for zone-level failures.

### Redundancy in a Secondary Region

For higher durability, data can replicate to a **secondary region**:

- **Geo-Redundant Storage (GRS)**: Primary LRS replicated asynchronously to secondary region LRS; durability: 16 nines.  
- **Geo-Zone-Redundant Storage (GZRS)**: Primary ZRS replicated asynchronously to secondary LRS; combines zone availability and regional disaster protection.

### Read Access to Secondary Region

- **RA-GRS / RA-GZRS**: Enables read access to secondary region even when primary is online.  
- Recovery Point Objective (RPO): Typically < 15 minutes, no SLA guarantees for replication lag.

---

## Azure Storage Services

Azure provides several storage services:

- **Azure Blobs**: Massively scalable object storage for unstructured data (text/binary). Supports Data Lake Storage Gen2.  
- **Azure Files**: Managed file shares via SMB or NFS, accessible from Windows, Linux, macOS.  
- **Azure Queues**: Reliable messaging between application components.  
- **Azure Disks**: Block-level storage for Azure VMs.  
- **Azure Tables**: NoSQL datastore for structured, non-relational data.

### Azure Blobs

- Stores **text or binary data**.
- Ideal for: images, documents, streaming media, backup, analysis.  
- Access via: URL, REST API, client libraries, PowerShell, CLI, Storage Explorer.

### Blob Storage Tiers

| Tier    | Usage                   | Retention   |
|---------|-------------------------|-------------|
| Hot     | Frequently accessed     | -           |
| Cool    | Infrequently accessed   | ≥ 30 days   |
| Cold    | Rarely accessed         | ≥ 90 days   |
| Archive | Rarely accessed offline | ≥ 180 days  |

### Azure Files

- Managed file shares with SMB/NFS.
- Fully managed and resilient.  
- Supports cloud tiering and Azure File Sync.  
- Can replace on-premises file shares seamlessly.

### Azure Queues

- Stores large numbers of messages (up to 64 KB each).  
- Access via HTTP/HTTPS.  
- Integrates with Azure Functions for event-driven processing.

### Azure Disks

- Managed block-level volumes for Azure VMs.  
- Conceptually like physical disks, but virtualized and highly available.

### Azure Tables

- NoSQL storage for structured, non-relational data.  
- Accessible inside and outside Azure cloud.

---

## Azure Data Migration Options

### Azure Migrate

- Unified platform to assess and migrate on-premises workloads to Azure.  
- Includes tools:
  - **Discovery & Assessment**
  - **Server Migration**
  - **Database Migration Assistant**
  - **Azure Database Migration Service**
  - **App Service Migration Assistant**

### Azure Data Box

- Physical device for offline transfer of **up to 80 TB** of data.  
- Used for:
  - One-time migrations
  - Large media imports
  - Initial bulk transfer with periodic sync
  - Disaster recovery or export to on-premises

- **Security**: Data wiped according to NIST 800-88r1 standards.

---

## Azure File Movement Options

### AzCopy

- Command-line tool to **upload, download, copy, or sync blobs/files**.  
- Synchronization is **one-directional**.

### Azure Storage Explorer

- GUI for managing blobs and files across storage accounts.  
- Uses AzCopy under the hood.  
- Supports Windows, macOS, Linux.

### Azure File Sync

- Centralizes file shares in Azure Files while keeping local access.  
- Supports SMB/NFS/FTPS.  
- Enables caching, cloud tiering, and easy server replacement.

