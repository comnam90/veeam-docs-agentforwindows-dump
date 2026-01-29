---
title: "Pre-Freeze and Post-Thaw Scripts"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/pre_post_scripts.html"
last_updated: "11/21/2025"
product_version: "13.0.1.1009"
---

# Pre-Freeze and Post-Thaw Scripts


If Veeam Agent computer runs applications that do not support Microsoft VSS, you can instruct Veeam Agent for Microsoft Windows to run custom scripts during the backup job session. For example, the pre-freeze script may quiesce the file system and application data to bring the computer OS to a consistent state before Veeam Agent for Microsoft Windows requests the creation of a Microsoft VSS snapshot. After the VSS snapshot is created, the post-thaw script may bring the OS and applications to their initial state.

Veeam Agent for Microsoft Windows supports scripts in the .EXE, .BAT, .CMD and .PS1 formats.

You can use scripts of other formats as well, but we cannot guarantee correct processing of such scripts.

Scripts must be created beforehand. You must specify paths to them in the backup job settings. Scripts must reside on a local drive of the Veeam Agent computer.

When the backup job starts, Veeam Agent for Microsoft Windows executes scripts specified for the job. A script is considered to be executed successfully if "0" is returned.

The default time period for script execution is 10 minutes. If the script fails to execute before the timeout expires, Veeam Agent for Microsoft Windows displays an error message in the job session and error or warning messages issued during script execution.

![Pre-Freeze and Post-Thaw Scripts](images/ep_backup_job_vss_scripts.webp "Pre-Freeze and Post-Thaw Scripts Specified for Backup Job")

Limitations for Pre-Freeze and Post-Thaw Scripts

Veeam Agent for Microsoft Windows has one limitation for pre-freeze and post-thaw scripts: you cannot stop a job when the pre-freeze or post-thaw script is executed. If the script hangs up, Veeam Agent for Microsoft Windows waits for 10 minutes and then continues running the job depending on the script processing mode.

Related Tasks

[Creating Backup Jobs](backup_job_create.md)


