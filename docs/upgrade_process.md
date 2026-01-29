---
title: "Upgrading Veeam Agent for Microsoft Windows"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/upgrade_process.html"
last_updated: "11/10/2025"
product_version: "13.0.1.1009"
---

# Upgrading Veeam Agent for Microsoft Windows


For Veeam Agent for Microsoft Windows, upgrade to newer versions is supported. You can start the upgrade process from the Veeam Agent control panel when the new version becomes available. To learn how to check for product updates, see [Checking for New Product Versions and Updates](settings_updates.md).

|  |
| --- |
| IMPORTANT |
| Upgrade to version 13.0.1 is supported for Veeam Agent for Microsoft Windows version 6.3.1 and later.  If your computer is running an earlier version of Veeam Agent, you must first [upgrade to the latest available 6.3 version](https://helpcenter.veeam.com/archive/agentforwindows/60/userguide/upgrade_process.html). |

Before You Begin

Before you upgrade Veeam Agent for Microsoft Windows to version 13.0.1, check the following prerequisites:

* Make sure that the Veeam Agent computer meets the [system requirements](system_requirements.md).
* Make sure that there are no running jobs.

If you have any running jobs, let them complete successfully before you start the upgrade. Disable any periodic jobs temporarily to prevent them from starting during the upgrade. If the protected computer runs VSS-aware applications and backup of database logs (Microsoft SQL Server transaction logs or Oracle archived logs) is enabled in the backup job for the computer, disable this backup job too.

During the upgrade process, configuration and backup files that were created with the previous version of Veeam Agent are not impacted in any way.

Upgrade Process

|  |
| --- |
| ![Upgrading Veeam Agent for Microsoft Windows](images/icon_note.webp) NOTE |
| Consider the following:   * In some cases, upgrade to the new version of Veeam Agent may require computer reboot. * You can also download the Veeam Agent setup archive from [this Veeam webpage](https://www.veeam.com/downloads.html). Save the downloaded archive on the computer where you plan to install the new version of the product and double-click the setup archive to start the upgrade. |

To upgrade Veeam Agent for Microsoft Windows:

1. Double-click the Veeam Agent icon in the system tray, or right-click the Veeam Agent icon in the system tray and select Control Panel.
2. Open the About tab.
3. If the new version of Veeam Agent is available, click Download.
4. When the download is complete, click Install to run the setup archive.
5. To upgrade Veeam Agent, you must accept the terms of the license agreements. Read the license agreements and click Accept and Update.
6. To preserve settings from the previous product installation, click Yes in the opened window.

1. After the installation is complete, click Finish.

Unattended Upgrade

You can upgrade Veeam Agent to a newer version in the unattended mode using the same command that is used for unattended installation. To learn more, see [Installing Veeam Agent for Microsoft Windows in Unattended Mode](installation_unattended.md).


