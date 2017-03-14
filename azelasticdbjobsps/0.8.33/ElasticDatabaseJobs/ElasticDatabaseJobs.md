---
Module Name: ElasticDatabaseJobs
Module Guid: D48CF693-4125-4D2D-8790-1514F44CE325
Download Help Link: http://go.microsoft.com/fwlink/?linkid=390762
Help Version: 2.0.0.0
Locale: en-US
ms.assetid: E1AF2634-2E0A-4B64-925C-A0895168F939
uid: ElasticDatabaseJobs
updated_at: 11/02/2016 10:11 AM
ms.date: 11/02/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/ElasticDatabaseJobs.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/ElasticDatabaseJobs.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/64699f630725ddbaf121a7306fb3e87efd8687b9
ms.topic: conceptual
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# ElasticDatabaseJobs Module

This topic displays help topics for the Azure Elastic Database Jobs Cmdlets.

Elastic Database Jobs (preview) enables you to reliably run a Transact-SQL (T-SQL) script or apply a data-tier application package (DACPAC) across a group of Azure SQL databases.
By using these cmdlets, you can easily perform administrative operations such as schema changes, credentials management, reference data updates, performance data collection, and tenant (customer) telemetry collection.

This module includes preliminary documentation that is subject to change.
Blank topics are included as placeholders.


## About Windows PowerShell

Windows PowerShell is a task-based command-line shell and scripting language designed for system administration.
Unlike most shells, which accept and return text, Windows PowerShell is built on top of the .NET Framework, and accepts and returns .NET Framework objects.

Windows PowerShell introduces the concept of a cmdlet (pronounced "command-let"), a simple, single-function command-line tool built into the shell.
Cmdlets have the following naming convention: a verb and noun separated by a dash (-), such as **Get-Help**, **Get-Process**, and **Start-Service**.
Windows PowerShell includes more than one hundred basic core cmdlets.

For more information about, or for the syntax of, any of the cmdlets, use the `Get-Help <cmdlet name>` command, where `<cmdlet name>` is the name of the cmdlet that you want to research.
For more detailed information, you can run any of the following commands:

* `Get-Help <cmdlet name> -Detailed`
* `Get-Help <cmdlet name> -Examples`
* `Get-Help <cmdlet name> -Full`

For more information about Windows PowerShell, see the [Getting Started with Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell).



## ElasticDatabaseJobs Cmdlets
### [Add-AzureSqlJobChildTarget](./Add-AzureSqlJobChildTarget.md)
Associates a target to a custom collection target.


### [Get-AzureSqlJobContentDefinition](./Get-AzureSqlJobContentDefinition.md)
Gets one or multiple content definitions that are run or applied across entities within a job target.


### [Get-AzureSqlJobContent](./Get-AzureSqlJobContent.md)
Gets content containers to run or apply across entities in a target.


### [Get-AzureSqlJobCredential](./Get-AzureSqlJobCredential.md)
Gets one or multiple database credentials to use when connecting to databases for execution of jobs.


### [Get-AzureSqlJobExecutionPolicy](./Get-AzureSqlJobExecutionPolicy.md)
Gets one or multiple job execution policies.


### [Get-AzureSqlJobExecution](./Get-AzureSqlJobExecution.md)
Gets one or multiple job execution containers.


### [Get-AzureSqlJobSchedule](./Get-AzureSqlJobSchedule.md)
Gets one or multiple job schedules.


### [Get-AzureSqlJobScriptBatchExecution](./Get-AzureSqlJobScriptBatchExecution.md)
Gets one or multiple results of a script batch execution within a task execution.


### [Get-AzureSqlJobTarget](./Get-AzureSqlJobTarget.md)
Gets one or multiple containers of databases that can be used as a target for job runs.


### [Get-AzureSqlJobTaskExecution](./Get-AzureSqlJobTaskExecution.md)
Gets one or multiple task run results.


### [Get-AzureSqlJobTrigger](./Get-AzureSqlJobTrigger.md)
Gets one or multiple job triggers.


### [Get-AzureSqlJob](./Get-AzureSqlJob.md)
Gets one or multiple job definitions.


### [New-AzureSqlJobConnection](./New-AzureSqlJobConnection.md)
Creates a connection to an Elastic Database jobs database.


### [New-AzureSqlJobContent](./New-AzureSqlJobContent.md)
Creates content that can be run or applied across entities within a job target.


### [New-AzureSqlJobCredential](./New-AzureSqlJobCredential.md)
Creates database credentials when connecting to databases to run jobs.


### [New-AzureSqlJobExecutionPolicy](./New-AzureSqlJobExecutionPolicy.md)
Creates an execution policy which controls job execution timeouts.


### [New-AzureSqlJobSchedule](./New-AzureSqlJobSchedule.md)
Creates a time based specification for a job run to take place either on a reoccurring interval or at a single time.


### [New-AzureSqlJobTarget](./New-AzureSqlJobTarget.md)
Creates a set of databases that can be used as a target for jobs.


### [New-AzureSqlJobTrigger](./New-AzureSqlJobTrigger.md)
Creates a mapping of job to schedules.


### [New-AzureSqlJob](./New-AzureSqlJob.md)
Creates a job definition to be used for subsequent job runs.


### [Remove-AzureSqlJobChildTarget](./Remove-AzureSqlJobChildTarget.md)
Removes a child target from another target.


### [Remove-AzureSqlJobTrigger](./Remove-AzureSqlJobTrigger.md)
Removes a job trigger to stop future jobs runs according to a schedule.


### [Remove-AzureSqlJob](./Remove-AzureSqlJob.md)
Removes a job and its job run history from the system.


### [Set-AzureSqlJobContentDefinition](./Set-AzureSqlJobContentDefinition.md)
Sets the T-SQL script or DACPAC URI definition of content.


### [Set-AzureSqlJobCredential](./Set-AzureSqlJobCredential.md)
Updates the username or password within an existing credential.


### [Set-AzureSqlJobExecutionPolicy](./Set-AzureSqlJobExecutionPolicy.md)
Sets a job execution policy.


### [Set-AzureSqlJobSchedule](./Set-AzureSqlJobSchedule.md)
Updates a schedule.


### [Set-AzureSqlJobTarget](./Set-AzureSqlJobTarget.md)
Updates a job target definition.


### [Set-AzureSqlJobTrigger](./Set-AzureSqlJobTrigger.md)
Sets a job trigger.


### [Set-AzureSqlJob](./Set-AzureSqlJob.md)
Updates a job definition.


### [Start-AzureSqlJobExecution](./Start-AzureSqlJobExecution.md)
Starts a job execution.


### [Stop-AzureSqlJobExecution](./Stop-AzureSqlJobExecution.md)
Stops a job execution.


### [Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md)
Sets the Azure PowerShell session context to use the provided connection to the Elastic Database Jobs control database.


### [Wait-AzureSqlJobExecution](./Wait-AzureSqlJobExecution.md)
Waits for the provided job execution to complete.
