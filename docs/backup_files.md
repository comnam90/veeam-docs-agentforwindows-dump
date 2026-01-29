---
title: "Types of Backup Files"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_files.html"
last_updated: "10/23/2023"
product_version: "13.0.1.1009"
---

# Types of Backup Files


Veeam Agent produces backup files of the following types:

* VBK — full backup file.
* VIB — incremental backup file.
* VBM — backup metadata file. The backup metadata file is updated with every backup job session. It contains information about the computer on which the backup was created, every restore point in the backup chain, how restore points are linked to each other and so on. The backup metadata file is required for performing file-level and volume-level restore operations.

|  |
| --- |
| ![Types of Backup Files](images/icon_note.webp) NOTE |
| For backup jobs with database log backup options enabled, Veeam Agent for Microsoft Windows additionally produces backup files of the following types:   * VLB, VSM and VLM files — for Microsoft SQL Server transaction log backups * VLB, VOM and VLM files — for Oracle archived log backups. |


