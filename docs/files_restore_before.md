---
title: "Before You Begin"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/files_restore_before.html"
last_updated: "10/29/2025"
product_version: "13.0.1.1009"
---

# Before You Begin


Before you begin the file-level restore process, check the following prerequisites.

General

* The backup from which you plan to restore data must be successfully created at least once.
* When restoring symbolic links [to the original location or to another computer](files_restore_initial.md), Veeam Agent for Microsoft Windows recovers only links, not the content they point to, except for symbolic links that point to SMB (CIFS) shared folders; in this case, links are restored as empty folders.
* When [copying](files_restore_new.md) symbolic links, Veeam Agent for Microsoft Windows copies the content to which the links point.
* [For backups stored in network shared folders and on backup repositories] You must have access to the target location where the backup file resides.

* [For backup repository targets] If you plan to restore data from a backup stored in a backup repository, you must have access permissions on this backup repository. To learn more, see [Setting Up User Permissions on Backup Repositories](integrate_permissions.md).

|  |
| --- |
| NOTE |
| Consider the following:   * If you perform restore under an account that does not have administrative privileges, you might not be able to access certain files or folders due to the user's security context settings. To learn more about the security context, see [Microsoft documentation](https://learn.microsoft.com/en-us/windows/win32/ad/security-contexts-and-active-directory-domain-services). * When you restore files or folders, target EFS settings are applied to the restored objects. For example, if you restore files or folders to a folder encrypted with EFS, the restored objects are encrypted. |

ReFS Restore

If you restore files or folders from a ReFS volume-level backup that was made on another machine, the Veeam Agent computer where you perform restore must run the OS that supports the specific ReFS version. For example, you can restore files from a ReFS 3.x volume only to a computer that runs one of the following OSes:

* Microsoft Windows 10 version 22H2
* Microsoft Windows Server 2016 or later

NTFS Restore

* If you restore files or folders from an NTFS volume-level backup that was made on another machine, and data deduplication is enabled for some volumes of the backup, the Veeam Agent computer where you perform restore must run the same OS version or later as the backed-up machine OS, and data deduplication on this computer must be enabled.
* If you restore files or folders from an NTFS volume-level backup that was made on another machine, and the allocation unit size of volumes is set to 128K or greater, the Veeam Agent computer where you perform restore must run one of the following OSes:

+ Microsoft Windows 10 version 22H2
+ Microsoft Windows Server 2019 or later


