---
title: "Moving Veeam Agent Backups to Veeam Backup Repository"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/appendix_move_backups_to_vbr.html"
last_updated: "12/4/2024"
product_version: "13.0.1.1009"
---

# Moving Veeam Agent Backups to Veeam Backup Repository


This topic describes how to place existing Veeam Agent backups in a Veeam backup repository so that the Veeam Agent backup job continues the existing backup chain.

This topic covers the following scenarios:

* [Move a backup stored locally to the Veeam backup repository](#local).
* [Replace the initial Veeam backup repository with another Veeam backup repository](#vbr).

|  |
| --- |
| NOTE |
| Keep in mind that the following users participate in implementation of both scenarios:   * Veeam Agent user performs all actions in the Veeam Agent control panel. * Veeam Backup Administrator performs all actions in the Veeam Backup & Replication console. |

Moving Locally Stored Backup to Veeam Backup Repository

In this scenario, a backup job is targeted at a local folder. The backup job ran at least once.

This scenario can be helpful when you need to back up a large amount of data to the Veeam backup repository but the network connection is slow. In this case, you can create a backup locally and move it to the Veeam backup repository.

To move locally stored backup files to the Veeam backup repository, the Veeam Backup Administrator must perform the following steps:

1. Browse to the folder where Veeam backup repository stores backup files. For example, C:\Backup.

For more information, see the [Configure Backup Repository Settings](https://helpcenter.veeam.com/docs/vbr/userguide/repository_repository.html?ver=13) section in the Veeam Backup & Replication User Guide.

1. In the C:\Backup folder, create a new folder in the following format: C:\Backup\<domain\_name>\_<user\_name>\<folder\_name>, where:

* <domain\_name> — domain name that Veeam Agent uses to connect to the Veeam backup repository.
* <user\_name> — user name that Veeam Agent uses to connect to the Veeam backup repository.
* <folder\_name> — name of the target folder to store backups. You can use the name of the original backup job or specify a new name for the folder.

For example: C:\Backup\TECH\_Administrator\System\_Backup.

1. Using external tools, move all backup files to the folder created at the step 2.
2. Rescan the Veeam backup repository. To learn how to rescan the Veeam backup repository, see the [Rescanning Backup Repositories](https://helpcenter.veeam.com/docs/vbr/userguide/rescanning_backup_repositories.html?ver=13) section in the Veeam Backup & Replication User Guide.

As a result, the moved backup will appear under the Backups > Disk (Imported) node in the inventory pane.

|  |
| --- |
| NOTE |
| If the backup file is encrypted, you must decrypt the backup before proceeding to the next step. To learn more, see the [Decrypting Data with Password](https://helpcenter.veeam.com/docs/vbr/userguide/decrypt_with_pass.html?ver=13) section in the Veeam Backup & Replication User Guide. |

After the Veeam Backup Administrator moved the backup files to the target folder, the Veeam Agent user must perform the following steps:

1. Edit the Veeam Agent backup job:

1. At the Name step of the wizard, make sure that the name of the backup job is the same as the name of the folder you created at the step 2.
2. At the Destination step of the wizard, target the backup job at the Veeam backup repository.
3. At the Backup Server step of the wizard, select a backup repository where you want to store backups and specify settings for the Veeam backup server that manages the target backup repository. For more information, see [Veeam Backup Repository Settings](backup_job_vbr.md).
4. At the Backup Repository step of the wizard, click the Map backup link and select the moved backup file.
5. At the Summary step of the wizard, make sure that the Run the job when I click Finish check box is cleared and click Finish to save changes. As a result, the backup will be moved from the Backups > Disk (Imported) node to the Backups > Disk node in the inventory pane.

1. Run the Veeam Agent backup job. The backup job will continue the backup chain for the full backup that was moved to the Veeam backup repository.

Replacing Initial Veeam Backup Repository with Another Veeam Backup Repository

In this scenario, the backup job is targeted at a Veeam backup repository and you want to replace the initial repository with another Veeam backup repository.

This scenario can be helpful if you want to move backed up data to a repository that has more storage capacity.

To replace the Veeam Backup & Replication repository, the Veeam Backup Administrator must perform the following steps:

1. Delete the existing Veeam Agent backup job from the Veeam Backup & Replication console. For more information, see [Deleting Veeam Agent Backup Jobs](integration_delete.md).

|  |
| --- |
| NOTE |
| Deleting the job from the Veeam Backup & Replication console does not remove the backup job from the Veeam Agent control panel. |

1. Delete configuration database records about backups created by the Veeam Agent backup job. For more information, see [Removing Veeam Agent Backups](integraton_remove_backups.md).
2. Browse to the folder where the target Veeam backup repository stores backup files. For example, C:\Backup.

For more information, see the [Configure Backup Repository Settings](https://helpcenter.veeam.com/docs/vbr/userguide/repository_repository.html?ver=13) section in the Veeam Backup & Replication User Guide.

1. In the C:\Backup folder, create a new folder in the following format: C:\Backup\<domain\_name>\_<user\_name>\<folder\_name>, where:

* <domain\_name> — domain name that Veeam Agent uses to connect to the Veeam backup repository.
* <user\_name> — user name that Veeam Agent uses to connect to the Veeam backup repository.
* <folder\_name> — name of the target folder to store backups. You can use the name of the original backup job or specify a new name for the folder.

For example: C:\Backup\TECH\_Administrator\System Backup

1. Using external tools, move all backup files to the folder created at the step 4.
2. Rescan the Veeam backup repository. To learn more, see the [Rescanning Backup Repositories](https://helpcenter.veeam.com/docs/vbr/userguide/rescanning_backup_repositories.html?ver=13) section in the Veeam Backup & Replication User Guide.

As a result, the moved backup will appear under the Backups > Disk (Imported) node in the inventory pane.

|  |
| --- |
| NOTE |
| If the backup file is encrypted, you must decrypt the backup before proceeding to the next step. To learn more, see the [Decrypting Data with Password](https://helpcenter.veeam.com/docs/vbr/userguide/decrypt_with_pass.html?ver=13) section in the Veeam Backup & Replication User Guide. |

After the Veeam Backup Administrator moved the backup files to the target folder, the Veeam Agent user must perform the following steps:

1. Edit the Veeam Agent backup job:

1. At the Name step of the wizard, make sure that the name of the backup job is the same as the name of the folder you created at the step 4.
2. At the Backup Server step of the wizard, select a new backup repository and specify settings for the Veeam backup server that manages the target backup repository. For more information, see [Veeam Backup Repository Settings](backup_job_vbr.md).
3. At the Backup Repository step of the wizard, click the Map backup link and select the moved backup file.
4. At the Summary step of the wizard, make sure that the Run the job when I click Finish check box is cleared and click Finish to save changes. As a result, the backup will be moved from the Backups > Disk (Imported) node to the Backups > Disk node in the inventory pane.

1. Run the Veeam Agent backup job.


