---
title: "Application-Aware Processing"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/application_aware_processing.html"
last_updated: "10/28/2025"
product_version: "13.0.1.1009"
---

# Application-Aware Processing


To use application-aware processing, you must have the latest updates installed on the Veeam Agent computer OS. To learn more, see [Supported Applications](guest_processing.md#apps).

To create transactionally consistent backups of servers that run VSS-aware applications such as Microsoft SQL Server, Microsoft SharePoint, Microsoft Exchange or Oracle, you must enable application-aware processing for the backup job.

Application-aware processing is Veeam's proprietary technology based on Microsoft VSS. Microsoft VSS is responsible for quiescing applications and creating a consistent view of application data on the OS of the Veeam Agent computer. Use of Microsoft VSS ensures that there are no unfinished database transactions or incomplete application files when Veeam Agent requests the creation of a Microsoft VSS snapshot and starts copying backed-up data to the target location. For more information about Microsoft VSS, see [Microsoft documentation](https://learn.microsoft.com/en-us/windows-server/storage/file-server/volume-shadow-copy-service).

In the Server edition of Veeam Agent, the type of the VSS snapshot depends on application-aware processing settings:

* If application-aware processing is disabled for the backup job, Veeam Agent requests a copy-only VSS snapshot.
* If application-aware processing is enabled and the Perform copy only option is selected, Veeam Agent requests a copy-only VSS snapshot.
* If application-aware processing is enabled and the Process transaction logs with this job option is selected, Veeam Agent requests a full VSS snapshot.

To learn more, see [Specify Application-Aware Processing Settings](backup_job_vss_general.md).

![Application-Aware Processing](images/ep_backup_job_vss_general.webp "Application-Aware Processing")

|  |
| --- |
| ![Application-Aware Processing](images/icon_important.webp) IMPORTANT |
| If your computer OS runs an application that does not support Microsoft VSS (there is no VSS writer for this particular type of application, for example, MySQL), Veeam Agent for Microsoft Windows will not be able to utilize Microsoft VSS and application-aware processing for this application. To process such applications, you can use pre-freeze and post-thaw scripts. For more information, see [Pre-Freeze and Post-Thaw Scripts](pre_post_scripts.md). |


