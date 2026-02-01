---
title: "Synthetic Full Backup"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/synthetic_full_backup.html"
last_updated: "1/30/2026"
product_version: "13.0.1.1009"
---

# Synthetic Full Backup


In some situations, running active full backups periodically may not be an option. Active full backups are resource-intensive and consume considerable amount of network bandwidth. As an alternative, you can create synthetic full backups.

|  |
| --- |
| NOTE |
| Consider the following:   * Synthetic full backup is available only in the Workstation and Server editions of Veeam Agent for Microsoft Windows. * Synthetic full backup is not available for backup jobs targeted at object storage. |

In terms of data, the synthetic full backup is identical to a regular full backup. Synthetic full backup produces a VBK file that contains all data that you have chosen to back up. The difference between active and synthetic full backup lies in the way how backed-up data is retrieved:

* When you perform active full backup, Veeam Agent for Microsoft Windows reads backed-up data, compresses it and copies it to the target location.
* When you perform synthetic full backup, Veeam Agent for Microsoft Windows does not retrieve all backed-up data from the Veeam Agent computer. Instead, it creates a new incremental backup and then synthesizes a full backup from data you already have on the target location. Veeam Agent for Microsoft Windows accesses the previous full backup file and a chain of subsequent incremental backup files in the backup chain including a new incremental backup, consolidates data from these files and writes consolidated data into a new full backup file. As a result, the created synthetic full backup file contains the same data as an active full backup.

The synthetic full backup has a number of advantages:

* The synthetic full backup does not use network resources: it is created from backup files you already have on the target location.
* The synthetic full backup produces less load on the production environment: it is synthesized right on the target location.

Veeam Agent for Microsoft Windows treats synthetic full backups as regular full backups. As well as any other full backup file, the synthetic full backup file resets the backup chain. All subsequent incremental backup files use the synthetic full backup file as a new starting point.

A previously used full backup file and its subsequent incremental backup files remain on the disk. After the last incremental backup file created prior to the synthetic full backup becomes outdated, Veeam Agent for Microsoft Windows automatically deletes the previous backup chain. To learn more, see [Retention Policy for Synthetic Full Backups](#retention).

To create synthetic full backups, you must enable the Create synthetic full backups periodically option and schedule creation of synthetic full backups in the backup job settings.

![Synthetic Full Backup](images/ep_backup_job_settings_backup.webp "Create Synthetic Full Backups Periodically")

Retention Policy for Synthetic Full Backups

To be able to restore data from a Veeam Agent backup, you need to have a full backup file and a chain of subsequent incremental backup files on the disk. If you delete a full backup file, the whole chain of incremental backup files will become useless. In a similar manner, if you delete any incremental backup file before the point to which you want to roll back, you will not be able to restore data (since later incremental backup files depend on earlier incremental backup files).

For this reason, if you set up the backup job to create synthetic full backups, in some days there will be more restore points on the disk than specified by retention policy settings. Veeam Agent for Microsoft Windows will remove the full backup chain only after the last incremental backup file in the chain becomes outdated.

Related Tasks

[Creating Backup Jobs](backup_job_create.md)


