---
title: "Restoring Files and Folders"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/files_restore.html"
last_updated: "12/18/2024"
product_version: "13.0.1.1009"
---

# Restoring Files and Folders


If some files and folders on your computer get lost or corrupted, you can restore them from backups. For file-level restore, you can use backups of any type:

* Volume-level backups (backups of the entire computer or specific volumes)
* File-level backups

When you perform file-level restore, Veeam Agent for Microsoft Windows publishes the backup content directly into the computer file system and displays it in the Veeam Backup browser. You can restore files and folders to their initial location, copy files and folders to a new location or target applications to restored files and work with them as usual.

Before you perform file-level restore, [check prerequisites](files_restore_before.md). Then use the File Level Restore wizard to restore the necessary files or folders.

1. [Launch the File Level Restore wizard](files_restore_launch.md).
2. [Specify the backup file location](files_restore_source.md).
3. [Select the remote storage type](files_restore_remote.md).
4. [Specify remote storage settings](files_restore_remote_conf.md).
5. [Select a backup](files_restore_backup.md).
6. [Select a restore point](files_restore_point.md).
7. [Verify restore settings](files_restore_complete.md).
8. [Save restored files](files_restore_save.md).

Related Topics

[File-Level Restore](restore_file.md)


