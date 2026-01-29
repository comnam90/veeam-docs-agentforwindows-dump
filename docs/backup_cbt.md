---
title: "Changed Block Tracking"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_cbt.html"
last_updated: "9/18/2025"
product_version: "13.0.1.1009"
---

# Changed Block Tracking


To perform incremental backup, Veeam Agent for Microsoft Windows needs to know what data blocks have changed since the previous job session. To get the list of changed data blocks, Veeam Agent for Microsoft Windows uses the changed block tracking mechanism, or CBT. CBT increases the speed and efficiency of incremental backups.

To keep track of changed data blocks, Veeam Agent for Microsoft Windows can use the following mechanisms:

* Default CBT mechanism — this mechanism is enabled by default in all installations of Veeam Agent for Microsoft Windows. To learn more, see [Default Changed Block Tracking Mechanism](backup_cbt_default.md).
* Veeam CBT driver — this driver helps Veeam Agent for Microsoft Windows keep track of changed data blocks in a more efficient way. This functionality is available if the Veeam Agent computer meets a list of requirements. To learn more, see [Veeam Changed Block Tracking Driver](backup_cbt_driver.md).


