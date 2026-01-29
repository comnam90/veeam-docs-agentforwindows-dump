---
title: "Stopping Backup Job"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/backup_job_stop.html"
last_updated: "3/21/2024"
product_version: "13.0.1.1009"
---

# Stopping Backup Job


You can stop the running backup job before the job session completes, for example, if the backup process is about to take long, and you do not want the job to produce workload on the production environment during business hours.

When you stop a backup job, the job session will finish immediately. Veeam Agent will not produce a new restore point during the backup job session.

To stop a backup job:

1. Double-click the Veeam Agent for Microsoft Windows icon in the system tray, or right-click the Veeam Agent for Microsoft Windows icon in the system tray and select Control Panel.
2. In the main menu, do either of the following:

* Hover over the name of the running backup job that you want to stop and select Stop job.
* Hover over the name of the running backup job that you want to stop and select Open. Then click Cancel in the job statistics window.

![Stopping Backup Job](images/agent_job_stop.webp "Stop Backup Job")


