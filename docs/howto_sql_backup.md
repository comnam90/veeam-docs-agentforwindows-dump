---
title: "How to Back Up Microsoft SQL Server"
product: "agentforwindows"
doc_type: "userguide"
source_url: "https://helpcenter.veeam.com/docs/agentforwindows/userguide/howto_sql_backup.html"
last_updated: "2/4/2025"
product_version: "13.0.1.1009"
---

# How to Back Up Microsoft SQL Server


To protect Microsoft SQL Server, you can use the Server edition of Veeam Agent for Microsoft Windows. You can set up the Veeam Agent backup job to create transactionally consistent backups of Microsoft SQL Server and periodically back up database transaction logs. If Microsoft SQL Server fails, you can restore the Microsoft SQL Server from the necessary restore point of the backup. If you use Veeam Agent for Microsoft Windows with Veeam Backup & Replication, you can also use Veeam Explorer for Microsoft SQL Server to apply transaction logs and get databases on the Microsoft SQL Server to the necessary state between backups.

This scenario describes how to set up the backup job to create transactionally consistent backups of Microsoft SQL Server. You will:

1. [Install a license for the Server edition of Veeam Agent for Microsoft Windows](#lic).
2. [Configure the backup job to create backups of the Microsoft SQL Server in the network shared folder](#backup).

To install a Veeam Agent for Microsoft Windows license:

1. Double-click the Veeam Agent for Microsoft Windows icon in the system tray, or right-click the Veeam Agent for Microsoft Windows icon in the system tray and select Control Panel.
2. From the main menu, select About.
3. In the Version section, click the Update license to get additional features link.

![How to Back Up Microsoft SQL Server](images/ep_update_notifications_free.webp "Update License to Get Additional Features")

1. In the License section, click Install and browse for the LIC file that supports the Server edition of Veeam Agent for Microsoft Windows.

![How to Back Up Microsoft SQL Server](images/howto_cc_license_install.png "Install License")

1. In the Edition section, make sure that the Server option is selected or select this option.

![How to Back Up Microsoft SQL Server](images/howto_cc_all_editions_available_server.webp "Check that Server Edition Is Enabled")Sus

1. Click Close.

To configure the backup job:

1. Double-click the Veeam Agent for Microsoft Windows icon in the system tray, or right-click the Veeam Agent for Microsoft Windows icon in the system tray and select Configure backup.

![How to Back Up Microsoft SQL Server](images/howto_configure_backup_launch.webp "Start Backup Configuration Using System Tray")

1. At the Name step of the wizard, specify the job name and description. Click Next.

![How to Back Up Microsoft SQL Server](images/ep_backup_job_name.webp "Set Backup Job Name and Description")

1. At the Backup Mode step of the wizard, select what data you want to back up: entire computer, specific computer volumes or individual folders with files. Click Next.

![How to Back Up Microsoft SQL Server](images/howto_sql_volume_backup.webp "Set Backup Job Mode")

1. If you have selected to perform volume-level or file-level backup, select check boxes next to those objects that you want to include in the backup. Click Next.

![How to Back Up Microsoft SQL Server](images/howto_sql_volumes_backup.webp "Select Volumes for Volume-Level Backup Job")

1. At the Destination step of the wizard, select Shared folder. Click Next.

![How to Back Up Microsoft SQL Server](images/howto_sql_destination.webp "Select Destination for the Backup Job")

1. At the Shared Folder step of the wizard, specify settings to connect to the network shared folder in which you want to save backup files. Specify how many restore points you want to retain. Click Next.

![How to Back Up Microsoft SQL Server](images/howto_sql_share.webp "Specify Shared Folder to Backup to")

1. At the Backup Cache step of the wizard, click Next.
2. At the Guest Processing step of the wizard, make sure that the Enable application-aware processing check box is selected. Click Applications.

![How to Back Up Microsoft SQL Server](images/howto_sql_guest_processing.webp "Enable Application-Aware Processing and Display Processing Settings Window")

1. In the Processing Settings window, click the SQL tab. Specify settings for database transaction log processing. Click OK, then click Next.

![How to Back Up Microsoft SQL Server](images/howto_sql_vss_sql.webp "Specify Settings for Database Transaction Log Processing")

1. At the Schedule step of the wizard, specify the day and time when the backup job must be started and configure advanced scheduling settings if necessary.

![How to Back Up Microsoft SQL Server](images/howto_sql_schedule.webp "Schedule Backup Job")

1. Click Apply, then click Finish.


