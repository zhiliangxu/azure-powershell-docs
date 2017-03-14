---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 3AB48694-AB4F-4733-802C-A73AD134E786
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJobTaskExecution.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJobTaskExecution.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-AzureSqlJobTaskExecution

## SYNOPSIS
Gets one or multiple task run results.

## SYNTAX

### JobExecutionId
```
Get-AzureSqlJobTaskExecution -JobExecutionId <Guid[]> [[-AzureSqlJobConnection] <AzureSqlJobConnection>]
 [<CommonParameters>]
```

### JobTaskExecutionId
```
Get-AzureSqlJobTaskExecution -JobTaskExecutionId <Guid[]> [[-AzureSqlJobConnection] <AzureSqlJobConnection>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlJobTaskExecution** cmdlet gets one or multiple task run results.

## EXAMPLES

### Example 1: Get all task executions for the specified job execution ID
```
PS C:\>Get-AzureSqlJobTaskExecution -JobExecutionId 07981e74-5235-48a6-b24e-b5beb16a149a
JobTaskExecutionId : ac618be9-9a9c-4308-9652-42c8420aa9a4
JobTaskType        : ScriptSplit
Lifecycle          : Failed
CreatedTime        : 7/10/2015 2:01:04 PM -07:00
StartTime          : 7/10/2015 2:01:04 PM -07:00
EndTime            : 7/10/2015 2:01:04 PM -07:00
Message            : System.AggregateException: One or more errors occurred. ---> Microsoft.Azure.SqlDatabase.Jobs.Common.UserException: An exception
                     occured while executing command on behalf of the user. See inner exception for details. ---> System.AggregateException: One or more
                     syntax errors occurred. ---> System.InvalidOperationException: 46010: Incorrect syntax near \. (Line 19, Column 16)
```

This command gets all task executions for the provided job execution ID.

### Example 2: Get the specified job execution task
```
PS C:\>Get-AzureSqlJobTaskExecution -JobTaskExecutionId ac618be9-9a9c-4308-9652-42c8420aa9a4
JobTaskExecutionId : ac618be9-9a9c-4308-9652-42c8420aa9a4
JobTaskType        : ScriptSplit
Lifecycle          : Failed
CreatedTime        : 7/10/2015 2:01:04 PM -07:00
StartTime          : 7/10/2015 2:01:04 PM -07:00
EndTime            : 7/10/2015 2:01:04 PM -07:00
Message            : System.AggregateException: One or more errors occurred. ---> Microsoft.Azure.SqlDatabase.Jobs.Common.UserException: An exception
                     occured while executing command on behalf of the user. See inner exception for details. ---> System.AggregateException: One or more
                     syntax errors occurred. ---> System.InvalidOperationException: 46010: Incorrect syntax near \. (Line 19, Column 16)
```

This command gets the specified job execution task.

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

### -JobExecutionId
Specifies the job execution ID.

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

### -JobTaskExecutionId
Specifies the job task execution ID.

```yaml
Type: Guid[]
Parameter Sets: JobTaskExecutionId
Aliases:

Required: True
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

[New-AzureSqlJobConnection](./New-AzureSqlJobConnection.md)

[Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
