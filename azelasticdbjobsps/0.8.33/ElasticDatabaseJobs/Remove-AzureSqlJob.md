---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: F4AE7899-666E-4C76-8022-B586547BF932
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Remove-AzureSqlJob.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Remove-AzureSqlJob.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Remove-AzureSqlJob

## SYNOPSIS
Removes a job and its job run history from the system.

## SYNTAX

```
Remove-AzureSqlJob -JobName <String[]> [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureSqlJob** cmdlet removes a job and its job run history from the system.

Job and job run history deletion takes place asynchronously.
Any active jobs will not be automatically canceled by the system.
If you want to cancel an active job, use the [Stop-AzureSqlJobExecution](./Stop-AzureSqlJobExecution.md) cmdlet.
The job and job execution history will be deleted following the completion of any active job executions of the job.

## EXAMPLES

### Example 1: Remove a job and its job execution history
```
PS C:\>Remove-AzureSqlJob -JobName "MyJob"
```

This command removes the job named MyJob and its job execution history.

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

[Get-AzureSqlJob](./Get-AzureSqlJob.md)

[New-AzureSqlJob](./New-AzureSqlJob.md)

[Set-AzureSqlJob](./Set-AzureSqlJob.md)

[Stop-AzureSqlJobExecution](./Stop-AzureSqlJobExecution.md)

[Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md)
