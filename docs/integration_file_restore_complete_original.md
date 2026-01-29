---
title: "Restoring Files and Folders to Original Location"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/integration_file_restore_complete_original.html"
last_updated: "8/27/2025"
product_version: "13.0.1.1009"
---

# Restoring Files and Folders to Original Location


To restore files and folders to the original location, do the following:

1. Select the necessary files and folders in the file system tree or in the details pane on the right.
2. Right-click one of the selected items and select one of the following:

* To overwrite the original files and folders with the ones restored from the backup, select Restore > Overwrite.
* To save the restored files and folders next to the original ones, select Restore > Keep.

Veeam Backup & Replication will add the RESTORED\_YYYYMMDD\_HHMMSS postfix to the original names and store the restored items in the same folder where the original items reside.

Alternatively, you can select the same commands on the ribbon.

[![Restore Files to Original Location](images/agent_file_restore_complete_original.webp)](images/agent_file_restore_complete_original.webp "Restore Files to Original Location")


