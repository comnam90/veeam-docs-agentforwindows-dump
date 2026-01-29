---
title: "Long-Term Retention Policy (GFS)"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/gfs_retention.html"
last_updated: "10/23/2023"
product_version: "13.0.1.1009"
---

# Long-Term Retention Policy (GFS)


The long-term or Grandfather-Father-Son (GFS) retention policy allows you to store backup files for long periods of time — for weeks, months and even years. For this purpose, Veeam Agent does not create any special new backup files — it uses backup files created while backup job runs and marks these backups with specific GFS flags.

To mark a backup file for long-term retention, Veeam Agent can assign to the file the following types of GFS flags: weekly (W), monthly (M) and yearly (Y). The types of GFS flags that Veeam Agent assigns depend on the configured [GFS retention policy settings](backup_job_gfs_settings.md).

|  |
| --- |
| NOTE |
| Consider the following:   * GFS flags can be assigned only to full backup files created during the time period specified in GFS policy settings. * If you store your backups in object storage, and you do not configure Veeam Agent to perform active full backups periodically, Veeam Agent will create a full backup based on the last incremental backup and will assign a GFS flag to this full backup. If some data blocks required to create the full backup already reside in the object storage repository, the full backup will contain links to such data blocks. To avoid extra costs, Veeam Agent does not retrieve actual data blocks from the object storage repository. |

If Veeam Agent assigns a GFS flag to a full backup file, this backup file can no longer be deleted or modified. Veeam Agent does not apply short-term retention policy settings to the full backup file. For example, Veeam Agent ignores the backup file when determining whether the number of allowed backup files is exceeded.

When the specified retention period ends, Veeam Agent unassigns the GFS flag from the full backup file. If the backup file does not have any other GFS flags assigned, it can be modified and deleted according to the short-term retention policy.

Veeam Agent assigns GFS flags in the similar way as Veeam Backup & Replication does for VM backup files. To learn about logic behind GFS flags, see the [Assignment of GFS Flags](https://helpcenter.veeam.com/docs/vbr/userguide/gfs_how_flags_assigned.html?ver=13) and [Removal of GFS Flags](https://helpcenter.veeam.com/docs/vbr/userguide/gfs_flags_removal.html?ver=13) sections in the Veeam Backup & Replication User Guide.

Limitations

When planning to use GFS retention policy, consider the following limitations:

* [Applicable to all backup targets except object storage] While applying the GFS retention policy, Veeam Agent does not create new full backup files. You must configure your backup jobs in a way you do not lose any essential data due to an insufficient number of full backup files. For example, if you configure monthly GFS retention, you need at least one full backup file per month.
* If a GFS flag is assigned to a full backup file in an active backup chain, the following applies:

* Veeam Agent cannot transform the backup chain according to the short-term retention policy.
* Veeam Agent is not able to merge data from incremental backup files into the full backup file.

* Veeam Agent assigns GFS flags only after you save GFS retention policy settings. This means that GFS flags are assigned only to those backup files created after the configuration, while backup files created earlier are not affected and previously assigned flags are not modified.

* You cannot store full backups to which GFS flags are assigned in backup repositories with rotated drives.
* Retention policy for deleted items does not apply to full backup files to which GFS flags are assigned.

Related Topics

[Specify GFS Retention Policy](backup_job_gfs_settings.md)


