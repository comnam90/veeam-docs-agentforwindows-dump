---
title: "File-Level Restore"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/restore_file.html"
last_updated: "11/22/2023"
product_version: "13.0.1.1009"
---

# File-Level Restore


If you have lost or modified files and folders on your computer by mistake, you can restore a copy of the necessary objects from the backup. For file-level restore, you can use a backup of any type:

* Volume-level backup
* File-level backup

Veeam Agent for Microsoft Windows does not extract files and folders from the backup file. Instead, it uses Veeam’s proprietary driver to publish the backup content directly into the computer file system, under C:\VeeamFLR\<Volume N>. For accessing the backup file content, Veeam Agent for Microsoft Windows uses a separate program — Virtual Disk Driver (VDK) that is provided with the product.

After the backup content is mounted, you can use a built-in Veeam Backup browser or Microsoft Windows Explorer to browse and copy necessary files and folders to your local machine drive, save them in a network shared folder or point applications to files and work with them in a regular way.

Related Tasks

* [Restoring Files and Folders](files_restore.md)
* [How to Restore Files from Backup](howto_restore_files.md)


