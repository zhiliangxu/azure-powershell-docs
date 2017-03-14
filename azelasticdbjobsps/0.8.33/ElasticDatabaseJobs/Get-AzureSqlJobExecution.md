---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 2F400DA8-52CF-4D84-8AFA-EB2FEFE7DC3E
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJobExecution.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJobExecution.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-AzureSqlJobExecution

## SYNOPSIS
Gets one or multiple job execution containers.

## SYNTAX

### Filter (Default)
```
Get-AzureSqlJobExecution [-ParentJobExecutionId <Guid>] [-JobName <String>] [-ScheduleName <String>]
 [-ContentName <String>] [-TargetId <Guid>] [-JobType <JobType>] [-IncludeInactive] [-IncludeChildren]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### JobExecutionId
```
Get-AzureSqlJobExecution -JobExecutionId <Guid[]> [-IncludeChildren]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlJobExecution** cmdlet gets one or multiple job execution containers.
Each job execution container contains task executions performed to fulfill execution of a job.

## EXAMPLES

### Example 1: Get all active parent job executions across the system
```
PS C:\>Get-AzureSqlJobExecution
JobExecutionId       : e1b85439-14af-453e-a462-04cd17e1d3ec
ParentJobExecutionId :
Lifecycle            : WaitingToRetry
CreatedTime          : 7/10/2015 1:59:06 PM -07:00
StartTime            : 7/10/2015 1:59:08 PM -07:00
EndTime              :
JobName              : MyJob
ContentName          : MyScript
ContentVersionNumber : 1
TargetDescription    : {"CustomCollectionName":"myCustomCollection"}
TargetId             : b525727e-6ed0-44cc-94da-63c543e383d7
CredentialName       : MyCredential
ExecutionPolicyName  : Default execution policy
ResultSetDestination :
```

This command gets all active parent job executions across the system.

### Example 2: Get the specified job execution by ID
```
PS C:\>Get-AzureSqlJobExecution -JobExecutionId e1b85439-14af-453e-a462-04cd17e1d3ec
JobExecutionId       : e1b85439-14af-453e-a462-04cd17e1d3ec
ParentJobExecutionId : Lifecycle            : WaitingToRetry
CreatedTime          : 7/10/2015 1:59:06 PM -07:00
StartTime            : 7/10/2015 1:59:08 PM -07:00
EndTime              :
JobName              : MyJob
ContentName          : MyScript
ContentVersionNumber : 1
TargetDescription    : {"CustomCollectionName":"myCustomCollection"}
TargetId             : b525727e-6ed0-44cc-94da-63c543e383d7
CredentialName       : MyCredential
ExecutionPolicyName  : Default execution policy
ResultSetDestination :
```

This command gets the specified job execution by ID.

### Example 3: Get all active job executions across the specified job name
```
PS C:\>Get-AzureSqlJobExecution -JobName "MyJob"
JobExecutionId       : e1b85439-14af-453e-a462-04cd17e1d3ec
ParentJobExecutionId :
Lifecycle            : WaitingToRetry
CreatedTime          : 7/10/2015 1:59:06 PM -07:00
StartTime            : 7/10/2015 1:59:08 PM -07:00
EndTime              :
JobName              : MyJob
ContentName          : MyScript
ContentVersionNumber : 1
TargetDescription    : {"CustomCollectionName":"myCustomCollection"}
TargetId             : b525727e-6ed0-44cc-94da-63c543e383d7
CredentialName       : MyCredential
ExecutionPolicyName  : Default execution policy
ResultSetDestination :
```

This command gets all active job executions across the specified job name.

