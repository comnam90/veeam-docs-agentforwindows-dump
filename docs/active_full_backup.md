---
title: "Active Full Backup"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/active_full_backup.html"
last_updated: "10/23/2023"
product_version: "13.0.1.1009"
---

# Active Full Backup


In some cases, you need to regularly create a full backup. For example, your corporate backup job may require that you create a full backup on weekend and run incremental backup on work days. To let you conform to these requirements, Veeam Agent lets you create active full backups.

When Veeam Agent performs active full backup, it produces a full backup file and adds this file to the backup chain.

The active full backup resets the backup chain. All incremental backup files use the latest active full backup file as a new starting point. A previously used full backup file and its subsequent incremental backup files remain on the disk. After the last incremental backup file created prior to the active full backup becomes outdated, Veeam Agent automatically deletes the previous backup chain. To learn more, see [Retention Policy for Active Full Backups](#retention).

![Active Full Backup](images/active_full_backup.webp)

You can create active full backups manually or schedule a backup job to create active full backups periodically.

* To create an active full backup manually, use the Active full backup command from the Veeam Agent Tray menu. To learn more, see [Creating Active Full Backups](backup_active_full.md).
* To schedule active full backups, specify scheduling settings in the Advanced Settings window of the New Backup Job wizard. You can schedule active full backups to run weekly, for example, every Saturday, or monthly, for example, every first Thursday of a month.

![Active Full Backup](images/active_full_backup_conf.webp "Create Active Full Backups Periodically")

Retention Policy for Active Full Backups

To be able to restore data from a Veeam Agent backup, you need to have a full backup file and a chain of subsequent incremental backup files on the disk. If you delete a full backup file, the whole chain of incremental backup files will become useless. In a similar manner, if you delete any incremental backup file before the point to which you want to roll back, you won’t be able to restore data (since later incremental backup files depend on earlier incremental backup files).

For this reason, if you create an active full backup, in some days there will be more restore points on the disk than specified by retention policy settings. Veeam Agent will remove the full backup chain only after the last incremental backup file in the chain becomes outdated.

Related Tasks

* [Creating Backup Jobs](backup_job_create.md)
* [Creating Active Full Backups](backup_active_full.md)


