---
title: "Using with Veeam Backup & Replication"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/integrate.html"
last_updated: "12/1/2025"
product_version: "13.0.1.1009"
---

# Using with Veeam Backup & Replication


If you have the Veeam backup infrastructure deployed in the production environment, you can use Veeam Agent together with Veeam Backup & Replication.

|  |
| --- |
| IMPORTANT |
| If you plan to use Veeam Agent for Microsoft Windows  13.0.1 with Veeam Backup & Replication, you must install Veeam Backup & Replication 13.0.1. |

|  |
| --- |
| NOTE |
| This and subsequent sections describe tasks with Veeam Backup & Replication available for Veeam Agent operating in the standalone mode. For information about tasks available in Veeam Backup & Replication within the Veeam Agent management scenario, see the [Veeam Agent Backup](https://helpcenter.veeam.com/docs/vbr/userguide/protect_comp.html?ver=13) section in the Veeam Backup & Replication User Guide. |

Tasks with Veeam Backup & Replication

Veeam Backup & Replication lets you perform a number of additional data protection and disaster recovery tasks, as well as administrative actions with Veeam Agent backups. You can:

* [Grant access permissions on backup repositories](integrate_permissions.md).
* [Manage Veeam Agent licenses](license_vbr.md).

Data protection tasks

* [Create Veeam Agent backups on backup repositories](integration_backup_repository.md).
* [Create Veeam Agent backups on Veeam Cloud Connect repositories](integration_backup_cloud.md).
* [Copy Veeam Agent backups to secondary backup repositories](integration_backup_copy.md).
* [Archive Veeam Agent backups to tape](integration_tape.md).

Restore tasks

* [Restore Veeam Agent backups to Hyper-V VMs](integration_instant_restore_hyperv.md).
* [Restore Veeam Agent backups to VMware vSphere VMs](integration_instant_restore_vsphere.md).
* [Restore Veeam Agent backups to Nutanix VMs](integration_instant_restore_nutanix.md).

* [Restore volumes from Veeam Agent backups](integration_volume_restore.md).

* [Restore files and folders from Veeam Agent backups](integration_flr.md).

* [Restore application items from Veeam Agent backups](integration_explorers.md).

* [Restore disks from Veeam Agent backups](integration_disk_restore.md).
* [Publish disks to analyze backup content](integration_publish.md).

* [Restore data from Veeam Agent backups to Amazon EC2](integration_restore_to_amazon.md).

* [Restore data from Veeam Agent backups to Microsoft Azure](integration_restore_to_azure.md).
* [Restore data from Veeam Agent backups to Google Compute Engine](integration_restore_to_google.md).

* [Export restore points of Veeam Agent backups to standalone full backup files](agent_export_backup.md).

Administrative tasks

* [Import Veeam Agent backups](integration_import.md).
* [Enable and disable Veeam Agent backup jobs](integration_disable.md).
* [View Veeam Agent backup job statistics](integration_statistics.md).
* [Delete Veeam Agent backup jobs](integration_delete.md).
* [View Veeam Agent backup properties](integration_properties.md).
* [Create recovery tokens](integration_recovery_token.md).
* [Copy Veeam Agent backups](integration_copy.md).
* [Remove Veeam Agent backups](integraton_remove_backups.md).
* [Delete Veeam Agent backups](integration_delete_from_disk.md).

* [Configure global settings](integration_settings.md).

* [Assign roles to users](integration_user_roles.md).

Related Topic

[Integration with Veeam Backup & Replication](vbr_integration.md)


