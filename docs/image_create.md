---
title: "Creating Veeam Recovery Media"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/image_create.html"
last_updated: "4/22/2025"
product_version: "13.0.1.1009"
---

# Creating Veeam Recovery Media


You can create a Veeam Recovery Media — a recovery media for your computer. The Veeam Recovery Media contains all data that is required to run the Microsoft Windows RE. If your computer stops working or the hard disk fails, you can boot from the Veeam Recovery Media, instead of booting from the hard drive. After booting, you can use Veeam and Microsoft tools to fix errors, recover the system image of your computer and your data.

|  |
| --- |
| ![Creating Veeam Recovery Media](images/icon_note.webp) NOTE |
| In some cases, Windows Recovery Environment components may be missing on the system, and Veeam Agent for Microsoft Windows will not find them during the Veeam Recovery Media creation. In such case you will be prompted to do one of the following:   * Insert the Windows Installation Media so that Veeam Agent for Microsoft Windows can load the necessary components from it. * Download and install Windows Assessment and Deployment Kit (MS ADK).   Keep in mind that the Veeam Recovery Media created with MS ADK components will not contain the following tools:   * Windows Recovery Environment * Memory Diagnostic * Startup Repair |

Before you create a Veeam Recovery Media, [check prerequisites](image_create_before.md). Then use the [Create Recovery Media wizard](image_create_ui.md) or [command line interface](image_create_cmd.md) to create a Veeam Recovery Media. If you want to automate restore from the Veeam Recovery Media, [predefine restore settings](image_mode.md).

|  |
| --- |
| TIP |
| If you want to boot from the created Veeam Recovery Media automatically without pressing a key on the boot screen, you can disable the "Press any key to boot..." prompt with a registry value. To learn more, see [this Veeam KB article](https://www.veeam.com/kb4689). |

In This Section

* [Creating Veeam Recovery Media with UI](image_create_ui.md)
* [Creating Veeam Recovery Media with Command Line Interface](image_create_cmd.md)
* [Defining Veeam Recovery Media Operation Mode](image_mode.md)

Related Topics

[Veeam Recovery Media](recovery_media.md)


