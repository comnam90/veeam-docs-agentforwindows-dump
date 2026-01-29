---
title: "Database Log Backup Job"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/sql_backup_job.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# Database Log Backup Job


To back up database logs (Microsoft SQL Server transaction logs and Oracle archived logs), you must specify advanced settings for transaction log backup in the Veeam Agent backup job settings. The resulting job will comprise two jobs:

* Parent backup job — the backup job that creates a volume-level or file-level backup. The backup job becomes the parent job after you enable database log backup options at the Guest Processing step of the New Backup Job wizard.
* Child job — a transaction log backup job. Veeam Agent for Microsoft Windows automatically creates the child job if transaction log backup is enabled for the backup job. Session data of the transaction log backup job is stored in the Veeam Agent for Microsoft Windows database and displayed in the Veeam Agent control panel. To learn more, see [Transaction Log Backup Statistics](monitoring_restore_points_db.md).

The parent job runs in a regular manner — it starts by schedule or is started manually by the user. The transaction log backup job is triggered by the parent backup job. This sequence ensures that the restore point is present when it comes to transaction log replay.

|  |
| --- |
| ![Database Log Backup Job](images/icon_note.webp) NOTE |
| Veeam Agent for Microsoft Windows supports one transaction log backup job per Veeam Agent computer. If you plan to configure several backup jobs using Veeam Agent for Microsoft Windows, you can enable database log backup settings for one job only. |

Sessions of Transaction Log Backup Jobs

The transaction log backup job runs permanently in the background, shipping transaction logs to the backup location at a specific time interval (by default, every 15 minutes). A sequence of time intervals between sessions of the parent backup job makes up a session of the transaction log backup job.

The transaction log backup session starts and stops in the following way:

* The initial session starts when the parent backup job schedule is enabled. After that, the session starts with every new session of the parent backup job.
* The session ends before the next session of the parent backup job or when this parent backup job is disabled.


