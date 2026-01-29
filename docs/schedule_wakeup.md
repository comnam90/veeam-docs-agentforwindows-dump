---
title: "Computer Wake Up from Sleep"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/schedule_wakeup.html"
last_updated: "10/28/2025"
product_version: "13.0.1.1009"
---

# Computer Wake Up from Sleep


If your computer is in the standby mode at the time when the backup job must start, Veeam Agent for Microsoft Windows automatically wakes your computer from sleep. The wake-up feature lets you schedule your backup at night. At the defined time, Veeam Agent for Microsoft Windows will wake up the computer and perform a scheduled task. If necessary, you can additionally instruct Veeam Agent for Microsoft Windows to bring the computer back to the standby mode or power off the computer after the backup is finished.

Veeam Agent for Microsoft Windows wakes up the computer by default, unless the power saving settings on the computer prohibit this. If the wake up operation is not possible for some reason, the computer will remain in the standby mode, and the backup operation will not be performed. You can instruct Veeam Agent for Microsoft Windows to resume missed backup in such situations. To learn more, see [Missed Backup Schedule](scheduled_backup_missed.md).

|  |
| --- |
| ![Computer Wake Up from Sleep](images/icon_important.webp) IMPORTANT |
| [For tablets] If at the moment of backup a computer is in the Connected Standby power saving mode, Veeam Agent for Microsoft Windows will fail to wake it up due to limitations set by the OS itself. |


