---
title: "Backup Job"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/scheduled_backup_job.html"
last_updated: "9/1/2023"
product_version: "13.0.1.1009"
---

# Backup Job


Veeam Agent for Microsoft Windows lets you configure a scheduled backup job that will perform backup automatically in a timely manner. You can set up the backup job once and forget about running the backup operation manually. Veeam Agent for Microsoft Windows will periodically launch the job to back up necessary data on your computer.

The backup job settings define what data you want to back up, what the target location and retention policy for created backups are and how often you want to back up your data. If necessary, you can re-configure the backup job at any time or remove the job.

Depending on the product edition, you can configure one or more backup jobs in Veeam Agent for Microsoft Windows:

* For the Free product edition, you can configure one backup job only.
* For the Workstation product edition, you can configure an unlimited number of backup jobs targeted at a Veeam Cloud Connect repository plus one backup job targeted at any other supported backup location (local or removable computer drive, network shared folder or Veeam backup repository).
* For the Server product edition, you can configure an unlimited number of backup jobs targeted at any supported backup location.

To learn more about product editions, see [Product Editions](license_editions.md).

For example, you can configure one backup job to create volume-level backup and another backup job to create file-level backup. Or you can configure backup jobs targeted at different backup locations to keep several copies of your backed-up data. You can also configure multiple backup jobs with individual schedule to fine-tune automatic backup creation process.

Settings of the backup job apply to ad-hoc backups as well: standalone full backups, active full backups and incremental backups.

Related Topic

[Backup Job Schedule](scheduled_backup.md)


