---
title: "Product Editions"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/license_editions.html"
last_updated: "10/17/2023"
product_version: "13.0.1.1009"
---

# Product Editions


Veeam Agent for Microsoft Windows offers three product editions that define product functionality and operation modes:

* Server — a commercial edition that provides access to all product functions. The Server edition is intended for performing data protection tasks on servers that run the Microsoft Windows OS. To use the Server edition of Veeam Agent for Microsoft Windows, you must obtain and install a license on the protected computer. The license must have a number of instances that is enough to protect a machine with the Server product edition.
* Workstation — a commercial edition that offers capabilities for performing data protection tasks on desktop computers and laptops that run the Microsoft Windows OS. To use the Workstation edition of Veeam Agent for Microsoft Windows, you must obtain and install a license on the protected computer. The license must have a number of instances that is enough to protect a machine with the Workstation product edition.
* Free — a free edition that offers limited capabilities. In contrast to the Workstation and Server editions, the Free edition does not require a license.

For more information about product editions, pricing and features available for them, see [this Veeam webpage](https://www.veeam.com/windows-cloud-server-backup-agent.html).

To learn more about instance licensing, see [this Veeam webpage](https://www.veeam.com/instance-licensing.html).

When you install a license on the protected computer, you can select the product edition of Veeam Agent for Microsoft Windows: Workstation or Server (if both editions are supported by the license). To learn more, see [Selecting Product Edition](settings_mode.md).

If you use Veeam Agent for Microsoft Windows with Veeam Backup & Replication, you should manage product licenses and editions from the Veeam Backup & Replication console. To learn more, see [Managing License](license_vbr.md).

If the license has expired and you have used backup job options available for the Workstation and Server editions, you must disable these options in the properties of the backup job. Otherwise, the backup job will fail.


