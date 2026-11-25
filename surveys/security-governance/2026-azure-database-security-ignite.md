**English** | [日本語](2026-azure-database-security-ignite.ja.md)

# Azure database security at Ignite 2026

## Overview

- **What it is.** An official Microsoft recap of security releases for Azure SQL Database, Azure Database for PostgreSQL Flexible Server, and Azure HorizonDB.
- **What it says.** Six enhancements reached general availability and three entered public preview across encryption, identity, masking, and networking.
- **Caveat.** The announcement establishes release status. Eligibility, region coverage, and migration impact depend on the specific service and configuration.

## Six practical takeaways

- Azure SQL Database lists AES-256 customer-managed Transparent Data Encryption (TDE) protectors and regex-based Dynamic Data Masking as generally available.
- Pausing and resuming Azure SQL TDE scans and using a managed identity per database are in public preview.
- PostgreSQL Flexible Server can change from VNet integration to a network configuration that supports private endpoints. Microsoft documents a one-way change and a break in connectivity.
- HorizonDB lists Private Link, Microsoft Entra authentication, and user-assigned managed identities as generally available.
- HorizonDB encryption at rest with customer-managed keys is in public preview. Microsoft Learn lists a restriction on combining it with geo-redundant backup.
- Proposed application. Inventory each workload's key custody, identity permissions, DNS and connection paths, and restore requirements before choosing a rollout.

## Publication and review scope

Pieter Vanhove, Microsoft Azure SQL Blog, November 25, 2026. Read the announcement and supporting Microsoft materials on November 26, 2026 JST. The table records availability as announced. Operational behavior has not been reproduced.

| Service | Change | Announced availability |
| --- | --- | --- |
| Azure SQL Database | AES-256 customer-managed TDE protector | GA |
| Azure SQL Database | Suspend and resume TDE scans | Public preview |
| Azure SQL Database | Regex-based Dynamic Data Masking | GA |
| Azure SQL Database | Database-level managed identity | Public preview |
| Azure Database for PostgreSQL Flexible Server | VNet-integrated server change to a private endpoint-capable configuration | GA |
| Azure HorizonDB | Azure Private Link | GA |
| Azure HorizonDB | Customer-managed keys for encryption at rest | Public preview |
| Azure HorizonDB | Microsoft Entra authentication | GA |
| Azure HorizonDB | User-assigned managed identities | GA |

## Evidence and limitations

- **Encryption and masking.** The TDE protector protects the database encryption key. Microsoft Learn documents AES-256 protectors for Azure SQL Database in Azure Key Vault Premium or Managed HSM. Regex masking changes returned values for nonprivileged users while leaving stored values intact. Privileged users and users with UNMASK can see the underlying values.
- **Identity.** Entra authentication concerns principals that connect to the database. Managed identities can give database workloads a credential-free route to supported Azure resources, subject to permissions on those resources. The Azure SQL preview documentation illustrates the scope with storage access.
- **Networking and recovery.** The PostgreSQL guide says the in-place network change is irreversible and that existing connections close. The server stays inaccessible until a supported connection path is configured. Verify private DNS, dependent clients, and replication connectivity in the cutover plan. HorizonDB documentation lists customer-managed keys and geo-redundant backup as mutually exclusive.
- **Evidence.** Microsoft explains intended behavior and release status. The announcement provides no independent availability or performance measurements.

## Application and low-cost check

Proposed and untried. Build a paper inventory for one database workload and check its required controls against Microsoft's documentation. Include keys and ownership, query masking and permissions, name resolution, private connectivity, and restore objectives. If a non-production environment is available, use synthetic records and verify access with the intended identities. Evaluate reconnection and restore in an isolated environment before considering a production migration.

## Related notes

- [Azure's Ignite 2026 platform announcements](../articles/2026-azure-ignite-platform-announcements.md)
- [Multi-cloud security architecture](2026-multi-cloud-security-architecture.md)

## Sources

- [Microsoft Azure SQL Blog announcement](https://techcommunity.microsoft.com/blog/azuresqlblog/whats-new-in-azure-database-security-stronger-encryption-simpler-identity-and-ne/4575935)
- [Microsoft Learn on customer-managed TDE](https://learn.microsoft.com/en-us/azure/azure-sql/database/transparent-data-encryption-byok-overview?view=azuresql)
- [Microsoft on suspending and resuming TDE scans](https://techcommunity.microsoft.com/blog/azuresqlblog/take-control-of-transparent-data-encryption-scans-suspend-and-resume-now-in-prev/4571096)
- [Microsoft Learn on regex-based masking](https://learn.microsoft.com/en-us/azure/azure-sql/database/dynamic-data-masking-regex?view=azuresql)
- [Microsoft on database-level identity for storage access](https://techcommunity.microsoft.com/blog/azuresqlblog/give-each-azure-sql-database-its-own-identity-for-storage-access-preview/4575974)
- [Microsoft Learn on changing PostgreSQL networking](https://learn.microsoft.com/en-us/azure/postgresql/network/how-to-migrate-vnet-private-endpoint-capable-server)
- [Microsoft Learn on HorizonDB scope and limitations](https://learn.microsoft.com/en-us/azure/horizondb/overview/overview)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
