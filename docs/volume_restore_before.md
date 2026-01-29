---
title: "Before You Begin"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/volume_restore_before.html"
last_updated: "10/28/2025"
product_version: "13.0.1.1009"
---

# Before You Begin


Before you begin the volume-level restore process, check the following prerequisites and limitations.

General

* The volume-level backup from which you plan to restore data must be successfully created at least once.
* [For backups stored in network shared folders and on backup repositories] You must have access to the target location where the backup file resides.

* [For backup repository targets] If you plan to restore data from a backup stored in a backup repository, you must have access permissions on this backup repository. To learn more, see [Setting Up User Permissions on Backup Repositories](integrate_permissions.md).

* A user account under which you start the restore operation must have administrative privileges on the Veeam Agent computer. If the account under which you are currently logged on to Microsoft Windows does not have administrative privileges, you will be prompted to enter administrator credentials.

ReFS Restore

If you restore a ReFS volume from a backup that was made on another machine, the Veeam Agent computer where you perform restore must run the OS that supports the specific ReFS version. For example, you can restore a ReFS 3.x volume only to a computer that runs one of the following OSes:

* Microsoft Windows 10 version 22H2
* Microsoft Windows Server 2016 or later

NTFS Restore

* If you restore an NTFS volume from a backup that was made on another machine, and data deduplication was enabled for the volume, the Veeam Agent computer where you perform restore must run the same OS version or later as the backed-up machine OS.
* If you restore an NTFS volume from a backup that was made on another machine, and the allocation unit size of the volume was set to 128K or greater, the Veeam Agent computer where you perform restore must run one of the following OSes:

+ Microsoft Windows 10 version 22H2
+ Microsoft Windows Server 2019 or later

Volume-Level Restore Limitations

Volume-level restore has the following limitations:

* You cannot restore the system volume to its original location.
* You cannot restore a volume to the volume on which the Microsoft Windows swap file is hosted.
* You cannot restore a volume to the volume where the backup file that you use for restore is located.

To overcome the first two limitations, you can boot from the recovery image and use the Volume Level Restore wizard for volume-level restore. To learn more, see [Restoring from Veeam Recovery Media](image_boot.md).


