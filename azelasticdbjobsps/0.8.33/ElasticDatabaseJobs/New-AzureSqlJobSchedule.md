---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: A6FB51F0-2A72-4D99-A400-8FBB4E82B3CA
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/New-AzureSqlJobSchedule.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/New-AzureSqlJobSchedule.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# New-AzureSqlJobSchedule

## SYNOPSIS
Creates a time based specification for a job run to take place either on a reoccurring interval or at a single time.

## SYNTAX

### OneTime
```
New-AzureSqlJobSchedule -ScheduleName <String> [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 [-OneTime] [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### MinuteInterval
```
New-AzureSqlJobSchedule -ScheduleName <String> [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 -MinuteInterval <Int32> [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### HourInterval
```
New-AzureSqlJobSchedule -ScheduleName <String> [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 -HourInterval <Int32> [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### DayInterval
```
New-AzureSqlJobSchedule -ScheduleName <String> [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 -DayInterval <Int32> [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### WeekInterval
```
New-AzureSqlJobSchedule -ScheduleName <String> [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 -WeekInterval <Int32> [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### MonthInterval
```
New-AzureSqlJobSchedule -ScheduleName <String> [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 -MonthInterval <Int32> [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureSqlJobSchedule** cmdlet creates a time based specification for a job run to take place either on a reoccurring interval or at a single time.

Jobs can be set to run according to a schedule through the creation of a trigger through the [New-AzureSqlJobTrigger](./New-AzureSqlJobTrigger.md) cmdlet.

## EXAMPLES

### Example 1: Create a schedule with a time trigger
```
PS C:\>New-AzureSqlJobSchedule -ScheduleName "MyOneMinuteIntervalSchedule" -StartTime (Get-Date).ToUniversalTime() -MinuteInterval 1
ScheduleName                  Interval                      StartTime                     EndTime
------------                  --------                      ---------                     -------
MyOneMinuteIntervalSchedule   Minutes: 1                    7/4/2015 7:00:00 AM -07:00    12/31/9999 3:59:59 PM -08:00
```

This command creates a schedule to be triggered every one minute.

### Example 2: Create a schedule with a trigger of one hour
```
PS C:\>New-AzureSqlJobSchedule -ScheduleName "MyOneHourIntervalSchedule" -MinuteInterval 1
ScheduleName                  Interval                      StartTime                     EndTime
------------                  --------                      ---------                     -------
MyOneHourIntervalSchedule     Hours: 1                      7/4/2015 7:00:00 AM -07:00    12/31/9999 3:59:59 PM -08:00
```

This command creates a schedule to be triggered every one hour.

### Example 3: Create a schedule with a trigger of one day
```
PS C:\>New-AzureSqlJobSchedule -ScheduleName "MyOneHourIntervalSchedule" -DayInterval 1
ScheduleName                  Interval                      StartTime                     EndTime
------------                  --------                      ---------                     -------
MyOneDayIntervalSchedule      Days: 1                       7/4/2015 7:00:00 AM -07:00    12/31/9999 3:59:59 PM -08:00
```

This command creates a schedule to be triggered every one day.

### Example 4: Create a schedule that is triggered at a specific time
```
PS C:\>New-AzureSqlJobSchedule -ScheduleName "MyOneTimeSchedule" -StartTime (New-Object -TypeName System.DateTime -ArgumentList (2015, 07, 15, 07, 00, 00)).ToUniversalTime() -OneTime
ScheduleName                  Interval                      StartTime                     EndTime
------------                  --------                      ---------                     -------
MyOneTimeSchedule             OneTime                       7/15/2015 7:00:00 AM -07:00   12/31/9999 3:59:59 PM -08:00
```

This command creates a schedule to be triggered once at the provided start time.

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
Specifies the number of hours to allow to elapse between jobs.

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
Specifies the number of minutes to allow to elapse between jobs.

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
Specifies the number of months to allow to elapse between jobs.

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
Indicates that the schedule will only run once on the specified start time.

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
Specifies the number of weeks to allow to elapse between jobs.

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

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