### Example 4: Get all active job executions across the specified job name, including child jobs
```
PS C:\>Get-AzureSqlJobExecution -JobName "CreateTableJob" -IncludeChildren
JobExecutionId       : a664a3d1-0dba-4516-ad53-bf26115bfaa0
ParentJobExecutionId :
Lifecycle            : WaitingForChildJobExecutions
CreatedTime          : 7/10/2015 3:17:26 PM -07:00
StartTime            : 7/10/2015 3:17:27 PM -07:00
EndTime              :
JobName              : CreateTableJob
ContentName          : CreateMyTestTable
ContentVersionNumber : 1
TargetDescription    : {"CustomCollectionName":"myCustomCollection"}
TargetId             : b525727e-6ed0-44cc-94da-63c543e383d7
CredentialName       : MyCredential
ExecutionPolicyName  : Default execution policy
ResultSetDestination :

JobExecutionId       : c0d1433f-ca50-4cc4-81e2-80bcdf5ad258
ParentJobExecutionId : a664a3d1-0dba-4516-ad53-bf26115bfaa0
Lifecycle            : InProgress
CreatedTime          : 7/10/2015 3:17:31 PM -07:00
StartTime            : 7/10/2015 3:17:32 PM -07:00
EndTime              :
JobName              : CreateTableJob
ContentName          : CreateMyTestTable
ContentVersionNumber : 1
TargetDescription    : {"ServerName":"myServer.database.windows.net","DatabaseName":"myDatabase"}
TargetId             : 0f31294a-f42f-414d-a00f-4df43e9bd493
CredentialName       : MyCredential
ExecutionPolicyName  : Default execution policy
ResultSetDestination :
```

This command gets all active job executions across the specified job name, including the child job executions.

### Example 5: Get all active parent job executions across the system executing specific content
```
PS C:\>Get-AzureSqlJobExecution -ContentName MyScript
JobExecutionId       : e1b85439-14af-453e-a462-04cd17e1d3ec
ParentJobExecutionId :
Lifecycle            : WaitingToRetry
CreatedTime          : 7/10/2015 1:59:06 PM -07:00
StartTime            : 7/10/2015 1:59:08 PM -07:00
EndTime              :
JobName              : MyJob
ContentName          : MyScript
ContentVersionNumber : 1
TargetDescription    : {"CustomCollectionName":"myCustomCollection"}
TargetId             : b525727e-6ed0-44cc-94da-63c543e383d7
CredentialName       : MyCredential
ExecutionPolicyName  : Default execution policy
ResultSetDestination :
```

This command gets all active parent job executions across the system executing the specified content.

## PARAMETERS

### -AzureSqlJobConnection
Specifies the connection state object for the job.
You can get the connection state object through the N[ew-AzureSqlJobConnection](./New-AzureSqlJobConnection.md) cmdlet.
If you do not specify this parameter, the connection state is used from a prior call to the [Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md) cmdlet.

```yaml
Type: AzureSqlJobConnection
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContentName
Specifies the content name to use for filtering across all job executions.

```yaml
Type: String
Parameter Sets: Filter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeChildren
Indicates whether children job runs are included within the job output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeInactive
Indicates whether job runs are included within the job output.

```yaml
Type: SwitchParameter
Parameter Sets: Filter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobExecutionId
Specifies the ID of the job execution to obtain.

```yaml
Type: Guid[]
Parameter Sets: JobExecutionId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobName
Specifies the job name to use for filtering across all job executions.

```yaml
Type: String
Parameter Sets: Filter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobType
Specifies that this cmdlet filters the job executions by User, Cleanup, Heartbeat or TelemetryCollection job types.
All jobs created through [New-AzureSqlJob](./New-AzureSqlJob.md) are of type User.
System jobs are of type Cleanup, Heartbeat or TelemetryCollection.

```yaml
Type: JobType
Parameter Sets: Filter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentJobExecutionId
Specifies the parent job execution ID to use for filtering across all job executions.

```yaml
Type: Guid
Parameter Sets: Filter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleName
Specifies the schedule name to use for filtering across all job executions.

```yaml
Type: String
Parameter Sets: Filter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetId
Specifies the target ID to use for filtering across all job executions.

```yaml
Type: Guid
Parameter Sets: Filter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-AzureSqlJobExecution](./Start-AzureSqlJobExecution.md)

[Stop-AzureSqlJobExecution](./Stop-AzureSqlJobExecution.md)

[Wait-AzureSqlJobExecution](./Wait-AzureSqlJobExecution.md)
