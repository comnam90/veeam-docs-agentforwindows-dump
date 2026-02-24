---
title: "Backing Up to Cloud Repositories"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/integration_backup_cloud.html"
last_updated: "2/24/2026"
product_version: "13.0.1.1009"
---

# Backing Up to Cloud Repositories


You can store backups created with Veeam Agent in cloud repositories provided to you by a Veeam Cloud Connect service provider. To do this, you must connect to the service provider and point the backup job to the cloud repository. To learn more, see [Specify Service Provider Settings](backup_job_sp_settings.md).

Veeam Agent Backups on Tenant Side

Backups created with Veeam Agent are available under the Cloud node in the Home view of the Veeam Backup & Replication console deployed on the tenant side.

The backup administrator working with Veeam Backup & Replication on the tenant side can manage Veeam Agent backups created in the cloud repository and restore data from such backups. To recover data from a Veeam Agent backup, you can perform the following operations:

* [Export computer disks as virtual disks](integration_disk_restore.md).
* [Restore guest OS files](integration_flr.md).
* [Export restore points to standalone full backup files](agent_export_backup.md).

Veeam Agent Backups on Service Provider Side

The service provider can view information about backup and restore sessions performed by Veeam Agent users. The full list of sessions is available in the History view of the Veeam backup console deployed on the service provider side. The list of sessions performed within the last 24 hours is available under the Last 24 hours node in the Cloud Connect view of the Veeam backup console on the service provider side. The service provider cannot view detailed statistics about individual sessions in the list.

The service provider cannot perform restore tasks with Veeam Agent backups that are stored in the cloud repository.The service provider can perform the following restore tasks with unencrypted Veeam Agent backups stored in the cloud repository:

* Instant recovery
* Restore to public cloud repositories
* Disk restore
* Disk publish

To learn more, see the [Restoring Data from Tenant Backups](https://helpcenter.veeam.com/docs/vbr/cloud/cc_data_restore.html?ver=13) section in the Veeam Cloud Connect Guide.


