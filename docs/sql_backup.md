---
title: "Microsoft SQL Server and Oracle Logs Backup"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/sql_backup.html"
last_updated: "11/12/2025"
product_version: "13.0.1.1009"
---

# Microsoft SQL Server and Oracle Logs Backup


|  |
| --- |
| ![Microsoft SQL Server and Oracle Logs Backup](images/icon_note.webp) NOTE |
| This and subsequent sections describe application-aware processing of Microsoft SQL Server and Oracle database systems in Veeam Agent for Microsoft Windows. You can perform item-level recovery of Microsoft SQL Server and Oracle systems if you use Veeam Agent for Microsoft Windows with Veeam Backup & Replication. For more information, see [Veeam Backup & Replication Documentation](https://www.veeam.com/documentation-guides-datasheets.html). |

Microsoft SQL Server Log Backup

You can instruct the Veeam Agent backup job to create volume level or file-level backups and also periodically back up database transaction logs. If Microsoft SQL Server fails, you can restore Microsoft SQL Server from the necessary restore point of the Veeam Agent backup. If you use Veeam Agent for Microsoft Windows with Veeam Backup & Replication, you can also use Veeam Explorer for Microsoft SQL Server to apply transaction logs and get databases on the Microsoft SQL Server to the necessary state between backups.

Requirements for Microsoft SQL Server Transaction Log Backup

* Veeam Agent for Microsoft Windows supports transaction log backups for the following systems:

* Microsoft SQL Server 2025
* Microsoft SQL Server 2022
* Microsoft SQL Server 2019
* Microsoft SQL Server 2017
* Microsoft SQL Server 2016
* Microsoft SQL Server 2014 SP2
* Microsoft SQL Server 2012 SP3

* The database whose logs you want to back up must use the Full or Bulk-logged recovery model. In this case, all changes of the Microsoft SQL Server state will be written to transaction logs, and you will be able to replay transaction logs to restore the Microsoft SQL Server. You can use the Microsoft SQL Server Management Studio to switch to one of these models. For more information, see [Microsoft documentation](http://msdn.microsoft.com/en-us/library/ms189275.aspx).

Oracle Log Backup

Veeam Agent for Microsoft Windows supports backup of Oracle database archived logs. If you use Veeam Agent for Microsoft Windows with Veeam Backup & Replication, you can use Veeam Explorer for Oracle to apply archived logs and get Oracle databases to the necessary state between backups.

Database archived logs are created by the Oracle system. The Oracle database can run in one of the following logging modes:

* ARCHIVELOG turned on — logs are saved and can be used for recovery purposes.

* ARCHIVELOG turned off — no archived logs are saved. We do not recommend this mode, because it does not provide proper disaster recovery.

With ARCHIVELOG turned on, the Oracle system stores database archived logs in a certain location on the machine that runs the database system, as specified by the database administrator. Veeam Agent for Microsoft Windows allows you to set up the following ways of log handling:

* Instruct the backup job to collect log files from the Oracle system and ship them to the backup location where they are stored next to regular backup files created by Veeam Agent for Microsoft Windows.
* Skip log processing — log files remain untouched and are preserved within the Veeam Agent backup.

If you enable application-aware processing for Oracle, during the job session Veeam Agent for Microsoft Windows collects information about the database and processes archived logs according to job settings. Application-specific settings are configured at the Guest Processing step of the New Backup Job wizard — you can specify how logs should be managed for Oracle databases.

Requirements for Oracle Archived Log Backup

* Veeam Agent for Microsoft Windows supports archived log backup and restore for Oracle database version 11.2 and later.
* Automatic Storage Management (ASM) is not supported.
* The database must run in the ARCHIVELOG mode.

In This Section

* [Database Log Backup Job](sql_backup_job.md)
* [How Microsoft SQL Server Log Backup Works](sql_backup_hiw.md)
* [How Oracle Archived Log Backup Works](oracle_backup_hiw.md)
* [Retention for Database Log Backups](sql_backup_retention.md)

Related Tasks

[Creating Backup Jobs](backup_job_create.md)


