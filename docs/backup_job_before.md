---
title: "Before You Begin"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_job_before.html"
last_updated: "12/12/2025"
product_version: "13.0.1.1009"
---

# Before You Begin


Before you configure a backup job, consider the following:

* The target location where you plan to store backup files must have enough free space. The required space depends on the size of backed-up data and backup job settings.
* Available backup job options depend on the edition of Veeam Agent for Microsoft Windows. Make sure that you have obtained and installed a license that has the desired number of instances. To learn more, see [Licensing](licensing.md).
* [For Veeam backup repository] Veeam Agent for Microsoft Windows installed on Microsoft Windows Server 2012 R2 does not support backup to Veeam Backup & Replication on Linux.
* [For Veeam backup repository] You can store created backups in a backup repository only if the backup server runs Veeam Backup & Replication 13.0.1. If you plan to use a commercial version of Veeam Agent for Microsoft Windows with Veeam Backup & Replication, you must install a license in Veeam Backup & Replication that has a sufficient number of instances to protect machines with Veeam Agent. To learn more, see [Managing License](license_vbr.md).
* [For Veeam backup repository] If you plan to use a Veeam backup repository as a target for backups, you must preconfigure user access permissions on this backup repository. To learn more, see [Setting Up User Permissions on Backup Repositories](integrate_permissions.md).
* [For Veeam backup repository] Backup repositories with enabled KMS encryption are not supported. To learn more about KMS encryption for Veeam backup repositories, see the [Key Management System Keys](https://helpcenter.veeam.com/docs/vbr/userguide/kms.html?ver=13) section in the Veeam Backup & Replication User Guide.
* [For Veeam Cloud Connect repository] If you plan to use a cloud repository as a target for backups, make sure that the service provider has communicated to you the necessary data: cloud gateway settings, user account settings and certificate thumbprint.
* A user account under which you launch the New Backup Job wizard must have administrative privileges on the Veeam Agent computer. If the account under which you are currently logged on to Microsoft Windows does not have administrative privileges, you will be prompted to enter administrator credentials.

Backup has the following limitations:

* You cannot save the backup of entire computer on the local computer disk. Use an external hard drive or USB drive, network shared folder or backup repository as a target location.
* Veeam Agent for Microsoft Windows does not back up data to which symbolic links are targeted. It only backs up the path information that the symbolic links contain. After restore, identical symbolic links are created in the restore destination.
* Keep in mind that Veeam Agent stops running the backup job session if it has not finished within 21 days (504 hours).


