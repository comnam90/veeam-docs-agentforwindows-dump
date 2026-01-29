---
title: "Overview"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/overview.html"
last_updated: "10/9/2025"
product_version: "13.0.1.1009"
---

# Overview


Veeam Agent for Microsoft Windows is a data protection and disaster recovery solution for physical and virtual machines. Veeam Agent for Microsoft Windows can be used to protect different types of computers and devices: desktops, laptops and tablets. The solution can be installed on Windows-based workstations, physical servers and virtual machines. To learn about supported OSes, see [System Requirements](system_requirements.md).

|  |
| --- |
| ![Overview](images/icon_note.webp) NOTE |
| Veeam Agent for Microsoft Windows can operate in either standalone or managed mode. Depending on the mode, Veeam Agent provides different features and limitations. To learn more, see [Standalone and Managed Operation Modes](operation_modes.md). |

Veeam Agent for Microsoft Windows offers a variety of features to protect your data. You can:

* Create a Veeam Recovery Media on an external hard drive or USB flash drive, or create an ISO file with the Veeam Recovery Media on disk.
* Create an entire system image backup, back up specific computer volumes or individual folders with files. Backups can be stored on an external hard drive, in a network shared folder, in object storage, in a Veeam backup repository or Veeam Cloud Connect repository.

In case of a disaster, you can perform the following restore operations:

* Start the OS from the Veeam Recovery Media and use Veeam Agent for Microsoft Windows and standard Microsoft Windows tools to diagnose and fix problems.
* Perform bare metal restore.
* Restore necessary data from backups to its original location or a new location.

Veeam Agent for Microsoft Windows integrates with Veeam Backup & Replication. Backup administrators who work with Veeam Backup & Replication can perform advanced tasks with Veeam Agent backups: perform data restore tasks with Veeam Agent backups, manage Veeam Agent backup jobs or backups created with these jobs.

In This Section

* [Solution Architecture](architecture.md)
* [Standalone and Managed Operation Modes](operation_modes.md)
* [Data Backup](backup.md)
* [Data Restore](restore.md)
* [Veeam Recovery Media](recovery_media.md)
* [BitLocker Encrypted Volumes Support](bitlocker.md)
* [Integration with Veeam Backup & Replication](vbr_integration.md)


