---
title: "Publishing Disks"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/integration_publish.html"
last_updated: "2/11/2026"
product_version: "13.0.1.1009"
---

# Publishing Disks


You can use the Veeam backup console to publish disks from Veeam Agent backups.

|  |
| --- |
| TIP |
| You can publish disks using the PowerShell console. To learn more, see the [Disk Publishing (Data Integration API)](https://helpcenter.veeam.com/docs/vbr/powershell/veeam_data_integration_api.html?ver=13) section in the Veeam PowerShell Reference. |

Disk publishing allows you to save time by getting backup content of one or multiple disks instead of all disks from a backup. This technology gives read-only access to data and helps if you want to analyze data of your backup. For example, look for specific documents or usage patterns, or perform antivirus scan of backed-up data.

For Microsoft Windows-based Veeam Agent computers, disk publishing uses the iSCSI protocol. After the publishing, the target server can access the backup content using the iSCSI initiator and read the necessary data from the disk.

To learn more, see the [Disk Publishing](https://helpcenter.veeam.com/docs/vbr/userguide/data_integration_api.html?ver=13) section in the Veeam Backup & Replication User Guide.


