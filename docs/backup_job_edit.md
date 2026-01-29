---
title: "Editing Backup Job Settings"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_job_edit.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Editing Backup Job Settings


If you want to change settings of a backup job, you can edit it at any time. For example, you may want to edit the backup job to add a new folder to the backup scope, change the target location or job scheduling settings.

To access backup job settings, do one of the following:

* Double-click the Veeam Agent for Microsoft Windows icon in the system tray or right-click it and select Control Panel. Then hover over the name of the backup job whose settings you want to change, and select Edit job.
* Right-click the Veeam Agent for Microsoft Windows icon in the system tray and select Backup > Configure backup.

|  |
| --- |
| ![Editing Backup Job Settings](images/icon_note.webp) NOTE |
| The Backup option is not available in the system tray menu if multiple backup jobs are configured in Veeam Agent for Microsoft Windows. |

Then edit the job settings as required. To learn more about available job settings, see [Creating Backup Jobs](backup_job_create.md).

If you change the target location for the backup job, during the next backup job session Veeam Agent for Microsoft Windows will perform full data backup. All subsequent backup sessions will produce incremental backups — Veeam Agent for Microsoft Windows will copy only changed data to the target location and add a new incremental backup file to the backup chain.

If you change the backup scope for the backup job, during the next backup job session Veeam Agent for Microsoft Windows will create a new incremental backup. The backup will contain the following data:

* All data blocks pertaining to new data added to the backup scope.
* Changed data blocks pertaining to original data in the backup scope (data that was processed by the job at the time before you changed the backup scope).

|  |
| --- |
| ![Editing Backup Job Settings](images/icon_tip.webp) TIP |
| Full backup takes much more time than incremental backup. If you change the target location, you can copy an existing backup chain to the new location manually. In this case, the new backup job session will produce an incremental backup file and add it to the backup chain. |

Editing Encryption Settings

If you change encryption settings for the backup job, during the next backup job session Veeam Agent for Microsoft Windows will create active full backup — encrypted (if encryption was enabled) or unencrypted (if encryption was disabled). All subsequent backup sessions will produce incremental backups.

Enabling or disabling encryption does not affect backup files that were created before you have changed encryption settings.

If the backup chain contains encrypted and unencrypted backup files, you need to provide a password to restore data from any restore point in this chain. After all encrypted backup files are removed from the backup chain according to retention policy, you will be able to restore data from remaining unencrypted restore points without providing a password.


