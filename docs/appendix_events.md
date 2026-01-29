---
title: "Appendix A. Veeam Agent Events"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/appendix_events.html"
last_updated: "11/1/2024"
product_version: "13.0.1.1009"
---

# Appendix A. Veeam Agent Events


Veeam Agent for Microsoft Windows logs its events to event logs on the computer where the product is installed. Events can be used for monitoring the backup job activity and alerting about the backup status.

The table below lists all events logged by Veeam Agent for Microsoft Windows.

| Event ID | Name | Description | Event Log | Source | Severity |
| --- | --- | --- | --- | --- | --- |
| 110 | Backup Job Started | Veeam Agent <jobname> has been started [by user <username>]. | Veeam Agent | Veeam Agent | Information |
| 115 | Backup Job Resumed | Backup Job <jobname> has been resumed. | Veeam Agent | Veeam Agent | Information |
| 190 | Backup Job Finished | Veeam Agent <jobname> finished with <job status>. | Veeam Agent | Veeam Agent | Information  Warning  Error |
| 191 | Backup Job Retry | Veeam Agent <jobname> finished with Error and will be retried. | Veeam Agent | Veeam Agent | Warning |
| 195 | Synchronization Finished | Synchronization for cached restore points finished with <job status>. <Additional information about synchronized restore points>. | Veeam Agent | Veeam Agent | Information  Warning  Error |
| 196 | Destination Changed | Backup job destination has been switched from <target> to Backup Cache. | Veeam Agent | Veeam Agent | Information |
| 197 | Backup Cache Deleted | Backup cache has been deleted by <username>. | Veeam Agent | Veeam Agent | Information |
| 1074 | Computer shut down2 | The process C:\Windows\system32\Shutdown.exe (<jobname>) has initiated the shutdown of computer <jobname> on behalf of user NT AUTHORITY\SYSTEM for the following reason: No title for this reason could be found Reason Code: 0x800000ff Shutdown Type: shutdown Comment: Computer was shut down after successful backup by Veeam Agent for Microsoft Windows. | System | User32 | Information |
| 4010 | License Installed | License key for Veeam Agent for Windows has been installed. | Veeam Agent | Veeam Agent | Information |
| 4020 | License Expiring | License key for Veeam Agent is about to expire in <N> days. | Veeam Agent | Veeam Agent | Warning |
| 4030 | License Expired | License key for Veeam Agent has expired. | Veeam Agent | Veeam Agent | Error |
| 4025 | License in Grace Period | Your license has expired and needs to be renewed. Veeam Agent will continue to operate for the duration of the grace period. | Veeam Agent | Veeam Agent | Error |
| 4040 | License Support Expiring | Support contract for Veeam Agent is about to expire in <N> days. | Veeam Agent | Veeam Agent | Warning |
| 4050 | License Support Expired | Support contract for Veeam Agent has expired. Contact Veeam sales representative to renew your support contract. | Veeam Agent | Veeam Agent | Error |
| 4060 | Product Edition Changed | Veeam Agent for Windows edition has been changed from <previousedition> to <currentedition>. | Veeam Agent | Veeam Agent | Information |
| 10010 | Restore Point Created | '<computername>' restore point has been created. | Veeam Agent | Veeam Agent | Information |
| 10050 | Restore Point Removed | Restore point for '<computername>' has been removed according to the configured retention policy. | Veeam Agent | Veeam Agent | Information |
| 23010 | Backup Job Created | The <jobname> backup job has been created. | Veeam Agent | Veeam Agent | Information |
| 23050 | Backup Job Modified | The <jobname> backup job has been modified. | Veeam Agent | Veeam Agent | Information |
| 23090 | Backup Job Deleted | EndpointBackup <jobname> has been deleted. | Veeam Agent | Veeam Agent | Information |
| 23051 | Agent Modified | Veeam Agent option <optionname> has been changed.3 | Veeam Agent | Veeam Agent | Information |
| 23502 | Agent Upgraded | Veeam Agent has been successfully upgraded. | Veeam Agent | Veeam Agent | Information |
| Failed to upgrade Veeam Agent. | Error |
| 23110 | Backup Mode Changed | The <jobname> backup mode has been changed from <previousmode> to <currentmode>. | Veeam Agent | Veeam Agent | Information |
| 23120 | Backup Source Updated | The <jobname> backup job source objects have been updated. | Veeam Agent | Veeam Agent | Information |
| 26010 | USB Device Ejected | Target USB device has been successfully ejected. | Veeam Agent | Veeam Agent | Information |
| 178 | Managed mode Enabled | Veeam Agent has been switched to managed mode.4 | Veeam Agent | Veeam Agent | Information |
| 179 | Managed mode Disabled | Veeam Agent has been switched to free mode.4 | Veeam Agent | Veeam Agent | Information |
| 201 | Read-only mode Enabled | Read only UI access has been enabled.4 | Veeam Agent | Veeam Agent | Information |
| 202 | Read-only mode Disabled | Read only UI access has been disabled.4 | Veeam Agent | Veeam Agent | Information |

1 Job details contain information about the reason for completing the job with the Warning or Error status.

2 The event is triggered if the user has instructed Veeam Agent for Microsoft Windows to shut down the computer on successful backup.

3 The event is triggered if the user has changed any Veeam Agent for Microsoft Windows setting other than backup job settings.

4 The event can be triggered if Veeam Agent for Microsoft Windows is managed by a Remote Monitoring and Management platform, for example, LabTech.


