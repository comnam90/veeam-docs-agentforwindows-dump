---
title: "Resetting CBT"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/cbt_reset.html"
last_updated: "9/18/2025"
product_version: "13.0.1.1009"
---

# Resetting CBT


In some cases, it may be required to reset CBT data collected by the Veeam CBT driver. For example, after a volume was changed in a non-Windows OS.

To reset CBT, run the command line interface with administrative privileges and use one of the following commands:

* To reset CBT for all volumes of the Veeam Agent computer, use a command with the following syntax:

|  |
| --- |
| "C:\Program Files\Veeam\Endpoint Backup\Veeam.EndPoint.Manager.exe" RESETCBT all |

* To reset CBT for a specific volume, use a command with the following syntax:

|  |
| --- |
| "C:\Program Files\Veeam\Endpoint Backup\Veeam.EndPoint.Manager.exe" RESETCBT %volumeMountPoint% |

or

|  |
| --- |
| "C:\Program Files\Veeam\Endpoint Backup\Veeam.EndPoint.Manager.exe" RESETCBT %volumeUUID% |

where:

* %volumeMountPoint% — mount point of the volume, for example: C:\.
* %volumeUUID% — ID of the volume, for example: \\?\Volume{1214be80-1165-41e5-8244-8fbf79d85c31}.

After CBT reset, during the next backup job session, Veeam Agent for Microsoft Windows will create incremental backup. The backup job session will require greater time, because Veeam Agent for Microsoft Windows will need to read all data from the backed-up volumes.


