---
title: "Step 2. Specify Backup File Location"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/volume_restore_source.html"
last_updated: "11/14/2025"
product_version: "13.0.1.1009"
---

# Step 2. Specify Backup File Location


At the Backup Location step of the wizard, specify where the backup file that you plan to use for restore resides.

If you configured only one backup job, Veeam Agent automatically locates the latest backup of this backup job on the target storage, and you pass immediately to the [Restore Point](volume_restore_point.md) step of the wizard. If there are several backup jobs configured or Veeam Agent fails to locate the backup for some reason, specify where the backup file resides:

* Local storage — select this option if the backup file resides on the computer drive, external drive or removable storage device that is currently connected to your computer. Click Browse and select a backup metadata file (VBM).
* Network storage — select this option if the backup file resides in object storage, in a network shared folder, in a backup repository managed by a Veeam backup server or in a cloud repository exposed to you by a Veeam Cloud Connect service provider. In this case, the Volume Level Restore wizard will include additional steps for specifying file location settings.

![Step 2. Specify Backup File Location](images/ep_volume_restore_source.webp "Specify Backup Location")


