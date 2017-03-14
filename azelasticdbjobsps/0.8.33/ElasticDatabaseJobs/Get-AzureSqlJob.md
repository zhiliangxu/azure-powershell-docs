---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: BE8DBC20-68D1-4F97-8B24-3C21AB2E2B32
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJob.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJob.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-AzureSqlJob

## SYNOPSIS
Gets one or multiple job definitions.

## SYNTAX

### Filter (Default)
```
Get-AzureSqlJob [-ScheduleName <String>] [[-AzureSqlJobConnection] <AzureSqlJobConnection>]
 [<CommonParameters>]
```

### JobName
```
Get-AzureSqlJob -JobName <String[]> [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlJob** cmdlet gets one or multiple job definitions.

## EXAMPLES

### Example 1: Get a specified job by name
```
PS C:\>Get-AzureSqlJob -JobName MyJob
JobName              : MyJob
ContentName          : MyScript
ContentVersionNumber :
TargetDescription    : {"CustomCollectionName":"myCustomCollection"}
TargetId             : b525727e-6ed0-44cc-94da-63c543e383d7
CredentialName       : MyCredential
ExecutionPolicyName  : Default execution policy
ResultSetDestination :
```

This command gets the specified job by name.

### Example 2: Get all jobs that have defined triggers over the provided schedule
```
PS C:\>Get-AzureSqlJob -ScheduleName MyOneMinuteIntervalSchedule
JobName              : MyJob
ContentName          : MyScript
ContentVersionNumber :
TargetDescription    : {"CustomCollectionName":"myCustomCollection"}
TargetId             : b525727e-6ed0-44cc-94da-63c543e383d7
CredentialName       : MyCredential
ExecutionPolicyName  : Default execution policy
ResultSetDestination :
```

This command gets all jobs that have defined triggers over the provided schedule.

### Example 3: Get all jobs defined in the system
```
PS C:\>Get-AzureSqlJob
JobName              : System Job: telemetry
ContentName          :
ContentVersionNumber :
TargetDescription    :
TargetId             :
CredentialName       :
ExecutionPolicyName  : System execution policy: telemetry
ResultSetDestination :

JobName              : System Job: heartbeat
ContentName          :
ContentVersionNumber :
TargetDescription    :
TargetId             :
CredentialName       :
ExecutionPolicyName  : System execution policy: heartbeat
ResultSetDestination :

JobName              : System Job: cleanup
ContentName          :
ContentVersionNumber :
TargetDescription    :
TargetId             :
CredentialName       :
ExecutionPolicyName  : System execution policy: cleanup
ResultSetDestination :

JobName              : MyJob
ContentName          : MyScript
ContentVersionNumber :
TargetDescription    : {"CustomCollectionName":"myCustomCollection"}
TargetId             : b525727e-6ed0-44cc-94da-63c543e383d7
CredentialName       : MyCredential
ExecutionPolicyName  : Default execution policy
ResultSetDestination :

JobName              : MyResultsJob
ContentName          : MyScript
ContentVersionNumber :
TargetDescription    : {"CustomCollectionName":"myCustomCollection"}
TargetId             : b525727e-6ed0-44cc-94da-63c543e383d7
CredentialName       : MyCredential
ExecutionPolicyName  : Default execution policy
ResultSetDestination : Microsoft.Azure.SqlDatabase.Jobs.Client.ResultSetDestination

JobName              : MyResultsJobAcrossShardMap
ContentName          : MyScript
ContentVersionNumber :
TargetDescription    : {"ShardMapName":"myShardMap","ShardMapManagerServerName":"myShardMapManagerServer.database.windows.net","ShardMapManagerDatabaseName":
                       "myShardMapManagerDatabase"}
TargetId             : 1afd9326-1277-4344-832f-8170d0375ff7
CredentialName       : MyCredential
ExecutionPolicyName  : Default execution policy
ResultSetDestination : Microsoft.Azure.SqlDatabase.Jobs.Client.ResultSetDestination
```

This command gets all jobs defined in the system.

## PARAMETERS

### -AzureSqlJobConnection
Specifies the connection state object for the job.
You can get the connection state object through the [New-AzureSqlJobConnection](./New-AzureSqlJobConnection.md) cmdlet.
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

### -JobName
Specifies the name of the job.

```yaml
Type: String[]
Parameter Sets: JobName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleName
Specifies the name of the schedule as a filter when getting jobs.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureSqlJob](./New-AzureSqlJob.md)

[Remove-AzureSqlJob](./Remove-AzureSqlJob.md)

[Set-AzureSqlJob](./Set-AzureSqlJob.md)
