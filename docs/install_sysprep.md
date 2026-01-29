---
title: "Using Sysprep and Veeam Agent for Microsoft Windows"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/install_sysprep.html"
last_updated: "2/23/2024"
product_version: "13.0.1.1009"
---

# Using Sysprep and Veeam Agent for Microsoft Windows


You can pre-install Veeam Agent in a custom Microsoft Windows system image that will be used for deployment on different computers. To do this, you should perform a set of configuration steps in the reference Microsoft Windows system installation that will be included in a deployment image.

To configure a custom Microsoft Windows system image with Veeam Agent:

1. Install Veeam Agent in a Microsoft Windows system image. To learn more, see [Installing Veeam Agent for Microsoft Windows](installation_process.md).
2. Configure the backup job in the way you want it to work on computers with pre-installed Veeam Agent. To learn more, see [Creating Backup Jobs](backup_job_create.md).

|  |
| --- |
| ![Using Sysprep and Veeam Agent for Microsoft Windows](images/icon_note.webp) NOTE |
| It is advised to configure the backup job for the entire computer backup. In case of volume-level backup, it may be necessary to reconfigure the backup job after Microsoft Windows is deployed to the target computer and include the necessary volumes in the backup once again. This may happen if volumes' GUIDs were changed at the stage of Microsoft Windows generalization with Sysprep. |

1. Create a registry value: HKEY\_LOCAL\_MACHINE\SOFTWARE\Veeam\Veeam Endpoint Backup\SysprepMode (DWORD)=1.

This registry value is used to regenerate the job ID when Veeam Agent starts for the first time on the new computer. If you do not create the registry value, the backup job may fail as soon as it is started on the new computer.

1. Run the Sysprep tool in the Generalize mode to remove any system-specific data. If you need to run the Sysprep tool in the Audit mode, do not forget to re-create the registry value afterwards.
2. Deploy the image on the necessary computers in any convenient way. To learn more about deployment of Microsoft Windows system to new computers, see [Microsoft documentation](https://technet.microsoft.com/en-us/library/dd349343.aspx).

When you deploy the created image on the computer, Veeam Agent will re-generate internal IDs of the backup jobs. As a result, the backup job will be fully functional.

|  |
| --- |
| ![Using Sysprep and Veeam Agent for Microsoft Windows](images/icon_note.webp) NOTE |
| After Veeam Agent for Microsoft Windows starts on the new computer for the first time, the registry value is changed to 0 so that the job ID is not changed during subsequent starts of Veeam Agent for Microsoft Windows. |


