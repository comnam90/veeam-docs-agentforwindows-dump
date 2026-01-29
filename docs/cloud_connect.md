---
title: "Backup to Veeam Cloud Connect Repository"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/cloud_connect.html"
last_updated: "9/1/2023"
product_version: "13.0.1.1009"
---

# Backup to Veeam Cloud Connect Repository


If you want to store your data in the cloud, you can connect to a Veeam Cloud Connect service provider (SP) and create Veeam Agent backups in a cloud repository.

Limitations for Backup to Cloud Repository

Backup to a Veeam Cloud Connect repository has the following limitations:

* You can store backups in a Veeam Cloud Connect repository if you use the Workstation or Server edition of Veeam Agent for Microsoft Windows only.
* You cannot use a Veeam Cloud Connect repository as a target for standalone full backup. To learn more, see [Standalone Full Backup](adhoc_backup_full.md).
* Veeam Agent for Microsoft Windows does not support creating transaction log backups in the cloud repository. You cannot enable transaction log backup options in the properties of the backup job targeted at the cloud repository.


