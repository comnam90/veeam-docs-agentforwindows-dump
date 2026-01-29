---
title: "Backup on Specific Events"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/scheduled_backup_events.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Backup on Specific Events


In addition to the basic job schedule, you can instruct Veeam Agent to launch the backup job on specific events. Veeam Agent lets you trigger backup on the following events:

* Lock — the user locks the computer.
* Log off — the user performs a logout operation on the computer.
* When backup target is connected — the target backup location becomes available: the user attaches a known removable storage device to the computer or a network connection to the backup repository is established.

You can instruct Veeam Agent to eject the removable storage device after the backup job successfully completes. This helps to protect backup files in the target location from encrypting ransomware, such as CryptoLocker.

Backup on specific event helps you ensure that you capture all changes made within a specific time interval — for example, during a working day. When the necessary event occurs, Veeam Agent automatically launches the scheduled backup job. As a result, you can be sure that all changes made within some period of time are backed up, and you do not lose your data.

If you choose to perform backup on specific events, you can restrict the frequency of backup job sessions. You can instruct Veeam Agent not to start the backup job at specific events more often than once a specified time interval, for example, not more often than every 2 hours. This option does not affect daily schedule. Daily backups are performed according to the defined schedule regardless of the specified time interval.

Backup on specific events helps you fine-tune the backup job schedule. For example, you can specify the following scheduling settings for the backup job:

* The backup job must start automatically at 10:00 PM every day.
* The backup job must start at computer lock.
* The backup job must not run more often than every 2 hours.

Veeam Agent will launch the backup job at the end of the working day, when you lock your computer. In addition, Veeam Agent will perform backup at 10:00 PM regardless of the time interval between the computer lock and scheduled backup.

If you lock your computer later than at 10:00 PM, Veeam Agent will perform backup in the following order. At 10:00 PM, Veeam Agent will launch the backup job upon the daily schedule. If the time interval between the scheduled backup and computer lock is greater than 2 hours, Veeam Agent will additionally perform backup at computer lock. If the time interval between the scheduled backup and computer lock is not greater than 2 hours, Veeam Agent will not perform backup at computer lock.


