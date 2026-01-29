---
title: "Veeam Recovery Media"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/recovery_media.html"
last_updated: "10/9/2025"
product_version: "13.0.1.1009"
---

# Veeam Recovery Media


Veeam Agent for Microsoft Windows lets you create a Veeam Recovery Media — a recovery image of your computer.

The recovery image is a "copy" of your OS with the limited functionality — it contains all data required to run Microsoft Windows Recovery Environment (Windows RE), and provides an alternative way to boot your computer. If the OS installed on the computer fails to start for some reason, you can boot the Windows RE from the recovery image. After booting, you can do the following:

* You can use Veeam Agent for Microsoft Windows and Microsoft Windows tools to diagnose problems and fix errors on your computer.
* You can restore data from a backup to your computer. For this scenario, you must have a backup created with Veeam Agent for Microsoft Windows or system image created with Microsoft Windows.

The recovery image can be helpful if one of the following errors occur:

* The OS on the computer fails to start.
* The computer is blocked with malware and you cannot get access to your data.
* You want to perform bare metal restore from the backup on the computer without the OS and other software installed.
* You want to restore the system volume of the computer and so on.

You can create a recovery image on the following kinds of media:

* Removable storage devices such as USB drives or SD cards
* ISO images on local or external computer drives

The restore from the Veeam Recovery Media can operate in the manual or unattended mode.

When you boot from the Veeam Recovery Media, you can use the Veeam Agent for Microsoft Windows recovery environment to fix the OS system errors on your computer or restore data from the backup. Veeam Agent for Microsoft Windows offers a set of tools for the computer system image and data recovery:

* Bare Metal Recovery — the Veeam Agent for Microsoft Windows wizard to recover data on the original computer or a new computer.
* Windows Recovery Environment — a built-in Microsoft Windows tool to recover the computer system image.
* Tools — Veeam Agent for Microsoft Windows and Microsoft Windows utilities for advanced computer administration.

Limitations for Veeam Recovery Media

* You cannot restore dynamic volumes using a Veeam Recovery Media. To restore dynamic volumes, you can recover data from the volume-level backup on a working computer system. To learn more, see [Restoring Volumes](volume_restore.md).
* The Veeam Recovery Media is based on the Microsoft Windows RE. Due to Microsoft limitations, Microsoft Windows RE automatically reboots after 72 hours of continuous use. All data that has not been saved before reboot will be lost.

Related Tasks

* [Creating Veeam Recovery Media](image_create.md)
* [Restoring from Veeam Recovery Media](image_boot.md)


