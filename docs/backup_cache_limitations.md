---
title: "Limitations for Backup Cache"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_cache_limitations.html"
last_updated: "11/22/2023"
product_version: "13.0.1.1009"
---

# Limitations for Backup Cache


The backup cache has the following limitations:

* The backup cache is available only in Workstation and Server editions of Veeam Agent for Microsoft Windows.
* You cannot use the backup cache for a file-level backup job.
* You cannot restore data from backup files that reside in the backup cache. Until restore points are uploaded from the backup cache to the target location, these restore points are not considered as a fully valid part of the backup chain.
* Veeam Agent for Microsoft Windows does not support creating full backups (including active full backups and synthetic full backups) in the backup cache except for the very first full backup file in the backup chain.
* Veeam Agent for Microsoft Windows does not support creating encrypted backups in the backup cache. If encryption options are specified for the backup job, Veeam Agent will create unencrypted backup files in the backup cache. When the target location becomes available, Veeam Agent will encrypt data prior to uploading it to the remote storage.
* Veeam Agent for Microsoft Windows does not support creating transaction log backups in the backup cache. You cannot enable transaction log backup and the backup cache for the backup job simultaneously.
* Restore points created in the backup cache cannot be uploaded to the target location after you perform the following operations:

* Change target location for backup files in the properties of the backup job
* Change a folder defined for the backup cache

* Move or delete backup files on the target location
* [For Veeam backup repository] Enable or disable data encryption settings in Veeam Backup & Replication

If the backup cache contains one or more restore points at the time when you perform one of these operations, you need to delete restore points from the backup cache.

* You cannot delete restore points from the backup cache while Veeam Agent for Microsoft Windows is performing the following operations:

* Creating a new restore point in the backup cache.
* Uploading a restore point from the backup cache to the target location.


