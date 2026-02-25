---
title: "Step 6. Finalize Restore"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/integration_file_restore_complete.html"
last_updated: "2/24/2026"
product_version: "13.0.1.1009"
---

# Step 6. Finalize Restore


After you close the wizard, Veeam Backup & Replication opens the Veeam Backup browser with the file system tree of the restored Veeam Agent computer.

You can perform the following operations in the Veeam Backup browser:

* [Compare files and folders from a backup with the original files and folders](integration_file_restore_complete_compare.md).
* [Restore only changed files and folders to the original location](integration_file_restore_complete_changed.md).
* [Copy files and folders to the Veeam Backup & Replication console or network shared folder](integration_file_restore_complete_copy.md).
* [Restore files and folders to the original location](integration_file_restore_complete_original.md).
* [Restore files and folders to another Veeam Agent computer](integration_file_restore_complete_new.md).
* [Restore permissions only](integration_file_restore_complete_permissions.md).
* [Launch application item restore](integration_file_restore_complete_items.md).
* [Open files in Microsoft Windows File Explorer](integration_file_restore_complete_explorer.md).

After you finish restoring files, [close the Veeam Backup browser](integration_file_restore_complete_close.md).

|  |
| --- |
| NOTE |
| Consider the following:   * Folder symbolic links are displayed under the ![Step 6. Finalize Restore](images/symlink_icon.webp) icon. * When restoring symbolic links, Veeam Backup & Replication restores only links, not the content they point to. * Hard links are displayed and restored as files. |


