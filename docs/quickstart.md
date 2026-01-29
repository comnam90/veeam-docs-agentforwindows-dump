---
title: "Getting Started"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/quickstart.html"
last_updated: "7/31/2023"
product_version: "13.0.1.1009"
---

# Getting Started


To protect your computer from a disaster of any kind, you must perform the following operations in Veeam Agent for Microsoft Windows:

1. Create a Veeam Recovery Media.

The Veeam Recovery Media provides an alternate way to boot the Microsoft Windows RE. If your computer fails to start or the hard disk gets corrupted, you can boot the Windows RE from the Veeam Recovery Media and restore your data.

To learn more, see [Creating Veeam Recovery Media](image_create.md).

1. Define what data you want to back up and configure the backup job.

Before you configure a backup job, you should decide on the following backup details:

* Backup scope: entire computer image, individual computer volumes or specific computer folders.
* Backup destination: where you want to store created backups.
* Backup schedule: how often you want to back up your data.

After that, you can configure the backup job. The backup job runs automatically by the defined schedule, captures the data that you have added to the backup scope and creates a chain of restore points in the target location. If your data gets lost or corrupted, you can restore it from the required restore point.

To learn more, see [Creating Backup Jobs](backup_job_create.md).

1. Specify Veeam Agent settings.

You can define resource usage settings during backup, instruct Veeam Agent to automatically check for new product versions and so on. To learn more, see [Specifying Settings](settings.md).

1. Monitor backup task performance.

You can use the Veeam Agent control panel to check how backup tasks are being performed, what errors have occurred during backup job sessions and so on. To learn more, see [Reporting](reporting.md).

1. In case of a disaster, you can restore the entire computer image or specific data on the computer. To learn more, see [Performing Restore](disaster_recovery.md).


