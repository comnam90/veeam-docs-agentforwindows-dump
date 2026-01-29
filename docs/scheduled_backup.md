---
title: "Backup Job Schedule"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/scheduled_backup.html"
last_updated: "11/28/2025"
product_version: "13.0.1.1009"
---

# Backup Job Schedule


Veeam Agent for Microsoft Windows launches the backup job according to the schedule you define. Scheduling options available for the backup job differ depending on the edition of Veeam Agent:

* For the Free and Workstation product editions, you can schedule the job to start at specific time daily or on specific week days. You can also instruct Veeam Agent to automatically perform backup on specific events. To learn more, see [Scheduling Options in Free and Workstation Editions](scheduled_backup_free_workstation.md).
* For the Server product edition, you can configure daily, monthly and periodic backup job schedule. You can also specify settings for automatic job retries and configure a backup window. To learn more, see [Scheduling Options in Server Edition](scheduled_backup_server.md).

If you configure multiple backup jobs in Veeam Agent, you can specify individual schedule for each job. Veeam Agent processes backup jobs sequentially, one after another. If the backup job must start upon schedule at the time when another backup job is already running, the job will wait for the running job to complete, and start afterwards.

For portable devices, Veeam Agent does not start a backup job on the defined schedule if a device is working on battery and the battery level is below 20%.

If a backup job started by schedule fails, Veeam Agent automatically retries the job.

In the Free and Workstation editions, Veeam Agent retries the job every 10 minutes within the next 23 hours. In the Server edition, you can specify retry settings along with other scheduling options. To learn more, see [Automatic Job Retries](scheduled_backup_retry.md) and [Job Retry](job_retry.md),

In any edition, Veeam Agent can wake your computer from sleep at the time when the backup job must start. To learn more, see [Computer Wake Up from Sleep](schedule_wakeup.md).

Related Tasks

* [Creating Backup Jobs](backup_job_create.md)
* [Editing Backup Job Settings](backup_job_edit.md)
* [Disabling and Enabling Scheduled Backups](disable_backup_job.md)


