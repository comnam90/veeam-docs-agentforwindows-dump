---
title: "Integration with Veeam Backup & Replication"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/vbr_integration.html"
last_updated: "11/19/2025"
product_version: "13.0.1.1009"
---

# Integration with Veeam Backup & Replication


If you plan to use Veeam Agent for Microsoft Windows 13.0.1 with Veeam Backup & Replication, you must install Veeam Backup & Replication 13.0.1 on the Veeam backup server.

|  |
| --- |
| ![Integration with Veeam Backup & Replication](images/icon_note.webp)NOTE |
| You can also use Veeam Backup & Replication to manage Veeam Agent for Microsoft Windows on computers in your infrastructure. Within the Veeam Agent management scenario, you can remotely deploy Veeam Agent for Microsoft Windows to your computers, as well as configure and manage Veeam Agent backup jobs in Veeam Backup & Replication. To learn more, see the [Veeam Agent Backup](https://helpcenter.veeam.com/docs/vbr/userguide/protect_comp.html?ver=13) section in the Veeam Backup & Replication User Guide.  The current guide covers subjects related to Veeam Agent for Microsoft Windows operating in the standalone mode. |

You can store backup files created with Veeam Agent for Microsoft Windows in backup repositories managed by Veeam Backup & Replication. To do this, you must select a backup repository as a target location in the properties of the Veeam Agent backup job. To learn more about backup repositories, see the [Backup Repositories](https://helpcenter.veeam.com/docs/vbr/userguide/backup_repository.html?ver=13) and [Scale-Out Backup Repositories](https://helpcenter.veeam.com/docs/vbr/userguide/backup_repository_sobr.html?ver=13) sections in the Veeam Backup & Replication User Guide.

Veeam Agent for Microsoft Windows works with the backup repository as with any other target location. Backup files are stored in a separate folder; you can perform standard restore operations using these files.

Information about Veeam Agent backups stored in the backup repositories, backup jobs and sessions becomes available in the Veeam Backup & Replication console:

* The Veeam Agent for Microsoft Windows backup job is displayed in the list of jobs in Veeam Backup & Replication.
* Backup files created with Veeam Agent for Microsoft Windows are displayed in the list of backups, under the Backups > Disk or Backups > Object Storage node.
* Performed job sessions are available in the History view of Veeam Backup & Replication.

Backup administrators working with Veeam Backup & Replication can perform a set of operations with Veeam Agent backups:

* Perform data protection operations: copy Veeam Agent backups to secondary backup repositories and archive these backups to tape; scan backups to detect malware or sensitive data.

* Perform restore operations: restore individual files and folders, application items; restore computer disks and convert them to the VMDK, VHD or VHDX format; restore Veeam Agent backups to Microsoft Azure, Amazon Elastic Compute Cloud, Google Compute Engine or to other hypervisors; publish disks from backups.
* Perform administrative tasks: disable and delete Veeam Agent backup jobs, remove Veeam Agent backups and so on.

Related Topics

* [Backup to Veeam Cloud Connect Repository](cloud_connect.md)
* [Managing Veeam Agent in Veeam Backup & Replication](agent_management.md)

Related Tasks

[Using with Veeam Backup & Replication](integrate.md)


