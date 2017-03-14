---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 2882003C-8B0B-4007-8A40-D19BB6731CE2
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Wait-AzureSqlJobExecution.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Wait-AzureSqlJobExecution.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Wait-AzureSqlJobExecution

## SYNOPSIS
Waits for the provided job execution to complete.

## SYNTAX

### JobExecutionId
```
Wait-AzureSqlJobExecution [-TimeoutSeconds <Int32>] [-Any] -JobExecutionId <Guid[]>
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### JobExecutionInfo
```
Wait-AzureSqlJobExecution [-TimeoutSeconds <Int32>] [-Any] -InputObject <JobExecutionInfo[]>
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### JobName
```
Wait-AzureSqlJobExecution [-TimeoutSeconds <Int32>] -JobName <String[]>
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Wait-AzureSqlJobExecution** cmdlet waits for the provided job execution to complete.

## EXAMPLES

### Example 1: Wait for a specific job execute to complete
```
PS C:\>Wait-AzureSqlJobExecution -JobExecutionId 07981e74-5235-48a6-b24e-b5beb16a149a
```

This command waits for the provided job execution to complete.

### Example 2: Wait for a specific job execution to complete after a time duration
```
PS C:\>Wait-AzureSqlJobExecution -JobExecutionId 07981e74-5235-48a6-b24e-b5beb16a149a -TimeoutSeconds 60
```

This command waits for the provided job execution to complete, timing out after 60 seconds.

## PARAMETERS

### -Any
Indicates that the cmdlet will wait for only one provided job to complete rather than all.

```yaml
Type: SwitchParameter
Parameter Sets: JobExecutionId, JobExecutionInfo
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -InputObject
Specifies JobExecutionInfo object(s) on which to wait.
JobExecutionInfo objects can be obtained using the [Get-AzureSqlJobExecution](./Get-AzureSqlJobExecution.md) cmdlet.

```yaml
Type: JobExecutionInfo[]
Parameter Sets: JobExecutionInfo
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -JobName
Specifies the name of the job.

```yaml
Type: String[]
Parameter Sets: JobName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TimeoutSeconds
Specifies the time duration before this cmdlet times out.

```yaml
Type: Int32
Parameter Sets: (All)
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

[Get-AzureSqlJobExecution](./Get-AzureSqlJobExecution.md)

[Start-AzureSqlJobExecution](./Start-AzureSqlJobExecution.md)

[Stop-AzureSqlJobExecution](./Stop-AzureSqlJobExecution.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
