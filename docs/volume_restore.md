---
title: "Restoring Volumes"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/volume_restore.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Restoring Volumes


You can restore a specific computer volume or all volumes from the volume-level backup.

Volumes can be restored to their original location or to a new location.

* If you restore a volume to its original location, Veeam Agent for Microsoft Windows will overwrite the data on the original volume with the data restored from the backup.
* If you restore volume data to a new location, Veeam Agent for Microsoft Windows will restore data from the backup and write it to the selected destination. If necessary, you can specify new disk mapping settings for the restored volume.

Before you perform volume-level restore, [check prerequisites](volume_restore_before.md). Then use the Volume Level Restore wizard to restore the necessary volumes.

1. [Launch the Volume Level Restore wizard](volume_restore_launch.md).
2. [Specify the backup file location](volume_restore_source.md).
3. [Select the remote storage type](volume_restore_remote.md).
4. [Specify remote storage settings](volume_restore_remote_conf.md).
5. [Select a backup](volume_restore_backup.md).
6. [Select a restore point](volume_restore_point.md).
7. [Map restored disks](volume_restore_disk_mapping.md).
8. [Resize restored volumes](volume_restore_resize.md).
9. [Complete the restore process](volume_restore_complete.md).

Related Topics

[Volume-Level Restore](restore_volume.md)


