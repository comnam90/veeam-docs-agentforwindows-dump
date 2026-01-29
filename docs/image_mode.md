---
title: "Defining Veeam Recovery Media Operation Mode"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/image_mode.html"
last_updated: "10/28/2025"
product_version: "13.0.1.1009"
---

# Defining Veeam Recovery Media Operation Mode


By default, you must manually specify the backup file location and restore point during the restore from a Veeam Recovery Media. If you know in advance that you will need to restore data from a specific backup stored in the Veeam backup repository, you can change the Veeam Recovery Media operation mode and predefine restore settings. In this case, restore will be performed automatically.

To predefine the restore settings, do the following:

1. Create a Veeam Recovery Media with the [UI](image_create_ui.md) or [command line interface](image_create_cmd.md).
2. Open the disk or removable storage device with the created recovery image or mount the ISO file.
3. Specify the following settings in the BMRAnswerFile.xml file:

|  |
| --- |
| NOTE |
| If you work with an ISO file, you will need an ISO editor to save changes to the BMRAnswerFile.xml file. |

1. Change the recovery media operation mode to unattended. To do this, set the Prompt value for the OPERATION\_MODE property.
2. Specify the Veeam backup server that manages the backup repository where the required backup file resides. To do this, set a value for the VBR\_SERVER property. You can specify IP address and port in 172.168.0.1:10005 format or hostname in machine.domain.name:port format.
3. Define whether you want to see the Veeam backup server certificate validation warnings before you start the restore process. To do this, set a value for the VBR\_SERVER\_VALIDATION property:

* Set the PromptWarnings value if you want to review the warnings and validate the certificate manually or cancel the restore process.
* Set the IgnoreWarnings value if you want to skip the warnings and perform restore using the existing certificate.

1. [Optional] Specify the recovery token to connect to the Veeam backup server. To do this, set a value for the RECOVERY\_TOKEN property. To learn how to create a recovery token, see [Creating Recovery Token](integration_recovery_token.md).

If you do not specify a recovery token in the XML file or specify an expired recovery token, you will be prompted to enter a valid recovery token during the restore process.

|  |
| --- |
| NOTE |
| By default, a recovery token is valid for 24 hours. To create a recovery token with a longer validity period, use the Add-VBRComputerRecoveryToken cmdlet. To learn more, see the [Add-VBRComputerRecoveryToken](https://helpcenter.veeam.com/docs/vbr/powershell/add-vbrcomputerrecoverytoken.html?ver=13) section in the Veeam PowerShell Reference. |

1. [Optional] Specify a restore point to select during the restore process. To do this, set a value for the RESTORE\_POINT property. You can specify the first or latest restore point. If you do not specify a restore point in the XML file, you will be prompted to select it during the restore process.

1. Save the changes to the XML file.

With these settings, you will be able to launch the restore process in the unattended mode. To learn more, see [Restoring from Veeam Recovery Media in the Unattended Mode](image_boot_unattended.md).

If you want to switch the Veeam Recovery Media back to the manual mode, set the Manual value for the OPERATION\_MODE property in the BMRAnswerFile.xml file and save the changes.

|  |
| --- |
| <?xml version="1.0" encoding="utf-8"?> |


