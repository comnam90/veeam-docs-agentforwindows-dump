---
title: "Installing Veeam Agent for Microsoft Windows in Unattended Mode"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/installation_unattended.html"
last_updated: "11/10/2025"
product_version: "13.0.1.1009"
---

# Installing Veeam Agent for Microsoft Windows in Unattended Mode


You can install Veeam Agent for Microsoft Windows in the unattended mode using the command line interface. The unattended installation mode does not require user interaction — the installation runs automatically in the background, and you do not have to respond to the installation wizard prompts. You can use the unattended installation mode to automate the Veeam Agent installation process in large-scale environments.

Prerequisite Software

During the product installation, Veeam Agent for Microsoft Windows automatically sets up the following required prerequisite components:

* SQLite database engine
* Veeam OpenSSL3 FIPS Provider
* ASP.NET Core Runtime
* .NET Desktop Runtime
* [For Microsoft Windows Server 2012 R2] Microsoft Visual C ++ 2015-2022 Redistributable

In some cases, installation of prerequisite software requires computer reboot. This can happen, for example, if you have an earlier version of a prerequisite component installed on the computer and during the installation process this component is used by third-party software.

In this situation, unattended setup will install Veeam Agent for Microsoft Windows but will not start the Veeam Agent for Microsoft Windows service. After you reboot the computer, the Veeam Agent for Microsoft Windows service will be started and Veeam Agent for Microsoft Windows will be fully functioning.

Installation

To install Veeam Agent for Microsoft Windows version 13.0.1, use a command with the following syntax:

|  |
| --- |
| <path\_to\_exe> /silent /accepteula /acceptthirdpartylicenses /acceptlicensingpolicy /acceptrequiredsoftware |

where <path\_to\_exe> — path to the Veeam Agent for Microsoft Windows installation file.

Veeam Agent for Microsoft Windows uses the following codes to report about the installation results:

* 1000 — Veeam Agent for Microsoft Windows has been successfully installed.
* 1001 — prerequisite components required for Veeam Agent for Microsoft Windows have been installed on the machine. Veeam Agent for Microsoft Windows has not been installed. The machine needs to be rebooted.
* 1002 — Veeam Agent for Microsoft Windows installation has failed.
* 1101 — Veeam Agent for Microsoft Windows has been installed. The machine needs to be rebooted.


