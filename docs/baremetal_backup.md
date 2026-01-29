---
title: "Step 7. Select Backup"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/baremetal_backup.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Step 7. Select Backup


The Backup step of the wizard is available if you have chosen to restore data from a backup file that resides in a remote location — in object storage, in a network shared folder, in a Veeam backup repository or Veeam Cloud Connect repository.

From the list of backups, select a backup from which you want to recover data. To quickly find the necessary backup, use the search field at the bottom of the window: enter a backup name or a part of it in the search field and click the Start search button on the right or press [ENTER].

In the list of backups, Veeam Agent for Microsoft Windows displays only those backups that meet the following criteria:

1. Backups created at the volume level. File-level backups are not displayed.
2. [For backup repository target] Backups accessible by the user whose credentials are specified at the [Backup Server](baremetal_vbr.md) step of the wizard:

* If you specify credentials for the user who has access to the backup repository, the list of backups will include only backups created by this user.
* If you specify credentials for the Backup Administrator on the backup server, the list of backups will include all Veeam Agent backups stored in the backup repository.

1. [For cloud repository target] Backups accessible by the user whose credentials are specified at the [Credentials](baremetal_sp.md#creds) step of the wizard:

* If you specify credentials for the tenant account, the list of backups will include backups created by all users who create backups under this tenant account and its subtenant accounts.
* If you specify credentials for the subtenant account, the list of backups will include only those Veeam Agent backups that were created under this subtenant account.

|  |
| --- |
| NOTE |
| If you want to restore data from an encrypted backup, and the Veeam Recovery Media from which you booted your computer does not contain encryption keys required to unlock the backup file, you need to provide a password to unlock the encrypted file. To learn more, see [Restoring Data from Encrypted Backups](restore_encrypted.md). |

![Step 7. Select Backup](images/ep_baremetal_backup.webp "Select Backup")


