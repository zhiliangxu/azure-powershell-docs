---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 568BFFAB-1C4A-4C63-A299-983E6F6EFD23
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Set-AzureSqlJobSchedule.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Set-AzureSqlJobSchedule.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Set-AzureSqlJobSchedule

## SYNOPSIS
Updates a schedule.

## SYNTAX

### StartEndTimeOnly (Default)
```
Set-AzureSqlJobSchedule -ScheduleName <String[]> [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### OneTime
```
Set-AzureSqlJobSchedule -ScheduleName <String[]> [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 [-OneTime] [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### MinuteInterval
```
Set-AzureSqlJobSchedule -ScheduleName <String[]> [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 -MinuteInterval <Int32> [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### HourInterval
```
Set-AzureSqlJobSchedule -ScheduleName <String[]> [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 -HourInterval <Int32> [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### DayInterval
```
Set-AzureSqlJobSchedule -ScheduleName <String[]> [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 -DayInterval <Int32> [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### WeekInterval
```
Set-AzureSqlJobSchedule -ScheduleName <String[]> [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 -WeekInterval <Int32> [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### MonthInterval
```
Set-AzureSqlJobSchedule -ScheduleName <String[]> [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 -MonthInterval <Int32> [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureSqlJobSchedule** cmdlet updates a schedule.

## EXAMPLES

### Example 1: Update a schedule to use a different interval
```
PS C:\>Set-AzureSqlDatabaseJobSchedule -ScheduleName "MySchedule" -MinuteInterval 10
ScheduleName                            Interval                                StartTime                              EndTime                               
------------                            --------                                ---------                              -------                               
MySchedule                              Minutes: 10                             7/10/2015 3:48:46 PM -07:00            12/31/9999 3:59:59 PM -08:00
```

This command updates the schedule named MySchedule to use a different interval.

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

### -DayInterval
Specifies the number of days to allow to elapse between jobs.

```yaml
Type: Int32
Parameter Sets: DayInterval
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndTime
Specifies the ending time for the schedule to be active.

```yaml
Type: DateTimeOffset
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HourInterval
Specifies the number of hours that elapse between jobs.

```yaml
Type: Int32
Parameter Sets: HourInterval
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinuteInterval
Specifies the number of minutes that elapse between jobs.

```yaml
Type: Int32
Parameter Sets: MinuteInterval
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonthInterval
Specifies the number of months that elapse between jobs.

```yaml
Type: Int32
Parameter Sets: MonthInterval
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OneTime
Indicates that the schedule will only execute once on the specified start time.

```yaml
Type: SwitchParameter
Parameter Sets: OneTime
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleName
Specifies an array that contains the name of the schedule.

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

### -StartTime
Specifies the starting time for the schedule to be active.

```yaml
Type: DateTimeOffset
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeekInterval
Specifies the number of weeks that elapse between jobs.

```yaml
Type: Int32
Parameter Sets: WeekInterval
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

[Get-AzureSqlJobSchedule](./Get-AzureSqlJobSchedule.md)

[New-AzureSqlJobSchedule](./New-AzureSqlJobSchedule.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
