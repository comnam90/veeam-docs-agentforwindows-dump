---
title: "Exporting Disks"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/integration_disk_restore.html"
last_updated: "11/19/2025"
product_version: "13.0.1.1009"
---

# Exporting Disks


You can restore computer disks from Veeam Agent backups created using Veeam Agent for Microsoft Windows and convert them to disks of the VMDK, VHD or VHDX format.

During disks restore, Veeam Backup & Replication creates standard virtual disks that can be used by VMware vSphere and Microsoft Hyper-V VMs.

* When you restore a disk in the VMDK format, Veeam Backup & Replication creates a pair of files that make up the VM virtual disk: a descriptor file and file with the virtual disk content.
* When you restore a disk in the VHD/VHDX format, Veeam Backup & Replication creates a file of the VHD or VHDX format.

You can save converted disks locally on any server or SMB share added to the backup infrastructure or place disks on a datastore connected to an ESXi host (for VMDK disk format only). VMDK disks can be restored as thin provision and thick disks:

* Disks restored to a datastore are saved in the thin provisioned format.
* Disks restored to a server are saved in the thick provisioned format.

Veeam Backup & Replication supports batch disk restore. For example, if you choose to restore 2 computer disks, Veeam Backup & Replication will convert them to 2 virtual disks and store these disks in the specified location.To restore disks and convert them to the VMDK, VHD or VHDX format, perform the following steps in the Export Disk wizard:

1. [Launch the Export Disk wizard](integration_disk_restore_launch.md).
2. [Select a backup](integration_disk_restore_backup.md).
3. [Select a restore point](integration_disk_restore_point.md).
4. [Select disks](integration_disk_restore_disks.md).
5. [Select the destination and disk format](integration_disk_restore_format.md).
6. [Specify secure restore settings](integration_disk_restore_secure.md).
7. [Specify restore reason](integration_disk_restore_reason.md).
8. [Complete restore process](integration_disk_restore_complete.md).


