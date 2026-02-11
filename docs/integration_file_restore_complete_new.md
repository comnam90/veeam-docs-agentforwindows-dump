---
title: "Restoring Files and Folders to Another Veeam Agent Computer"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/integration_file_restore_complete_new.html"
last_updated: "2/11/2026"
product_version: "13.0.1.1009"
---

# Restoring Files and Folders to Another Veeam Agent Computer


|  |
| --- |
| NOTE |
| Consider the following:   * You can restore files and folders only to a computer that is managed by the same Veeam backup server that manages the Veeam backup repository where the backup resides. * You cannot restore files and folders to cloud machines. * You cannot restore files and folders that are in the comparison state. |

To restore files and folders to another Veeam Agent computer, do the following:

1. Select the necessary files and folders in the file system tree or in the details pane on the right.
2. Right-click one of the selected items and select one of the following:

* If you want to overwrite files and folders with identical names on the target computer, select Restore to > Overwrite.
* If you want to keep files and folders with identical names on the target computer, select Restore to > Keep.

If there are items with identical names, Veeam Backup & Replication will add the RESTORED\_YYYYMMDD\_HHMMSS postfix to the original names and store the restored items on the target computer.

Alternatively, you can select the same commands on the ribbon.

1. In the Select Host window, select the target Veeam Agent computer.
2. If prompted, in the Credentials window, provide credentials to connect to the target computer.
3. In the Choose Target Folder window, specify a path to the folder where the restored objects will be saved.


