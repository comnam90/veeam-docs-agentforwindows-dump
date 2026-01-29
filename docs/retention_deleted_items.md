---
title: "Retention Policy for Outdated Backups"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/retention_deleted_items.html"
last_updated: "9/13/2024"
product_version: "13.0.1.1009"
---

# Retention Policy for Outdated Backups


In addition to specifying general retention policy settings, you can define retention policy for outdated backups. An outdated backup is a backup for which no new restore points were created within the last <N> days. Retention policy for outdated backups helps to avoid keeping redundant data in the target location: once the outdated backup retention period is over, an outdated backup is automatically removed from the target location.

Veeam Agent for Microsoft Windows offers retention policy for outdated backups that are created in the following types of target locations:

* Veeam backup repository
* Veeam Cloud Connect repository

To specify retention policy for outdated backups, you must enable the Remove deleted items data after <N> days option in backup job settings and specify the number of days for which data of outdated backups must be retained in the backup repository. By default, Veeam Agent for Microsoft Windows retains outdated backups for 30 days. You can change the number of days to retain outdated backups if necessary.

Consider the following:

* You must use retention policy for outdated backups wisely. We strongly recommend that you set retention policy for outdated backups to 7 days or more to prevent unwanted data loss.

* The Remove deleted items after <N> days option lets you control data of backups for which Veeam Agent for Microsoft Windows does not produce new restore points for some time. In addition to it, Veeam Agent for Microsoft Windows applies general retention policy rules to maintain the necessary number of restore points in the backup chain. To learn more, see [Backup Retention Policy](retention.md).

![Retention Policy for Outdated Backups](images/retention_policy_deleted_items.webp "The Remove Deleted Items After <N> Days Option Enabled")

How Retention Policy for Outdated Backups Works

Although you specify retention policy settings for outdated backups in Veeam Agent for Microsoft Windows, actions required to track and delete outdated Veeam Agent backups are taken on the Veeam Backup & Replication side.

To perform necessary actions, Veeam Backup & Replication performs background retention for backups on the backup server. The background retention starts automatically every 24 hours at 00:30.

|  |
| --- |
| ![Retention Policy for Outdated Backups](images/icon_note.webp) NOTE |
| You can change the background retention schedule with registry values. For more information, [contact Veeam Customer Support](support_report.md). |

During the background retention session, Veeam Backup & Replication performs the following operations:

1. Veeam Backup & Replication checks the configuration database to detect Veeam Agent backups that reside in the backup repository.
2. For each Veeam Agent backup, Veeam Backup & Replication checks whether the following conditions are met:

1. The configuration database contains information about the backup job that created the Veeam Agent backup.

The configuration database does not contain information about the backup job that created the backup in the following cases:

* The backup job that created the backup was removed in Veeam Agent for Microsoft Windows.
* The Veeam Agent backup was imported in the Veeam Backup & Replication console.
* The Veeam Agent backup is a standalone full backup.

If the configuration database does not contain information about the backup job that created the backup, Veeam Backup & Replication does not remove such a backup from the backup repository.

1. The Remove deleted items after <N> days option is enabled in the backup job settings. If the option is enabled, Veeam Backup & Replication checks whether the following conditions are met:

* No new restore points were created by the backup job for the last <N> days.
* No new backup job sessions were detected by Veeam Backup & Replication for the last <N> days.
* [For backup jobs with database log backup enabled] No database log copies (Microsoft SQL Server transaction log or Oracle archive log copies) were created by the database log backup job for the last <N> days.

Where <N> is the number of days specified for the Remove deleted items data after <N> days option.

1. If all the conditions listed in the step 2 are met, Veeam Backup & Replication removes the Veeam Agent backup from the configuration database and deletes actual backup files from the backup repository.

Related Topics

[Creating Backup Jobs](backup_job_create.md)


