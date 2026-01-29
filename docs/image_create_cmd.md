---
title: "Creating Veeam Recovery Media with Command Line Interface"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/image_create_cmd.html"
last_updated: "11/26/2024"
product_version: "13.0.1.1009"
---

# Creating Veeam Recovery Media with Command Line Interface


In addition to creating the Veeam Recovery Media with the Create Recovery Media wizard, you can use the command line interface to create the recovery image and save it as an ISO file. To create the Veeam Recovery Media, use a command with the following syntax:

|  |
| --- |
| "C:\Program Files\Veeam\Endpoint Backup\Veeam.EndPoint.Manager.exe" /createrecoverymediaiso /f:<location>\<name>.iso |

where:

* <location> — path to the folder in which the recovery image ISO file will be created. All folders that are mentioned in the path must be created in advance. Names of folders in the path must not contain spaces.
* <name> — name of the resulted ISO file. The file name must not contain spaces.

|  |
| --- |
| ![Creating Veeam Recovery Media with Command Line Interface](images/icon_note.webp) NOTE |
| Consider the following:   * When you create the Veeam Recovery Media using the command line interface, Veeam Agent for Microsoft Windows includes in the recovery image storage and network drivers that are currently installed on the Veeam Agent computer, and current network settings of this computer. If you want to include additional drivers or data decryption key in the recovery image, you must create the Veeam Recovery Media using the Create Recovery Media wizard. To learn more, see [Creating Veeam Recovery Media with UI](image_create_ui.md). * If you do not use the /f: option to specify a path to the folder in which to save the resulting ISO file, Veeam Agent for Microsoft Windows will save the ISO file to the C:\Users\%UserProfile%\Documents folder with the VeeamRecoveryMedia\_<machine>.iso name, where <machine> — name of your Veeam Agent computer. * You cannot save the ISO file to a network shared folder using the command line interface. |

You can use the last exit code to verify if the backup job has completed successfully. To check the last exit code, use the %ERRORLEVEL% variable in cmd.exe. Veeam Agent can provide the following exit codes:

* 0 — recovery image successfully created
* 1 — the create recovery image operation failed

Example of Use

The example below creates an ISO file with the VeeamRE name in the E:\Veeam\RecoveryImage folder.

|  |
| --- |
| "C:\Program Files\Veeam\Endpoint Backup\Veeam.EndPoint.Manager.exe" /createrecoverymediaiso /f:E:\Veeam\RecoveryImage\VeeamRE.iso |


