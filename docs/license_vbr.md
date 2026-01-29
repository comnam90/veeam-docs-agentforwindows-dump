---
title: "Managing License"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/license_vbr.html"
last_updated: "5/2/2025"
product_version: "13.0.1.1009"
---

# Managing License


If you plan to use Veeam Agent with Veeam Backup & Replication, you must install a license in Veeam Backup & Replication or Veeam Backup Enterprise Manager. The license must have a total number of instances that is sufficient to protect machines (servers and workstations) on which you plan to install Veeam Agent. For more information, see [Veeam Licensing Policy](https://www.veeam.com/licensing-policy.html#instance-conversion).

After Veeam Agent connects to Veeam Backup & Replication, Veeam Agent automatically starts consuming instances in the license. The product edition for Veeam Agent is selected depending on the OS running on the Veeam Agent computer. You can switch to another commercial edition of Veeam Agent manually if needed.  If you do not want Veeam Agents to consume instances, you can restrict instance consumption. For more information, see [Managing Instance Consumption by Veeam Agents](manage_instance_consumption.md).

The number of backup jobs configured in Veeam Agent does not impact instance consumption. For example, if 2 backup jobs are configured in Veeam Agent that operates in the Server edition, this Veeam Agent will consume instances required for 1 server.

Veeam Agent obtains information about the license from Veeam Backup & Replication and keeps it locally on the Veeam Agent computer. Information about the license is valid for 32 days. If Veeam Agent does not connect to Veeam Backup & Replication during this period, Veeam Backup & Replication will revoke its license.

|  |
| --- |
| NOTE |
| In addition to managing Veeam Agent licenses, you can use the Veeam Backup & Replication console to manage Veeam Agent backup jobs and perform operations with backups created by these jobs.  If your backup server is connected to Veeam Backup Enterprise Manager, you can use Veeam Backup Enterprise Manager to manage licenses and perform restore tasks with Veeam Agent backups. You cannot manage Veeam Agent backup jobs with Veeam Backup Enterprise Manager. |

For more information on Veeam Backup & Replication licensing, see the [Licensing](https://helpcenter.veeam.com/docs/vbr/userguide/licensing.html?ver=13) section in the Veeam Backup & Replication User Guide.

Related Tasks

* [Managing Instance Consumption by Veeam Agents](manage_instance_consumption.md)

* [Assigning License to Veeam Agent](license_vbr_mode.md)
* [Viewing Licensed Veeam Agents and Revoking License](license_vbr_revoke.md)


