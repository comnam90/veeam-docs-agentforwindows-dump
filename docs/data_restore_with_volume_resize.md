---
title: "Volume Resize"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/data_restore_with_volume_resize.html"
last_updated: "9/1/2023"
product_version: "13.0.1.1009"
---

# Volume Resize


With Veeam Agent for Microsoft Windows, you can resize backup volumes during [volume-level restore](restore_volume.md). When you select to resize a volume, Veeam Agent for Microsoft Windows restores data from the backup and resizes the restored volume to the specified size.

There are two ways to resize a volume depending on the amount of free disk space on the target location:

* Volume shrink — you can shrink a volume when you restore it to a new location that has less space than the size of the volume in the backup. You can also shrink a volume that is restored to its original location to free disk space on the target location. To learn more, see [How Volume Shrink Works](shrink_hiw.md).

* Volume extend — you can extend a backup volume when you restore it to a new location that has more available disk space than the size of the backup volume. To learn more, see [How Volume Extend Works](extend_hiw.md).

Volume resize may be also helpful when you need to restore data after hardware upgrade. For example, you may want to resize volumes in the following situations:

* Shrink backup data to restore system volumes of your computer to a smaller disk after you replace an old HDD drive with a faster but less capacitive SSD drive.
* Extend the backup volume during volume-level restore to a new, more capacitive HDD drive.

You can restore and resize volumes:

* With the Volume Restore wizard when you restore volumes under Microsoft Windows system. For more information, see [Restoring Volumes](volume_restore.md).
* With the Veeam Bare Metal Recovery wizard when you perform restore from the Veeam Recovery Media. For more information, see [Restoring from Veeam Recovery Media](image_boot.md).

The volume resize option is available only in the Manual restore mode at the Disk Mapping step of the wizard.

Limitations for volume resize

Volume resize has the following limitations:

* You cannot restore a volume to the volume of the smaller size if the amount of data stored on the backup volume exceeds the free space on the target disk.

* You can only resize basic volumes that use the NTFS file system.
* If you resize a BitLocker encrypted volume during restore, the restored volume will be unencrypted.

Related Tasks

* [Restoring from Veeam Recovery Media](image_boot.md)
* [Restoring Volumes](volume_restore.md)


