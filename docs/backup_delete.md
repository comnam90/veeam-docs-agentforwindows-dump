---
title: "Deleting Backups"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_delete.html"
last_updated: "8/10/2023"
product_version: "13.0.1.1009"
---

# Deleting Backups


Backup files created with Veeam Agent for Microsoft Windows are removed automatically according to the retention policy settings.

If necessary, you can remove the backup files manually with a file manager, for example, Microsoft Windows Explorer. In this case, delete the whole backup chain from the target location. After you remove the whole backup chain from the target location, during the next backup job session, Veeam Agent for Microsoft Windows will produce a new full backup. All subsequent backups will be incremental.

|  |
| --- |
| IMPORTANT |
| Do not delete individual backup files from the backup chain. If you delete a full or incremental backup file, the chain will be broken. In this case, Veeam Agent for Microsoft Windows may fail to perform the scheduled backup next time. |

Deleting Backups with Command Line Interface

You can use the command line interface to delete Veeam Agent backups from a Veeam Cloud Connect repository or object storage.

When you delete a backup from a Veeam Cloud Connect repository, Veeam Agent for Microsoft Windows deletes actual backup files from the repository and removes records about the backup from the Veeam Backup & Replication database on the SP backup server. After information about the backup is removed from the SP backup server, Veeam Backup & Replication removes this information from its database and console on the tenant backup server, too.

Before you delete a backup, check the following prerequisites:

* To perform the delete backup operation, you must run the command line interface with administrative privileges.
* The delete backup operation cannot be performed if a backup or a restore task is currently running.
* Check the following backup job settings:

* The target location from which you want to delete a backup must be specified as a target location for backup files in the backup job settings.
* Credentials of the user account whose backup you want to delete must be specified in the backup job settings.

To learn more, see [Veeam Cloud Connect Repository Settings](backup_job_sp_settings.md) and [Object Storage Settings](backup_job_object_storage.md).

To delete a Veeam Agent backup, use a command with the following syntax:

|  |
| --- |
| "C:\Program Files\Veeam\Endpoint Backup\Veeam.EndPoint.Manager.exe" /deletebackup |

|  |
| --- |
| ![Deleting Backups](images/icon_tip.webp) TIP |
| If more than one backup job is configured, Veeam Agent for Microsoft Windows will provide a list of backup jobs. To delete a backup, type the number that is displayed next to the backup job whose backup you want to delete. |

Veeam Agent for Microsoft Windows can provide the following exit codes:

* 0 — backup job was successfully deleted
* -1 — the delete backup job operation failed


