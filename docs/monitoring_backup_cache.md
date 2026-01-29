---
title: "Viewing Status of Restore Points in Backup Cache"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/monitoring_backup_cache.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Viewing Status of Restore Points in Backup Cache


If the backup cache is enabled for the job, you can monitor status of restore points in the backup cache. Veeam Agent for Microsoft Windows displays the restore point status through the icon on a bar in the chart.

The icon can be in one of the following states:

| Icon | Description | Backup state |
| --- | --- | --- |
| ![Viewing Status of Restore Points in Backup Cache](images/cache_icon_check.webp "Backup File Is Saved on Target Storage") | Check mark over the icon. | The backup file created within the backup session is saved on the target storage. |
| — | No icon. | The backup file created within the backup session is saved in the backup cache. |
| ![Viewing Status of Restore Points in Backup Cache](images/cache_icon_sync.webp "Backup File Is Being Uploaded from Backup Cache to Target Storage") | Sync sign over the icon. | The backup file is being uploaded from the backup cache to the target storage. |
| ![Viewing Status of Restore Points in Backup Cache](images/cache_icon_corrupt.webp "Backup File Was Not Uploaded to Target Storage and Has Been Deleted") | Error sign over the icon. | The backup file was not uploaded to the target storage or has been deleted from the backup cache. |

|  |
| --- |
| ![Viewing Status of Restore Points in Backup Cache](images/icon_tip.webp) TIP |
| You can also monitor the backup cache activity and view detailed statistics on the restore point upload process. To learn more, see [Monitoring Backup Cache Activity](backup_cache_view_log.md). |

![Viewing Status of Restore Points in Backup Cache](images/ep_reporting_cache.webp "Statistics in Control Panel")


