---
title: "Volume-Level Restore"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/restore_volume.html"
last_updated: "9/1/2023"
product_version: "13.0.1.1009"
---

# Volume-Level Restore


If data on a computer volume gets corrupted, you can restore this volume from the backup. For volume-level restore, you can use backups that were created at the volume level. File-level backups cannot be used for volume restore.

When you perform volume-level restore, Veeam Agent for Microsoft Windows restores the entire content of the volume. It retrieves from the backup data blocks pertaining to a specific volume and copies them to the necessary location.

Keep in mind that you cannot browse the volume in the backup and select individual application items, files and folders for restore. For granular file-level restore, you can use the file-level restore option. To learn more, see [File-Level Restore](restore_file.md).

A volume can be restored to its original location or new location. If you restore the volume to its original location, Veeam Agent for Microsoft Windows overwrites data on the original volume. If you restore the volume to a new location, and the target disk contains any data, Veeam Agent for Microsoft Windows overwrites data in the target location with data retrieved from the backup.

A volume can be restored to a new location that has greater or less space than the size of the volume in the backup. Depending on the amount of free disk space on target location, you can select either to shrink or to extend the volume during restore. To learn more, see [Volume Resize](data_restore_with_volume_resize.md).

Limitations for Volume-Level Restore

Volume restore has the following limitations:

* You cannot restore the system volume to its original location.
* You cannot restore a volume to the volume on which the swap file is currently hosted.
* You cannot restore a volume to the volume where the backup file used for restore is located.

To overcome the first two limitations, you can create a Veeam Recovery Media and use the Veeam Bare Metal Recovery wizard for volume-level restore. To learn more, see [Veeam Recovery Media](recovery_media.md).

Related Tasks

* [Restoring from Veeam Recovery Media](image_boot.md)
* [How to Perform Bare Metal Recovery](howto_baremetal_recovery.md)
* [Restoring Volumes](volume_restore.md)
* [How to Restore Computer Volume](howto_restore_volume.md)


