---
title: "Monitoring Backup State with Tray Agent"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/reporting_tray.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Monitoring Backup State with Tray Agent


The Veeam Agent for Microsoft Windows icon displayed in the system tray lets you monitor the state of your backups and get informed about the computer protection status.

The icon can be in one of the following states:

| Icon | Description | Backup state |
| --- | --- | --- |
| ![Monitoring Backup State with Tray Agent](images/ep_icon_ellipsis.webp "Backup Job Is Not Configured") | Question mark over the icon | The backup job is not configured. |
| ![Monitoring Backup State with Tray Agent](images/ep_icon_noschedule.webp "Backup Job Is Set Up but Not Scheduled") | Veeam Agent for Microsoft Windows icon | The backup job is set up but scheduling settings for the job are not configured. |
| ![Monitoring Backup State with Tray Agent](images/ep_icon_progress.webp "Backup Task Is Being Performed") | Animated icon | The backup task is being performed. To view the backup task progress, hover the mouse over the icon. |
| ![Monitoring Backup State with Tray Agent](images/ep_icon_success.webp "Backup Job Completed") | Clock over the icon | * The backup job has been scheduled; waiting for the first backup job session. * The latest session of the scheduled backup job has completed successfully; waiting for the next backup job session. |
| ![Monitoring Backup State with Tray Agent](images/ep_icon_cache.webp "Backup File Is Being Uploaded from Backup Cache to Target Storage") | Sync sign over the icon | Veeam Agent is uploading backup files from the backup cache to the target storage. |
| ![Monitoring Backup State with Tray Agent](images/ep_icon_cancel.webp "Backup Job Canceled") | Cancel sign over the icon | The latest session of the scheduled backup job has been canceled. |
| ![Monitoring Backup State with Tray Agent](images/ep_icon_error.webp "Backup Job Session Terminated") | Error sign over the icon | An error occurred during the latest backup job session, and the session was terminated. |
| ![Monitoring Backup State with Tray Agent](images/ep_icon_disabled.webp "Scheduled Backup Job Disabled") | Minus sign over the icon | The scheduled backup job is disabled. |
| ![Monitoring Backup State with Tray Agent](images/ep_icon_disconnected.webp "Tray Agent Is Not Connected to Veeam Agent Service") | Grey icon | The tray agent is not connected to the Veeam Agent for Microsoft Windows service. |
| ![Monitoring Backup State with Tray Agent](images/ep_icon_warning.webp "Veeam Agent Issued a Warning") | Warning sign over the icon | * The backup job has completed with a warning, for example, the target location is running low on space. * [If you have selected a removable storage device as a target destination in the backup job settings] The target removable storage device is not connected to the computer. In this case, Veeam Agent also displays a warning on the notifications bar in the control panel. You can attach the target removable storage device to the computer within 10 minutes, and Veeam Agent will automatically start the scheduled backup job. |


