---
title: "Guest Processing"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/guest_processing.html"
last_updated: "11/12/2025"
product_version: "13.0.1.1009"
---

# Guest Processing


For Server edition of Veeam Agent for Microsoft Windows, you can specify guest processing options. Veeam Agent for Microsoft Windows offers the following guest processing options:

* [Application-aware processing](application_aware_processing.md). You can create transactionally consistent backups of servers running applications that support Microsoft VSS. Application-aware processing guarantees that you can perform restore from Veeam Agent backups without data loss.
* [Pre-freeze and post-thaw scripts](pre_post_scripts.md). You can use pre-freeze and post-thaw scripts to quiesce applications that do not support Microsoft VSS.
* [Transaction log truncation](transaction_truncation.md). You can set up the backup job to truncate transaction logs after the job successfully completes.
* [Transaction log backup for Microsoft SQL Server and Oracle](sql_backup.md). You can set up the backup job to back up transaction logs from servers running Microsoft SQL Server and archived logs of Oracle database systems.
* [File system indexing](indexing.md). You can set up the backup job to create a catalog of files and folders on the Veeam Agent computer OS. If you use Veeam Agent for Microsoft Windows with Veeam Backup & Replication, you will be able to search for individual files in Veeam Agent backups and perform 1-click restore in Veeam Backup Enterprise Manager.

File system indexing is optional. If you do not enable this option in the backup job settings, you will still be able to perform 1-click restore from the Veeam Agent backup. For more information, see the [Veeam Backup Enterprise Manager User Guide](https://www.veeam.com/documentation-guides-datasheets.html).

Supported Applications

Veeam Agent for Microsoft Windows supports VSS-aware processing for the following systems:

| Specification | Requirement |
| --- | --- |
| Microsoft Active Directory Domain Controllers | The following versions of Microsoft Active Directory Domain Services servers (domain controllers) are supported:   * Microsoft Windows Server 2025 * Microsoft Windows Server 2022 * Microsoft Windows Server 2019 * Microsoft Windows Server 2016 * Microsoft Windows Server 2012 R2   Minimum supported domain and forest functional level is Windows Server 2003. |
| Microsoft Exchange | The following versions of Microsoft Exchange are supported:   * Microsoft Exchange Subscription Edition * Microsoft Exchange 2019 * Microsoft Exchange 2016 |
| Microsoft SharePoint | The following versions of Microsoft SharePoint Server are supported:   * Microsoft SharePoint Server Subscription Edition * Microsoft SharePoint Server 2019 * Microsoft SharePoint Server 2016   All editions are supported (Foundation, Standard, Enterprise). |
| Microsoft SQL Server | The following versions of Microsoft SQL Server are supported:   * Microsoft SQL Server 2025 * Microsoft SQL Server 2022 * Microsoft SQL Server 2019 * Microsoft SQL Server 2017 * Microsoft SQL Server 2016 * Microsoft SQL Server 2014 * Microsoft SQL Server 2012   All editions of Microsoft SQL Server except LocalDB are supported. |
| Oracle | Oracle Database from version 11g to version 21c is supported for the following operating systems:   * Microsoft Windows Server 2025  * Microsoft Windows Server 2022 * Microsoft Windows Server 2019  * Microsoft Windows Server 2016 * Microsoft Windows Server 2012 R2   Important notes:   * Automatic Storage Management (ASM) is not supported. * Oracle Real Application Clusters (RAC) are not supported. * Oracle servers using Data Guard are not supported. * Oracle Database Express Edition is supported. * 32-bit Oracle running on 64-bit operating systems is not supported. |

Related Tasks

[Creating Backup Jobs](backup_job_create.md)


