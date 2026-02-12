---
title: "Using SureBackup"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/sn_surebackup.html"
last_updated: "2/11/2026"
product_version: "13.0.1.1009"
---

# Using SureBackup


Veeam Backup & Replication offers the SureBackup technology to test backups and check if you can recover data from them. You can verify any restore point of a backed-up computer protected with Veeam Agent for Microsoft Windows.

To learn more about the logic behind SureBackup, see the [How SureBackup Works](https://helpcenter.veeam.com/docs/vbr/userguide/surebackup_hiw.html?ver=13) section in the Veeam Backup & Replication User Guide.

Before creating the SureBackup job, check limitations for Veeam Agent backups below. Then launch the New SureBackup Job wizard to create the SureBackup job. To learn more, see the [Creating SureBackup Job](https://helpcenter.veeam.com/docs/vbr/userguide/create_surebackup_job.html?ver=13) section in the Veeam Backup & Replication User Guide.

Limitations

For backups created with Veeam Agent for Microsoft Windows, SureBackup has the following limitations:

|  |
| --- |
| IMPORTANT |
| If the backup that you test with the SureBackup job contains pending updates, the Veeam Agent computer may start rebooting while the SureBackup job is running, and the job will fail. |

* SureBackup is not supported for backups stored in the Veeam Cloud Connect repository.
* SureBackup is not supported for backups stored in the archive tier of the the scale-out backup repository.

* For backups created with Veeam Agents, you cannot exclude objects from the scope of the SureBackup job at the Linked Jobs step of the New SureBackup Job wizard.

* [For full recoverability testing mode] SureBackup is not supported for backups containing drives greater than 64 TB.
* [For full recoverability testing mode] If you plan to verify computer recovery with VMware vSphere, consider the following:

* SureBackup is not supported for backups of 4 KB sector drives.
* SureBackup is not supported for backups of storage spaces.
* SureBackup is not supported for backups containing more than 54 drives.

* [For full recoverability testing mode] When Veeam Backup & Replication publishes virtual machines based on backed-up Veeam Agent computers in the isolated virtual environment, all these virtual machines are included in the first isolated network added during the virtual lab configuration. To learn more, see the [Create Isolated Networks](https://helpcenter.veeam.com/docs/vbr/userguide/vlab_isolated_network_vm.html?ver=13) section in the Veeam Backup & Replication User Guide.

* [For full recoverability testing mode] SureBackup is not supported for file-level backups. You must use entire machine or volume-level backup of the protected computer. The backup must include the computer system volume. To learn more about backup types, see [Backup Types](backup_types.md).

* [For full recoverability testing mode] SureBackup is not supported if the Microsoft Windows system partition and boot partition of the backed-up computer are located on different drives.

![Using SureBackup](images/agents_surebackup.webp "Launch SureBackup Wizard")


