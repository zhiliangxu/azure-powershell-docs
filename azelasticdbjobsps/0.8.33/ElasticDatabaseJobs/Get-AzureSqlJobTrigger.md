---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 3BC3E6BB-A0E5-4702-8D65-E9271B7CA9E0
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJobTrigger.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJobTrigger.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-AzureSqlJobTrigger

## SYNOPSIS
Gets one or multiple job triggers.

## SYNTAX

```
Get-AzureSqlJobTrigger [-JobName <String>] [-ScheduleName <String>]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlJobTrigger** cmdlet gets one or multiple job triggers.
A job trigger is a mapping of job to schedules.
In accordance to the schedule definition, job runs are triggered for each job or schedule mapping.

## EXAMPLES

### Example 1: Get all job triggers using the specified job name
```
PS C:\>Get-AzureSqlJobTrigger -JobName "MyJob"
JobName                                              ScheduleName                                                                                     Enabled
-------                                              ------------                                                                                     -------
MyJob                                                MyOneMinuteIntervalSchedule                                                                         True
```

This command gets all job triggers under the job named MyJob.

### Example 2: Get all job triggers using a specified job schedule
```
PS C:\>Get-AzureSqlJobTrigger -ScheduleName "MyOneMinuteIntervalSchedule"
JobName                                              ScheduleName                                                                                     Enabled
-------                                              ------------                                                                                     -------
MyJob                                                MyOneMinuteIntervalSchedule                                                                         True
```

This command gets all job triggers using the schedule named MyOneMinuteIntervalSchedule.

### Example 3: Get all triggers defined in the system
```
PS C:\>Get-AzureSqlJobTrigger
JobName                                              ScheduleName                                                                                     Enabled
-------                                              ------------                                                                                     -------
System Job: telemetry                                System schedule: telemetry                                                                          True
System Job: heartbeat                                System schedule: heartbeat                                                                          True
System Job: cleanup                                  System schedule: cleanup                                                                            True
MyJob                                                MyOneMinuteIntervalSchedule                                                                         True
```

This command gets all triggers defined in the system.

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
Specifies the job name.
If you specify this parameter, this cmdlet returns triggers that are bounded to the provided job name.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleName
Specifies the schedule name.
If you specify this parameter, this cmdlet returns triggers that are bounded to the provided schedule name.

```yaml
Type: String
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

[New-AzureSqlJobTrigger](./New-AzureSqlJobTrigger.md)

[Remove-AzureSqlJobTrigger](./Remove-AzureSqlJobTrigger.md)

[Set-AzureSqlJobTrigger](./Set-AzureSqlJobTrigger.md)

[Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
