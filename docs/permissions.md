---
title: "Permissions"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/permissions.html"
last_updated: "10/23/2023"
product_version: "13.0.1.1009"
---

# Permissions


Depending on the scenario, the user accounts must have the permissions listed in the following subsections:

* [Permissions for Backup to Object Storage](#obj_stor)

* [Permissions for Guest Processing](#guest_win)

Permissions for Backup to Object Storage

If you plan to back up data to object storage, make sure that the user account that you use to connect to the object storage has the required permissions. The list of required permissions differs depending on the selected object storage:

* [Amazon S3 or S3 compatible](#S3)
* [Google Cloud Storage](#Google)

Amazon S3 or S3 compatible

If you plan to back up data to the Amazon S3 or S3 compatible storage, make sure the user account that you plan to use has the following permissions:

Identity-based permission:

|  |
| --- |
| { |

Resource-based permissions:

|  |
| --- |
| {   "s3:DeleteObject",   "s3:GetBucketLocation",   "s3:GetBucketObjectLockConfiguration",   "s3:GetBucketVersioning",   "s3:GetObject",   "s3:ListBucket",   "s3:PutObject" } |

|  |
| --- |
| TIP |
| For information about required permissions for Amazon S3 storage with immutability enabled, see the [Using Object Storage Repositories](https://helpcenter.veeam.com/docs/vbr/userguide/required_permissions.html?ver=13#using-object-storage-repositories) section in the Veeam Backup & Replication User Guide. |

Google Cloud Storage

If you plan to back up data to the Google Cloud storage, make sure the user account that you plan to use has the following permissions:

|  |
| --- |
| {   "storage.buckets.get",   "storage.buckets.list",   "storage.objects.create",   "storage.objects.delete",   "storage.objects.get",   "storage.objects.list" } |

Permissions for Guest Processing

To use guest processing, make sure to configure user accounts according to the requirements listed in this section.

Consider the following general requirements when choosing a user account:

* [For file indexing] Choose a user account that has administrator privileges.
* When using Active Directory accounts, make sure to provide a user account in the DOMAIN\Username format.
* When using local user accounts, make sure to provide a user account in the Username or HOST\Username format.
* To process a Domain Controller server, make sure that you are using a user account that is a member of the DOMAIN\Administrators group.
* To back up a Read-Only Domain controller, a delegated RODC administrator account is sufficient. For more information, see [Microsoft documentation](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc755310%28v%3Dws.10%29#Anchor_1).

Depending on the application you need to back up, the user must have the permissions listed in the table below:

| Application | Required Permission |
| --- | --- |
| Microsoft SQL Server | To back up Microsoft SQL Server data, the user whose account you plan to use must be:   * Local Administrator on the Veeam Agent computer. * System administrator (has the Sysadmin role) on the target Microsoft SQL Server.   If you need to provide minimal permissions, the user account must be assigned the following roles and permissions:   * SQL Server instance-level role: public and dbcreator. * Database-level roles and roles for the model system database: db\_backupoperator, db\_denydatareader, public; for the master system database — db\_backupoperator, db\_datareader, public;  for the msdb system database — db\_backupoperator, db\_datareader, public, db\_datawriter. * Securables: view any definition, view server state, connect SQL. |
| Microsoft Active Directory | To back up Microsoft Active Directory data, the user account must be a member of the built-in Administrators group. |
| Microsoft Exchange | To back up Microsoft Exchange data, the user account must have the Local Administrator permissions in Microsoft Exchange. |
| Oracle | To back up Oracle data, the user account must be configured as follows:   * The user account must be a member of both the Local Administrators group and the ORA\_DBA group (if OS authentication is used).  * The user account must be granted SYSDBA privileges. |
| Microsoft SharePoint | To back up Microsoft SharePoint server, the user account must have the Farm Administrator role.  To back up Microsoft SQL databases of the Microsoft SharePoint Server, the user account must have the same privileges as for the [Microsoft SQL Server](#sql). |


