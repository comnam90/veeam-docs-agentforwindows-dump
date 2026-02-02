---
title: "Closing Veeam Backup Browser"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/integration_file_restore_complete_close.html"
last_updated: "1/30/2026"
product_version: "13.0.1.1009"
---

# Closing Veeam Backup Browser


You can browse Veeam Agent computer files only while the Veeam Backup browser is open. After the Veeam Backup browser is closed, Veeam Backup & Replication unmounts Veeam Agent computer disks from the machine where the Veeam Backup & Replication console is installed and from the mount server (if you have restored Veeam Agent computer files to the original location).

It is recommended that you close the Veeam Backup browser after you have finished restoring Veeam Agent computer files. When the Veeam Backup browser is open, the backup file whose computer file system is displayed in the browser is locked in the backup repository. As a result, some scheduled operations that use this backup file may fail.

Veeam Backup & Replication checks if there is any activity in the Veeam Backup browser with an interval of 5 minutes. If the user or Veeam Backup & Replication components and services do not perform any actions for 30 minutes, Veeam Backup & Replication displays a warning that the Veeam Backup browser is to be closed in 5 minutes.

After the warning is displayed, you can perform one of the following actions:

* You can close the Veeam Backup browser manually.
* You can click Cancel to postpone the close operation. In this case, the Veeam Backup browser will remain open for 5 minutes. After this period expires, Veeam Backup & Replication will display the warning again.
* You can perform no action at all. In this case, the Veeam Backup browser will close automatically in 5 minutes.


