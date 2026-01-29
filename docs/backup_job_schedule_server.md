---
title: "Scheduling Settings in Server Edition"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_job_schedule_server.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Scheduling Settings in Server Edition


At the Schedule step of the wizard, select to run the backup job manually or schedule the job to run on a regular basis.

|  |
| --- |
| ![Scheduling Settings in Server Edition](images/icon_important.webp) IMPORTANT |
| If the power scheme on your computer does not allow using wake up timers, Veeam Agent for Microsoft Windows will ask you to change the power scheme settings. Click Yes to allow Veeam Agent for Microsoft Windows to wake your computer from sleep for backup.  You can manually change the power scheme settings on your computer. To do this, navigate to Control Panel > All Control Panel Items > Power Options > Edit Plan Settings. |

To specify the job schedule:

1. Select the Run the job automatically check box. If this check box is not selected, you will have to start the backup job manually to create backup.
2. Define scheduling settings for the job:

* To run the job at specific time daily, on defined week days or with specific periodicity, select Daily at this time. Use the fields on the right to configure the necessary schedule.

* To run the job once a month on specific days, select Monthly at this time. Use the fields on the right to configure the necessary schedule.
* To run the job repeatedly throughout a day with a specific time interval, select Periodically every. In the field on the right, select the necessary time unit: Hours or Minutes. Click Schedule and use the time table to define the permitted time window for the job. In the Start time within an hour field, specify the exact time when the job must start.

A repeatedly run job is started by the following rules:

* Veeam Agent for Microsoft Windows always starts counting defined intervals from 12:00 AM. For example, if you configure to run a job with a 4-hour interval, the job will start at 12:00 AM, 4:00 AM, 8:00 AM, 12:00 PM, 4:00 PM and so on.
* If you define permitted hours for the job, after the denied interval is over, Veeam Agent for Microsoft Windows will immediately start the job and then run the job by the defined schedule.

For example, you have configured a job to run with a 2-hour interval and defined permitted hours from 9:00 AM to 5:00 PM. According to the rules above, the job will first run at 9:00 AM, when the denied period is over. After that, the job will run at 10:00 AM, 12:00 PM, 2:00 PM and 4:00 PM.

* To run the job continuously, select the Periodically every option and choose Continuously from the list on the right. A new backup job session will start as soon as the previous backup job session finishes.

1. In the Automatic retry section, define whether Veeam Agent for Microsoft Windows must attempt to run the backup job again if the job fails for some reason. Enter the number of attempts to run the job and define time intervals between them. If you select continuous backup, Veeam Agent for Microsoft Windows will retry the job for the defined number of times without any time intervals between the job runs.
2. In the Backup window section, define the time interval within which the backup job must complete. The backup window prevents the job from overlapping with production hours and ensures that the job does not impact performance of your server. To set up a backup window for the job:

1. Select the Terminate job if it exceeds allowed backup window check box and click Window.
2. In the Time Periods window, define the allowed hours and prohibited hours for backup. If the job exceeds the allowed window, it will be automatically terminated.

![Scheduling Settings in Server Edition](images/ep_backup_job_schedule_new.webp "Schedule Settings in Server Edition")


