---
title: "Data Compression"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/compression_deduplication.html"
last_updated: "10/23/2023"
product_version: "13.0.1.1009"
---

# Data Compression


Veeam Agent provides mechanisms of data compression and deduplication. Data compression and deduplication let you decrease traffic going over the network and disk space required for storing backup files.

Data Compression

Data compression decreases the size of created backups but affects duration of the backup procedure. Veeam Agent allows you to select one of the following compression levels:

| Compression Level | Compression Algorithm | Description |
| --- | --- | --- |
| None | No compression | This compression level is recommended if you plan to store backup files on storage devices that support hardware compression and deduplication. |
| Dedupe-friendly | Rle | Optimized compression level for very low CPU usage. You can select this compression level if you want to decrease the load on the CPU of the Veeam Agent computer. |
| Optimal | Lz4 | The default recommended compression level. It provides the best ratio between size of the backup file and time of the backup procedure. |
| High | Zstd 3 | Provides up to 60% additional compression ratio over the Optimal level at the cost of 2x higher CPU usage and 2x slower restore. |
| Extreme | Zstd 9 | Provides the smallest size of the backup file but reduces the backup performance. We recommend that you use the extreme compression level only on Veeam Agent computers with modern multi-core CPUs (6 cores recommended). |

You can change data compression settings for existing backup jobs. New settings will not have any effect on previously created backup files in the backup chain. They will be applied to new backup files created after the settings were changed.

Compression settings are changed on the fly. You do not need to create a new full backup to use new settings — Veeam Agent will automatically apply the new compression level to newly created backup files.

Storage Optimization

Depending on the type of storage you select as a backup target, Veeam Agent uses data blocks of different size, which optimizes the size of a backup file and job performance. You can choose one of the following storage optimization options:

* 4 MB — select this option for backup jobs that can produce very large full backup files (larger than 16 TB). With this option selected, Veeam Agent will use data block size of 4096 KB.

* 1 MB (default) — select this option for backup to SAN, DAS or local storage. With this option selected, Veeam Agent will use data block size of 1024 KB.

The SAN identifies larger blocks of data and therefore can process large amounts of data at a time. This option provides the fastest backup job performance.

* 512 KB — select this option for backup to NAS and onsite backup. With this option selected, Veeam Agent will use data block size of 512 KB. This option reduces the size of an incremental backup file because of reduced data block sizes.
* 256 KB — select this option if you plan to use WAN for offsite backup. With this option selected, Veeam Agent will use data block size of 256 KB. This results in the smallest size of backup files, allowing you to reduce the amount of traffic over WAN.

Various factors can affect the overall size of the backup files. As a result, the smallest file size may not always be achieved.

|  |
| --- |
| NOTE |
| If you change storage optimization settings, the new settings will be applied only after an active full backup is created. Veeam Agent will use the new block size for the active full backup and subsequent backup files in the backup chain. For more information on scheduling active full backups, see [Backup Settings](backup_job_advanced_backup.md). |


