---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: F0568B6B-E86F-445E-AAD6-6E9E984ED981
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJobScriptBatchExecution.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJobScriptBatchExecution.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-AzureSqlJobScriptBatchExecution

## SYNOPSIS
Gets one or multiple results of a script batch execution within a task execution.

## SYNTAX

```
Get-AzureSqlJobScriptBatchExecution -JobTaskExecutionId <Guid[]>
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlJobScriptBatchExecution** cmdlet gets one or multiple results of a script batch run within a task execution.
Each task run for script execution also create one or multiple script batch executions.

## EXAMPLES

### Example 1: Get the results of execution from each batch within a script
```
PS C:\>Get-AzureSqlJobScriptBatchExecution -JobTaskExecutionId fd3be7b5-f860-4068-93b1-4a3b2d7c3ef3
ScriptBatchNumber : 0
Lifecycle         : Succeeded
StartTime         : 7/10/2015 3:32:07 PM -07:00
EndTime           : 7/10/2015 3:32:08 PM -07:00
Message           :
```

This command gets the results of the specified job task execution from each batch within a script.
The job task execution ID must match a job task of type ScriptExecution.

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

### -JobTaskExecutionId
Specifies the job task execution ID to use for lookup of script batch executions.

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
