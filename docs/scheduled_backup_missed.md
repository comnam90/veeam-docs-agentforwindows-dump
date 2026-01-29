---
title: "Missed Backup Schedule"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/scheduled_backup_missed.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Missed Backup Schedule


Veeam Agent for Microsoft Windows does not perform scheduled backups if the computer is powered off. To handle situations of short power outage or computer restart, Veeam Agent provides a tolerance window of 15 minutes for scheduled backups.

For example, you have configured the backup job to run daily at 10:00 PM. At 9:55 PM, there is a power outage that lasts for 10 minutes. When the computer is on again at 10:05, Veeam Agent will automatically launch the scheduled job to back up your data.

Additionally, you can instruct Veeam Agent to resume missed daily backup. If the computer is powered off at the time when the scheduled backup job must start, and you power on the computer later, Veeam Agent will not wait for the next scheduled backup. Instead, Veeam Agent will start the backup job right after the computer is powered on to ensure no necessary data is lost because of the missed backup.


