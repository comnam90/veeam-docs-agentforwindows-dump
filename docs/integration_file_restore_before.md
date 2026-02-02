---
title: "Before You Begin"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/integration_file_restore_before.html"
last_updated: "1/30/2026"
product_version: "13.0.1.1009"
---

# Before You Begin


Before you begin the file-level restore process, check the following requirements and limitations:

Requirements

Consider the following general requirements:

* You can restore files from the file systems listed in the [Guest OS File Restore](https://helpcenter.veeam.com/docs/vbr/userguide/platform_support.html?ver=13#flr) section in the Veeam Backup & Replication User Guide.
* The account that you use to start the Veeam Backup & Replication console and to connect to the backup server must have permissions and privileges described in the [Installing and Using Veeam Backup & Replication](https://helpcenter.veeam.com/docs/vbr/userguide/required_permissions.html?ver=13#rpvbr) section in the Veeam Backup & Replication User Guide.
* You can restore files from a backup that has at least one successfully created restore point.
* To use full functionality of guest file restore from Veeam Agent for Microsoft Windows backups, you must configure a Windows-based mount server in your backup infrastructure. For more information, see the  [Mount Servers](https://helpcenter.veeam.com/docs/vbr/userguide/mount_server.html?ver=13) section in the Veeam Backup & Replication User Guide..
* [For [restore to original location](integration_file_restore_complete_original.md)] The mount server must have access to the Veeam Agent computer.
* [For [restore changes functionality](integration_file_restore_complete_changed.md)] This functionality is included in the Veeam Universal License. When using a legacy socket-based license, the Enterprise or Enterprise Plus editions of Veeam Backup & Replication are required.

Requirements for ReFS

|  |
| --- |
| NOTE |
| The information in this subsection is only applicable to restore from volume-level backups. |

If you plan to restore files from a computer running Microsoft Windows ReFS, consider the following requirements for the Veeam Backup & Replication components involved in the restore process:

* The machine on which a mount point is created (for example, the mount server) must run Microsoft Windows Server 2012 R2 OS or later.
* [For ReFS 3.x] If you plan to restore files from a computer running Microsoft Windows ReFS 3.x, the machine on which mount point is created must run Microsoft Windows Server 2016 OS or later and the ReFS version must be supported on it.
* The machine on which a mount point is created must run Microsoft Windows Server OS of the same version or newer than the Veeam Agent computer from which you plan to restore files.

To learn more about mount points creation, see the [Mount Points and Restore Scenarios](https://helpcenter.veeam.com/docs/vbr/userguide/guest_restore_scenarios.html?ver=13) section in the Veeam Backup & Replication User Guide.

Requirements for Data Deduplication

|  |
| --- |
| NOTE |
| The information in this subsection is only applicable to restore from volume-level backups. |

If you plan to restore files from a computer running Microsoft Windows Server 2012 R2 OS or later and data deduplication is enabled for some volumes, consider the following for the Veeam Backup & Replication components involved in the restore process:

* The machine on which a mount point is created (for example, the mount server) must run Microsoft Windows Server 2012 R2 OS or later.
* The machine on which a mount point is created must run Microsoft Windows Server OS of the same version or newer than the Veeam Agent computer from which you plan to restore files.
* Data deduplication must be enabled on the machine on which a mount point is created.

To learn in which scenarios on which machines mount points can be created, see the [Mount Points and Restore Scenarios](https://helpcenter.veeam.com/docs/vbr/userguide/guest_restore_scenarios.html?ver=13) section in the Veeam Backup & Replication User Guide.

Limitations

Consider the following limitations:

* You cannot restore pipes and other file system objects. File-level restore supports recovery of files and folders only.
* You can restore files from basic disks and dynamic disks (including simple, mirrored and striped volumes).

* [For restore from volume-level backups] Processing of reparse points is supported only for NTFS. Note that reparse points with reparse tag values other than IO\_REPARSE\_TAG\_MOUNT\_POINT, IO\_REPARSE\_TAG\_SYMLINK and IO\_REPARSE\_TAG\_DEDUP may be processed and restored incorrectly.
* The comparison functionality uses Veeam Deployer Service. This service is a 32-bit service. During the comparison, the service converts some 64-bit objects in 32-bit objects. That is why such objects are shown as deleted in the Veeam Backup browser, for example, some objects in the Windows folder.
* [For [permission restore](integration_file_restore_complete_permissions.md)] Veeam Backup & Replication restores only permissions. Attributes such as Read-only, Encrypted and so on are not restored.

* [For [permission restore](integration_file_restore_complete_permissions.md)] Permissions can be restored only for files and folders that are still present on the Veeam Agent computer. If files and folders are missing, restore fails.

* You cannot restore files encrypted with Windows EFS.


