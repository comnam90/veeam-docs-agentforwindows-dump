---
title: "Copying Veeam Agent Backups"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/integration_copy.html"
last_updated: "2/11/2026"
product_version: "13.0.1.1009"
---

# Copying Veeam Agent Backups


Veeam Backup & Replication offers the copying backup functionality that can be helpful if you want to copy backups of a backup job to another repository, local or shared folder.

When Veeam Backup & Replication performs the copy operation, it disables the job, copies files to the target location and then enables the job. After the copy operation finishes, the copied backups are shown in a node with the (Exported) postfix in the inventory pane.

|  |
| --- |
| NOTE |
| You cannot copy backups to/from object storage repositories. |

To copy a backup, do the following:

1. Open the Home view.
2. In the inventory pane, click Backups.
3. In the working area, right-click the backup and select Copy backup.

[![Copy Backup](images/ep_copy_backup.webp)](images/ep_copy_backup.webp "Copy Backup")


