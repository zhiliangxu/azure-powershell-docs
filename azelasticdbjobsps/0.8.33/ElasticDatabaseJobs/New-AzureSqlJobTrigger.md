---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: A5D19108-72A8-40E2-AAB9-FBC467CF7808
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/New-AzureSqlJobTrigger.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/New-AzureSqlJobTrigger.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# New-AzureSqlJobTrigger

## SYNOPSIS
Creates a mapping of job to schedules.

## SYNTAX

```
New-AzureSqlJobTrigger -JobName <String> -ScheduleName <String>
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureSqlJobTrigger** cmdlet creates a mapping of job to schedules.
In accordance to the schedule definition, job runs are triggered for each job or schedule mapping.

## EXAMPLES

### Example 1: Create a trigger for a job to run according to a specified schedule
```
PS C:\>New-AzureSqlJobTrigger -JobName "MyJob" -ScheduleName "MyOneMinuteIntervalSchedule"
JobName                                              ScheduleName                                                                                     Enabled
-------                                              ------------                                                                                     -------
MyJob                                                MyOneMinuteIntervalSchedule                                                                         True
```

This command creates a trigger for a job named MyJob to run according to the schedule named MyOneMinuteIntervalSchedule.

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
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleName
Specifies the name of the schedule.

```yaml
Type: String
Parameter Sets: (All)
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

[Get-AzureSqlJobTrigger](./Get-AzureSqlJobTrigger.md)

[Remove-AzureSqlJobTrigger](./Remove-AzureSqlJobTrigger.md)

[Set-AzureSqlJobTrigger](./Set-AzureSqlJobTrigger.md)

[New-AzureSqlJobConnection](./New-AzureSqlJobConnection.md)

[Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md)
