---
title: "Product Editions"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/license_editions.html"
last_updated: "3/27/2026"
product_version: "13.0.2.1102"
---

# Product Editions


Veeam Agent for Microsoft Windows offers three product editions that define product functionality and operation modes:

* Server — a commercial edition that provides access to all product functions and is intended for performing data protection tasks on computers that run the Microsoft Windows OS. Veeam Agent can operate in the Server edition if a commercial license that supports this edition is installed on the protected computer.
* Workstation — a commercial edition that offers limited capabilities that are sufficient for performing data protection tasks on computers that run the Microsoft Windows OS. Veeam Agent can operate in the Workstation edition if a commercial license that supports this edition is installed on the protected computer.
* Free — a free edition that offers the capabilities of the Workstation edition with certain limitations. In contrast to the Workstation and Server editions, the Free edition does not require a license.

To learn more about differences between product editions, see [Differences Between Product Editions](#dif).

Consider the following:

* When you install a license on the protected computer, you can select the Workstation or Server edition (if both editions are supported by the license). To learn more, see [Selecting Product Edition](settings_mode.md).
* If you use Veeam Agent with Veeam Backup & Replication, the Veeam Agent product edition is managed by Veeam Backup & Replication. To learn more, see [Managing License](license_vbr.md).
* If the license has expired and you have used backup job options available for the Workstation and Server editions, you must disable these options in the properties of the backup job. Otherwise, the backup job will fail.

Differences Between Product Editions

Keep in mind that the following backup options are not available in the Free edition:

Backup options available in the Server edition only

* Guest processing.
* Parallel disk processing.
* Advanced backup job scheduling:

* Daily, monthly, and periodic backup job schedules.
* Custom number of automatic retry attempts and the time intervals between them.
* Backup window to prevent the job from overlapping with production hours.

Backup options available in the Server and Workstation editions

* Multiple backup jobs:

* In the Server edition, you can configure unlimited number of backup jobs targeted at all supported backup repositories.
* In the Workstation edition, the number of backup jobs that you can target at a local drive, network shared folder, object storage repository or Veeam backup repository is limited to one. In addition to this backup job, you can configure an unlimited number of backup jobs targeted at a Veeam Cloud Connect repository.

|  |
| --- |
| NOTE |
| In the Free edition, you can configure only one backup job targeted at a local drive, network shared folder, or Veeam backup repository. |

* Direct backup to object storage and backup to Veeam Cloud Connect repository.
* Synthetic full backup.
* Veeam CBT driver.
* Backup cache.
* Long-Term Retention Policy (GFS).

To learn more about product editions, pricing and features available for them, see [this Veeam webpage](https://www.veeam.com/windows-cloud-server-backup-agent.html).


