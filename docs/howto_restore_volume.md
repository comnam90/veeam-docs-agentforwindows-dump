---
title: "How to Restore Computer Volume"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/howto_restore_volume.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# How to Restore Computer Volume


If a computer volume gets corrupted, you can restore it from the backup. The volume can be restored to its original location or to a new location. Note that you can restore volumes only from volume-level backups. You cannot restore volumes from file-level backups.

This scenario describes how to restore a volume from the backup available on a shared network folder to its original location.

1. Right-click the Veeam Agent for Microsoft Windows icon in the system tray and select Restore > Entire volumes.

![How to Restore Computer Volume](images/ep_volume_restore_launch.webp "Start Volume Restore Using System Tray")

1. At the Backup Location step of the wizard, select Network storage. Click Next.

![How to Restore Computer Volume](images/howto_restore_volume_storage.webp "Specify Backup Location")

1. At the Network Storage step of the wizard, select Shared folder. Click Next.

![How to Restore Computer Volume](images/ep_volume_restore_network_storage.webp "Specify Network Storage Type")

1. At the Shared Folder step of the wizard, specify settings of the shared folder where the backup is located. Click Next.

![How to Restore Computer Volume](images/ep_volume_restore_share.webp "Specify Shared Folder Details")

1. At the Backup step of the wizard, select the necessary backup in the shared folder. Click Next.

![How to Restore Computer Volume](images/ep_volume_restore_backups.webp "Select Backup to Restore from")

1. At the Restore Point step of the wizard, select a restore point from which you want to restore data. Click Next.

![How to Restore Computer Volume](images/ep_volume_restore_point.webp "Select Restore Point")

1. Select the volume that you want to restore. Consider the following:

+ You cannot restore the system volume to its original location.
+ You cannot restore a volume to the volume on which the Microsoft Windows swap file is hosted.
+ You cannot restore a volume to the volume where the backup file that you use for restore is located.

To overcome these limitations, you can perform [bare metal recovery](howto_baremetal_recovery.md).

![How to Restore Computer Volume](images/howto_volume_disk.webp "Select Volume to Restore")

1. Click Next, then click Restore.
2. Once restore is completed, click Finish to close the wizard.


