---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 0E2D8FAD-FAB9-46BF-81BB-5631C0EE2006
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Start-AzureSqlJobExecution.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Start-AzureSqlJobExecution.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Start-AzureSqlJobExecution

## SYNOPSIS
Starts a job execution.

## SYNTAX

```
Start-AzureSqlJobExecution -JobName <String[]> [[-AzureSqlJobConnection] <AzureSqlJobConnection>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureSqlJobExecution** cmdlet starts a job execution.

## EXAMPLES

### Example 1: Start a job execution using a specified job name
```
PS C:\>Start-AzureSqlJobExecution -JobName "MyJob"
JobExecutionId       : 736de27d-186f-42ae-8a4c-e5a77c683ccd
ParentJobExecutionId :
Lifecycle            : Created
CreatedTime          : 7/10/2015 2:15:32 PM -07:00
StartTime            :
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

This command starts a job execution using the job named MyJob.

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

[Get-AzureSqlJobExecution](./Get-AzureSqlJobExecution.md)

[Stop-AzureSqlJobExecution](./Stop-AzureSqlJobExecution.md)

[Wait-AzureSqlJobExecution](./Wait-AzureSqlJobExecution.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
