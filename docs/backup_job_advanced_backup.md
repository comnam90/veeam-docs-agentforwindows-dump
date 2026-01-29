---
title: "Backup Settings"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_job_advanced_backup.html"
last_updated: "10/7/2025"
product_version: "13.0.1.1009"
---

# Backup Settings


To specify settings for a backup chain created with the backup job:

1. Click Advanced at one of the following steps of the wizard:

* [Local Storage](backup_job_drive.md) — if you have selected the Local storage option at the [Destination](backup_job_target.md) step of the wizard.
* Bucket/Container — if you have selected the Object storage option at the [Destination](backup_job_target.md) step of the wizard.
* [Shared Folder](backup_job_share.md) — if you have selected the Shared folder option at the [Destination](backup_job_target.md) step of the wizard.
* [Backup Repository](backup_job_vbr.md#repo) — if you have selected the Veeam backup repository option at the [Destination](backup_job_target.md) step of the wizard.
* [Backup Resources](backup_job_sp_settings.md#repo) — if you have selected the Veeam Cloud Connect repository option at the [Destination](backup_job_target.md) step of the wizard.

1. If you want to periodically create synthetic full backups, select the Create synthetic full backups periodically check box. Use the Monthly on or Weekly on selected days options to define scheduling settings.
2. If you want to periodically create active full backups, select the Create active full backups periodically check box. Use the Monthly on or Weekly on selected days options to define scheduling settings.

Keep in mind that to create active and synthetic full backups on selected days, Veeam Agent must run the backup job on these days. To learn more about backup job schedule, see [Scheduling Settings](backup_job_schedule.md).

|  |
| --- |
| ![Backup Settings](images/icon_note.webp) NOTE |
| Consider the following:   * Synthetic full backup is available only in the Workstation and Server editions of Veeam Agent for Microsoft Windows. * Synthetic full backup is not available for backup jobs targeted at object storage. * Before scheduling periodic full backups, you must make sure that you have scheduled the backup job to run on the enough free space on the target location. As an alternative, you can create active full backups manually when needed. For more information, see [Creating Active Full Backups](backup_active_full.md). * If you schedule the active full backup and synthetic full backup on the same day, Veeam Agent for Microsoft Windows will perform only active full backup. Synthetic full backup will be skipped. |

![Backup Settings](images/ep_backup_job_settings_backup.webp "Advanced Backup Settings")

Related Topics

* [Active Full Backup](active_full_backup.md)
* [Synthetic Full Backup](synthetic_full_backup.md)


