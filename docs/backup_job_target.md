---
title: "Step 5. Select Backup Destination"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_job_target.html"
last_updated: "12/10/2024"
product_version: "13.0.1.1009"
---

# Step 5. Select Backup Destination


At the Destination step of the wizard, select a target location for the created backup.

You can store backup files in one of the following locations:

* Local storage — select this option if you want to save the backup on a removable storage device attached to the computer or on a local computer drive. With this option selected, you will pass to the [Local Storage](backup_job_drive.md) step of the wizard.
* Object storage — select this option if you want to save the backup in object storage. With this option selected, you will pass to the [Object storage](backup_job_object_storage.md) step of the wizard.
* Shared folder — select this option if you want to save the backup in a network shared folder. With this option selected, you will pass to the [Shared folder](backup_job_share.md) step of the wizard.
* Veeam backup repository — select this option if you want to save the backup in a backup repository managed by the Veeam backup server. With this option selected, you will pass to the [Backup Server](backup_job_vbr.md) step of the wizard.
* Veeam Cloud Connect repository — select this option if you want to save the backup in a cloud repository exposed to you by the Veeam Cloud Connect service provider. With this option selected, you will pass to the [Service Provider](backup_job_sp_settings.md) step of the wizard.

|  |
| --- |
| ![Step 5. Select Backup Destination](images/icon_important.webp) IMPORTANT |
| Consider the following:   * We strongly recommend that you store backups in the external location like USB storage device or shared network folder. You can also keep your backup files on the separate non-system local drive. * If you select to store the backup in a local folder included in the backup scope, Veeam Agent will automatically exclude this folder from the backup. * For the Free product edition, the Object storage and the Veeam Cloud Connect repository options are not available. |

![Step 5. Select Backup Destination](images/ep_backup_job_destination.webp "Select Backup Destination")


