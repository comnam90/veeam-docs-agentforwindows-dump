---
title: "Before You Begin"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/installation_before.html"
last_updated: "11/10/2025"
product_version: "13.0.1.1009"
---

# Before You Begin


Before you start the installation process, check the following prerequisites:

* The computer on which you plan to install Veeam Agent must satisfy system requirements specified in this document. To learn more, see [System Requirements](system_requirements.md).

* Make sure to install all available updates for the operating system on the computer you want to protect. Otherwise, the correct functioning of Veeam Agent is not guaranteed.
* If your computer runs Microsoft Windows 11, make sure that the Smart App Control feature is disabled. Otherwise, it may cause installation issues.

For information about Smart App Control, see [this Microsoft KB article](https://support.microsoft.com/en-us/topic/what-is-smart-app-control-285ea03d-fa88-4d56-882e-6698afdb7003).

* You must run the Veeam Agent setup file under the Administrator account or any user account that has Administrator privileges on the computer where you plan to install the product.
* Veeam Agent for Microsoft Windows requires the following components:

* SQLite database engine
* Veeam OpenSSL3 FIPS Provider
* ASP.NET Core Runtime
* .NET Desktop Runtime
* [For Microsoft Windows Server 2012 R2] Microsoft Visual C ++ 2015-2022 Redistributable

If these components are not pre-installed on the computer, the setup will install them during the product installation process.

* The product program files are placed to the %ProgramFiles%\Veeam\Endpoint Backup folder on the system volume. Make sure that you have enough free space on the system volume to install the product. Veeam Agent requires at least 250 MB.
* [Recommended] If you want to create a recovery image of your computer, make sure that you have enough free disk space in the target location. On average, the size of the created recovery image ranges from 600 to 900 MB.

During the recovery image creation, Veeam Agent formats the removable storage device. If you have important information on the device, create a copy of this data in some other location.


