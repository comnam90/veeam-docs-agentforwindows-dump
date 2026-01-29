---
title: "System Requirements"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/system_requirements.html"
last_updated: "12/12/2025"
product_version: "13.0.1.1009"
---

# System Requirements


The protected computer must meet requirements listed in the table below.

|  |
| --- |
| ![System Requirements](images/icon_note.webp)NOTE |
| The following system requirements apply to Veeam Agent for Microsoft Windows operating in the standalone mode.  To learn about system requirements for Veeam Agent for Microsoft Windows managed by Veeam Backup & Replication, see the [System Requirements for Microsoft Windows Computers](https://helpcenter.veeam.com/docs/vbr/userguide/agents_system_requirements_windows.html?ver=13) section in the Veeam Backup & Replication User Guide. |

| Specification | Requirement |
| --- | --- |
| Hardware | CPU: x64 processor.  Memory: 2 GB RAM or more. Memory consumption varies depending on number and size of processed disks.  Disk Space: 250 MB for product installation.  Network: 1 Mbps or faster. High latency and reasonably unstable WAN links are supported.  System firmware: BIOS or UEFI.  Drive encryption: Microsoft BitLocker (optional). BitLocker encrypted volumes must be unlocked at the moment when Veeam Agent starts the backup or restore operation. Only Microsoft BitLocker is supported for drive encryption. Other drive encryption products are not supported. |
| OS | 64-bit versions of the following operating systems are supported\*:   * Microsoft Windows Server 2025 * Microsoft Windows Server 2022  * Microsoft Windows Server 2019 * Microsoft Windows Server 2016 * Microsoft Windows Server 2012 R2 * Microsoft Windows 11 (from version 22H2 to version 25H2) * Microsoft Windows 10 General Availability Channel 22H2 * Microsoft Windows 10 Long-Term Servicing Channel (from version 2015 to version 2021)   \* Consider the following:   * Small Business Server, Server Essentials, and Server Storage editions of Microsoft Windows Server OSes are supported. * Server Core installations of Microsoft Windows Server OSes are supported for Veeam Agent for Microsoft Windows managed by Veeam Backup & Replication only. To learn more, see the [Veeam Agent Backup](https://helpcenter.veeam.com/docs/vbr/userguide/protect_comp.html?ver=13) section in the Veeam Backup & Replication User Guide. Veeam Agent operating in the standalone mode does not support Server Core installations. * Microsoft Windows OSes installed on ReFS boot partitions are not supported. * Windows Embedded / Windows IoT OSes are supported (except for custom builds by certain vendors that do not have components required for Veeam Agent operation). * Microsoft Failover Clusters are supported for Veeam Agent for Microsoft Windows managed by Veeam Backup & Replication only. To learn more, see the [Veeam Backup & Replication User Guide](https://helpcenter.veeam.com/docs/vbr/userguide/overview.html?ver=13). Veeam Agent operating in the standalone mode does not support Microsoft Failover Clusters. * Veeam Agent for Microsoft Windows installed on Microsoft Windows Server 2012 R2 does not support backup to Veeam Backup & Replication on Linux. |
| File System | Microsoft Windows FAT32/exFAT, NTFS, ReFS file systems are supported.  The supported file system must reside on a volume that is 64 TB or smaller, because Veeam Agent uses the Microsoft Software Shadow Copy Provider to create a volume shadow copy during the backup. To learn more about the limitation, see [Microsoft documentation](https://support.microsoft.com/en-us/help/2967756/usability-limit-for-volume-shadow-copy-service-vss-in-windows). |
| Software | The following required 3rd party software is included in the setup program:   * Veeam OpenSSL3 FIPS Provider * ASP.NET Core Runtime 8.0.21 * .NET Desktop Runtime 8.0.21 * [For Microsoft Windows Server 2012 R2] Microsoft Visual C ++ 2015-2022 Redistributable   When installing the product, the setup program checks whether all prerequisite software is available on the target computer. If some of the required software components are missing, the missing software is installed automatically.  Note: If you already have ASP.NET Core Runtime and NET Desktop Runtime version 8.0.21 or later on your computer, new packages will not be installed. However, make sure that both products have the same version; otherwise Veeam Agent operations will fail. |
| Database | SQLite database engine (installed with the product). |

Consider the following:

* Veeam Agent for Microsoft Windows works with only those hard drive types that are supported by the Microsoft Windows OS. Thus, Veeam Agent supports the 512 bytes and 4 KB sector hard drives only. Other hard drive types are not supported. To learn more, see [Microsoft documentation](https://support.microsoft.com/en-us/help/2510009/microsoft-support-policy-for-4k-sector-hard-drives-in-windows).
* Supported culture settings depend on the version of Microsoft Windows OS installed on your computer. For more information, see [Microsoft documentation](https://learn.microsoft.com/en-us/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).

Backup Source

Veeam Agent for Microsoft Windows supports backup of data that resides in the following types of storage:

* Local (internal) storage of the protected computer.
* Direct attached storage (DAS), such as USB, eSATA or Firewire external drives (USB sticks and SD cards are not supported).
* Storage Area Network (SAN), such as iSCSI connected volumes.

Keep in mind that Veeam Agent cannot work with third-party volume managers installed on the protected computer. Such managers may not allow Veeam Agent to interact with necessary interfaces and services properly.

Backup Target

Backup can be performed to the following types of storage:

Disk-based storage

* Local (internal) storage of the protected computer (not recommended).
* Direct attached storage (DAS), such as USB, eSATA or Firewire external drives, and raw device mapping (RDM) volumes.

|  |
| --- |
| IMPORTANT |
| Storage devices with the exFAT file system are not supported as a backup target. |

* Network Attached Storage (NAS) able to represent itself as SMB (CIFS) share.
* Storage Area Network (SAN), such as iSCSI connected volumes.
* On-premises object storage.
* Veeam Backup & Replication 13.0.1 backup repository.

Cloud storage

* Cloud-based object storage.
* Veeam Cloud Connect 13.0.1 cloud repository.

Network

Consider the following:

* If you back up to a repository managed by a Veeam backup server, Veeam Agent for Microsoft Windows must be able to establish a direct IP connection to the Veeam Backup & Replication server. Veeam Agent cannot work with Veeam Backup & Replication that is located behind a NAT gateway.
* Domain names of the Veeam Agent computer, Veeam Backup & Replication server and other servers in the Veeam backup infrastructure must be resolvable into IPv4 or IPv6 addresses.


