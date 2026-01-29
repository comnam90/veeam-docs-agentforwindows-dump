---
title: "Veeam Changed Block Tracking Driver"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_cbt_driver.html"
last_updated: "11/10/2025"
product_version: "13.0.1.1009"
---

# Veeam Changed Block Tracking Driver


You can set up Veeam Agent for Microsoft Windows to use the Veeam CBT driver instead of the default CBT mechanism. The Veeam CBT driver is a class filter driver for volume devices that helps Veeam Agent keep track of changed data blocks in a more efficient way. The driver is intended for computers running applications with large database files. The Veeam CBT driver is supported for volume-level and file-level backups.

|  |
| --- |
| NOTE |
| In case of the file-level backup, consider the following:   * Veeam Agent does not use the Veeam CBT driver to back up deduplicated files. * Veeam Agent uses the Veeam CBT driver to back up files of 50 MB and larger including files with unchanged last modification time attribute.  * When you run a backup job for the first time after switching to the Veeam CBT driver, the job may take a significant time to finish. This happens because the Veeam CBT driver cannot retrieve all necessary information about changed data blocks from backup files created with the default CBT mechanism. In this case, files for backup of which Veeam Agent uses the Veeam CBT driver are backed up as a whole.  * The Veeam CBT driver is designed to track data blocks that changed since the last run of the backup job. If you work with a file in an application that downloads the entire file into RAM, after you save the changes, all file blocks will be overwritten. Veeam Agent backs up such a file as a whole upon the next run of the backup job. |

To use the Veeam CBT driver, the Veeam Agent computer must meet the following requirements:

* Run one of the following OSes:

* Microsoft Windows 11 (from version 22H2 to version 25H2).
* Microsoft Windows 10 General Availability Channel 22H2.

* Microsoft Windows 10 Long-Term Servicing Channel versions 2019 and 2021.
* Microsoft Windows Server OS that is supported by Veeam Agent. For more information, see [System Requirements](system_requirements.md).

* Run the Workstation or Server edition of Veeam Agent for Microsoft Windows.

|  |
| --- |
| ![Veeam Changed Block Tracking Driver](images/icon_important.webp) IMPORTANT |
| Do not install the Veeam CBT driver on a computer running Microsoft Windows Server 2012 R2 if one or more volumes on this computer are encrypted with Microsoft BitLocker (or other encryption tool), or if you plan to use Microsoft BitLocker to encrypt volumes on this computer. Concurrent operation of Microsoft BitLocker and Veeam CBT driver may result in driver failures and may prevent the OS from starting. |

To enable the advanced CBT mechanism provided by the Veeam CBT driver, you need to install the driver in the Veeam Agent control panel. You can perform this operation at any time you need. To activate the driver after installation, Veeam Agent needs to reboot the computer. After computer reboot, the Veeam CBT driver will start keeping track of changed data blocks on computer volumes whose data you have selected for backup in the Veeam Agent backup job settings.

In contrast to the default CBT mechanism that supports NTFS volumes only, the Veeam CBT driver can keep track of changed data blocks on volumes that use the following file systems:

* FAT (only for volume-level backups)
* NTFS
* ReFS

Information about changed data blocks is registered in special VCT files. VCT files are stored in the C:\ProgramData\Veeam\EndpointData\CtStore folder on the Veeam Agent computer. When the backup job runs, Veeam Agent for Microsoft Windows uses VCT files to find out what data blocks have changed since the last run of the job, and copies only changed data blocks from the backed-up volume.

If you use the Veeam CBT driver, the C:\ProgramData\Veeam\EndpointData\CtStore folder accessibility is crucial for a successful backup. Consider the following:

* The folder and its content must not be compressed or encrypted.
* The folder and its parent folders must not be reparse points.

|  |
| --- |
| ![Veeam Changed Block Tracking Driver](images/icon_note.webp) NOTE |
| Consider the following:   * If the Veeam Agent computer shuts down unexpectedly, the Veeam CBT driver may fail to register information about changed data blocks in a VCT file. In this case, during the next backup job session, Veeam Agent for Microsoft Windows will need to read all data from the backed-up volume to create incremental backup. As a result, incremental backup will require greater time. * If data blocks are changed on a volume while this volume is mounted on another Windows-based machine, during the next backup job session, Veeam Agent for Microsoft Windows will also read all data from the volume to create incremental backup. * The Veeam CBT driver cannot detect data block changes made on a volume that is mounted in a non-Windows OS. For example, such changes can be made when you boot your computer using a Linux-based antivirus rescue disk. To continue the backup chain after such changes, you need to create active full backup instead of incremental backup. Alternatively, you can reset CBT. To learn more, see [Resetting CBT](cbt_reset.md).  * Changing the layout of the backed-up volume resets the changed block tracking. If this happens, Veeam Agent for Microsoft Windows creates a full backup of the entire volume during the next backup job run. |

Related Tasks

[Managing Veeam CBT Driver](cbt_manage.md)


