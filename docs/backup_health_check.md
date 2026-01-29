---
title: "Health Check for Backup Files"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_health_check.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Health Check for Backup Files


You can instruct Veeam Agent for Microsoft Windows to periodically perform the health check for your backups.

Veeam Agent offers two different health check mechanisms:

* In the first case, Veeam Agent performs a CRC check for metadata and a hash check for data blocks in the backup file to verify their integrity. The health check verifies the latest restore point in the backup chain to make sure that the restore point is consistent, and you will be able to restore data from this restore point. To learn more, see [Standard Health Check](health_check_standard.md).
* In the second case, Veeam Agent does not perform a hash check for data blocks, but verifies metadata for the whole backup, not just the latest restore point. This mechanism uses less traffic than the standard health check as it does not read data from data blocks. This type of health check is intended and is the default option for object storage targets. To learn more, see [Health Check for Object Storage](health_check_object_storage.md).

Health Check Schedule

To run the health check periodically, enable the Perform backup files health check option in the backup job settings and define the health check schedule. By default, the health check is performed on the last Friday of every month. You can change the schedule and run the health check weekly or monthly on specific days.

When you configure the health check schedule, consider the following:

* The health check runs automatically during the first incremental backup job session on the days specified in the health check schedule. If the backup job runs several times on a specified day, the health check is performed only with the first run of the backup job on that day. For example, if the job is scheduled to run several times on Saturday, and the health check is scheduled on Saturday, the health check will only be performed during the first backup job session on Saturday.

The health check is not performed during the first full backup or subsequent active full backup job sessions.

* If Veeam Agent does not run any backup jobs on the day specified in the health check schedule, the health check will be performed during the first backup job session following that day.

For example, you scheduled to run the health check every last day of a month, while the backup job is scheduled to run every day and create an active full backup on Sundays. If the last day of a month falls on a Sunday, the health check will be preformed on the following Monday with the first incremental backup job session on that day.

Limitations for Health Check

* The health check is not performed during an active full backup job session started manually or automatically by schedule.
* The health check is not performed during a backup job session that creates a restore point in the backup cache.
* The health check is not performed during the backup cache synchronization process.

Health Check Retries

The health check itself is started during the backup job session or the job retry session if the backup job session has failed. If the attempts are not successful, Veeam Agent for Microsoft Windows will perform the health check during the last job retry in any case.

If the health check detects corrupted data, Veeam Agent for Microsoft Windows completes the backup job with the Error status and starts the health check retry process. The health check retry starts as a separate backup job session. During the health check retry, Veeam Agent attempts to transport data blocks for the corrupted restore point from the Veeam Agent computer to the target location.

For a backup job started automatically upon schedule, the number of health check retries is equal to the number of job retries specified in the job settings. For a job started manually, Veeam Agent for Microsoft Windows performs 1 health check retry.

|  |
| --- |
| NOTE |
| Consider the following:   * If Veeam Agent for Microsoft Windows fails to fix the corrupted data during all health check retries, you must retry the job manually. In this case, Veeam Agent will transport the necessary data blocks from the Veeam Agent computer to fix the corrupted restore point. * If you try to restore data from a corrupted restore point, Veeam Agent will display a warning message informing you that the restore operation may fail or the restored data may be corrupted. |

Related Topics

[Creating Backup Jobs](backup_job_create.md)


