---
title: "Moving Veeam Agent Backups to Veeam Cloud Connect Repository"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/appendix_move_backups_to_vcc.html"
last_updated: "1/9/2026"
product_version: "13.0.1.1009"
---

# Moving Veeam Agent Backups to Veeam Cloud Connect Repository


This topic describes how to place existing Veeam Agent backups in a cloud repository in the Veeam Cloud Connect infrastructure so that the Veeam Agent backup job continues the existing backup chain. For more information about Veeam Cloud Connect, see the [Veeam Cloud Connect Guide](https://helpcenter.veeam.com/docs/vbr/cloud/cloud_overview.html?ver=13).

The scenarios described in this section can be helpful when you need to back up a large amount of data to the Veeam Cloud Connect repository but the network connection is slow. In this case, you can create a backup locally and move it to the Veeam Cloud Connect repository.

This topic covers the following scenarios:

* [Move a backup to a backup repository used as a cloud repository](#simple)
* [Move a backup to a scale-out backup repository used as a cloud repository](#sobr)

|  |
| --- |
| NOTE |
| Keep in mind that the following users participate in implementation of both scenarios:   * Service provider moves backup files to the target repository.  * Veeam Backup Administrator rescans the target repository in the Veeam Backup & Replication console.  * Veeam Agent user performs actions in the Veeam Agent control panel. |

Moving Backup to Backup Repository

Use this scenario if you want to move a locally stored backup to a backup repository used as a cloud repository. For information about backup repositories, see the [Backup Repositories](https://helpcenter.veeam.com/docs/vbr/userguide/backup_repository.html?ver=13) section in the Veeam Backup & Replication User Guide.

To move locally stored backup files to the cloud repository, the service provider must perform the following steps:

1. Browse to the folder where the cloud repository stores backup files. For example, C:\Backup.

For more information, see the [Configure Backup Repository Settings](https://helpcenter.veeam.com/docs/vbr/userguide/repository_repository.html?ver=13) section in the Veeam Backup & Replication User Guide.

1. In the C:\Backup folder, create a new folder in the following format:

* [If you work with tenant accounts] C:\Backup\<tenant\_name>\<folder\_name>
* [If you work with subtenant accounts] C:\Backup\<tenant\_name>\Users\<subtenant\_name>\<folder\_name>,

where:

* <tenant\_name> — name of the tenant account that you use to connect to the service provider. For more information, see the [Tenant Account Credentials](https://helpcenter.veeam.com/docs/vbr/cloud/cloud_tenant_creds.html?ver=13) section in the Veeam Cloud Connect Guide.
* <subtenant\_name> — name of the subtenant account that you use to connect to the service provider. For more information, see the [Managing Subtenant Accounts on SP Side](https://helpcenter.veeam.com/docs/vbr/cloud/cloud_connect_subtenants_manage.html?ver=13) section in the Veeam Cloud Connect Guide.
* <folder\_name> — name of the target folder to store backups. You can use the name of the original backup job or specify a new name for the folder.

For example, C:\Backup\ABC\_Company\System\_Backup or C:\Backup\ABC\_Company\Users\John\_Smith\System\_Backup.

1. Using external tools, move all backup files to the folder created at the step 2.

After the service provider moved the backup files to the backup folder, the Veeam Backup Administrator must rescan the cloud repository. To learn how to rescan a repository, see the [Rescanning Backup Repositories](https://helpcenter.veeam.com/docs/vbr/userguide/rescanning_backup_repositories.html?ver=13) section in the Veeam Backup & Replication User Guide.

The information about the added backup will be displayed in the rescan job session window.

After the Veeam Backup Administrator rescanned the backup repository, the Veeam Agent user must perform the following steps:

1. Edit the Veeam Agent backup job:

1. At the Destination step of the wizard, target the backup job at the Veeam Cloud Connect Repository.
2. At the Service Provider step of the wizard, specify settings for the cloud gateway to connect to the service provider. For more information, see [Specifying Service Provider Settings](backup_job_sp_settings.md#sp).
3. At the Credentials step of the wizard, specify settings for the tenant or subtenant account that you want to use to connect to the service provider. For more information, see [Specifying User Account Settings](backup_job_sp_settings.md#tenant).
4. At the Backup Resources step of the wizard, click the Map backup link and select the moved backup.
5. At the Summary step of the wizard, click Finish to save changes.

1. Run the Veeam Agent backup job. The backup job will continue the backup chain for the full backup that was moved to the cloud repository.

Moving Backup to Scale-Out Backup Repository

Use this scenario if you want to move a locally stored backup to a scale-out backup repository used as a cloud repository. For information about scale-out backup repositories, see the [Scale-Out Backup Repositories](https://helpcenter.veeam.com/docs/vbr/userguide/backup_repository_sobr.html?ver=13) section in the Veeam Backup & Replication User Guide.

|  |
| --- |
| IMPORTANT |
| Before you perform the move, make sure that the backup job name, the target backup folder name, the names of VBM files and paths to VBM files meet the following requirements:   * The names contain only allowed alphanumeric characters: a-z, A-Z, 0-9. * The names contain only allowed special characters: \_ - . + = @ ^. * The names of VBM files and paths to VBM files do not contain spaces. If the names or the paths contain spaces, replace them with underscores. |

To move locally stored backup files to the cloud repository, the service provider must perform the following steps:

1. Browse to the folder where the cloud repository stores backup files. For example, C:\Backup.

For more information, see the [Configure Backup Repository Settings](https://helpcenter.veeam.com/docs/vbr/userguide/repository_repository.html?ver=13) section in the Veeam Backup & Replication User Guide.

1. In the C:\Backup folder, create new folders for each extent of the scale-out backup repository. The folders must be in the following format:

* [If you work with tenant accounts] C:\Backup\<extent\_name>\<tenant\_name>\<folder\_name>
* [If you work with subtenant accounts] C:\Backup\<extent\_name>\<tenant\_name>\Users\<subtenant\_name>\<folder\_name>,

where:

* <extent\_name> — name of the backup repository you use as an extent. For more information, see the [Add Performance Extents](https://helpcenter.veeam.com/docs/vbr/userguide/sobr_add_extents.html?ver=13) section in the Veeam Backup & Replication User Guide.
* <tenant\_name> — name of the tenant account that you use to connect to the service provider. For more information, see the [Tenant Account Credentials](https://helpcenter.veeam.com/docs/vbr/cloud/cloud_tenant_creds.html?ver=13) section in the Veeam Cloud Connect Guide.
* <subtenant\_name> — name of the subtenant account that you use to connect to the service provider. For more information, see the [Managing Subtenant Accounts on SP Side](https://helpcenter.veeam.com/docs/vbr/cloud/cloud_connect_subtenants_manage.html?ver=13) section in the Veeam Cloud Connect Guide.
* <folder\_name> — name of the target folder to store backups. You can use the name of the original backup job or specify a new name for the folder.

For example, C:\Backup\Extent\_1\ABC\_Company\System\_Backup or C:\Backup\Extent\_1\ABC\_Company\Users\John\_Smith\System\_Backup.

1. Using external tools, copy the VBM file to both folders created at the step 2.
2. Using external tools, copy the VBK and VIB files to the folders created at the step 2 according to the placement policy specified for the backup repository. For more information, see the [Backup File Placement for Performance Tier](https://helpcenter.veeam.com/docs/vbr/userguide/backup_repository_sobr_placement.html?ver=13) section in the Veeam Backup & Replication User Guide.

After the service provider moved the backup files to the backup folder, the Veeam Backup Administrator must rescan the cloud repository. To learn how to rescan the repository, see the [Rescanning Backup Repositories](https://helpcenter.veeam.com/docs/vbr/userguide/rescanning_backup_repositories.html?ver=13) section in the Veeam Backup & Replication User Guide.

The information about the added backup will be displayed in the rescan job session window.

After the Veeam Backup Administrator rescanned the backup repository, the Veeam Agent user must perform the following steps:

1. Edit the Veeam Agent backup job:

1. At the Destination step of the wizard, target the backup job at the Veeam Cloud Connect Repository.
2. At the Service Provider step of the wizard, specify settings for the cloud gateway to connect to the service provider. For more information, see [Specifying Service Provider Settings](backup_job_sp_settings.md#sp).
3. At the Credentials step of the wizard, specify settings for the tenant or subtenant account that you want to use to connect to the service provider. For more information, see [Specifying User Account Settings](backup_job_sp_settings.md#tenant).
4. At the Backup Resources step of the wizard, click the Map backup link and select the moved backup.
5. At the Summary step of the wizard, click Finish to save changes.

1. Run the Veeam Agent backup job. The backup job will continue the backup chain for the full backup that was moved to the cloud repository.


