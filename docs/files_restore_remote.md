---
title: "Step 3. Select Remote Storage Type"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/files_restore_remote.html"
last_updated: "3/25/2026"
product_version: "13.0.2.1102"
---

# Step 3. Select Remote Storage Type


The Remote Storage step of the wizard is available if you have chosen to restore data from a backup file that resides in a remote location — in object storage, in a network shared folder, in a backup repository or in a cloud repository.

Specify where the backup file resides:

* Object storage — select this option if the backup file is located in object storage. With this option selected, you will pass to the [Object Storage](files_restore_object_storage.md) step of the wizard.

|  |
| --- |
| NOTE |
| Select this option only if the backup was saved to object storage directly. If the object storage is added as a Veeam backup repository or Veeam Cloud Connect repository, select the corresponding option instead.  To learn more about available object storage configurations, see [Backup to Object Storage](backup_to_object_storage.md). |

* Shared folder — select this option if the backup file is located in a network shared folder. With this option selected, you will pass to the [Shared Folder](files_restore_share.md) step of the wizard.
* Veeam backup repository — select this option if the backup file resides in a backup repository managed by the Veeam backup server. With this option selected, you will pass to the [Backup Server](files_restore_vbr.md) step of the wizard.
* Veeam Cloud Connect repository — select this option if the backup file resides in a cloud repository exposed to you by a Veeam Cloud Connect service provider. With this option selected, you will pass to the [Service Provider](files_restore_sp.md) step of the wizard.


