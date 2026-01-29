---
title: "Backup of External Drives"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_usb.html"
last_updated: "9/1/2023"
product_version: "13.0.1.1009"
---

# Backup of External Drives


You can use Veeam Agent for Microsoft Windows to back up data that resides on external USB/eSATA or FireWire drives connected to the Veeam Agent computer.

|  |
| --- |
| ![Backup of External Drives](images/icon_important.webp) IMPORTANT |
| Veeam Agent supports backup of external drives that support Microsoft VSS: HDD, SSD, and so on. USB flash drives (USB sticks) are not supported, because it is impossible to create a VSS snapshot on a device of this type. To learn how to check if your drive is supported, see [this Veeam KB article](https://www.veeam.com/kb3009). |

You can include an external drive in any type of backup: entire computer backup, volume-level backup or file-level backup.

* For entire computer backup, you can instruct Veeam Agent for Microsoft Windows to back up data of all external drives the are currently connected to the Veeam Agent computer. To do this, you must enable the Include external USB drives option at the Backup Mode step of the New Backup Job wizard.

An external drive whose data you want to back up must be connected to the Veeam Agent computer at the time when the backup job must start.

If an external drive that was backed up within a previous backup job session is not connected to the Veeam Agent computer when the backup job must start, Veeam Agent for Microsoft Windows will back up data of all existing drives and skip the absent one. The backup job session will complete successfully.

* For volume-level backup, you can include in the backup a specific volume that resides on an external drive. To do this, you must select the necessary volume at the Volumes step of the New Backup Job wizard.

If a USB drive that contains the volume included in the backup is not connected to the Veeam Agent computer when the backup job must start, the backup job will complete with an error.

* For file-level backup, you can include in the backup data of a specific volume that resides on an external drive (entire volume or specific folders with files). To do this, you must select the necessary object at the Files step of the New Backup Job wizard.

If a USB drive that contains a volume or folder included in the backup is not connected to the Veeam Agent computer when the backup job must start, the backup job will complete with an error.

|  |
| --- |
| NOTE |
| Veeam Agent for Microsoft Windows does not back up external drives used as rotated drives. USB drives registered as a known removable storage in Veeam Agent for Microsoft Windows are excluded from the backup. |

Related Topics

[Backup Types](backup_types.md)

Related Tasks

[Creating Backup Jobs](backup_job_create.md)


