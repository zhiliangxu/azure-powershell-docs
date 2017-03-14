---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 156DB6F6-BE77-4090-A921-AFE3622F7B63
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Set-AzureSqlJobExecutionPolicy.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Set-AzureSqlJobExecutionPolicy.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Set-AzureSqlJobExecutionPolicy

## SYNOPSIS
Sets a job execution policy.

## SYNTAX

```
Set-AzureSqlJobExecutionPolicy -ExecutionPolicyName <String[]> [-JobExecutionTimeout <TimeSpan>]
 [-InitialRetryInterval <TimeSpan>] [-RetryIntervalBackoffCoefficient <Single>]
 [-MaximumRetryInterval <TimeSpan>] [-MaximumAttempts <Int32>]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureSqlJobExecutionPolicy** cmdlet sets a job execution policy.

## EXAMPLES

### Example 1: Update an existing execution policy
```
PS C:\>Set-AzureSqlJobExecutionPolicy -ExecutionPolicyName myCustomExecutionPolicyName -JobExecutionTimeout ([System.TimeSpan]::FromHours(2))
ExecutionPolicyName             : myCustomExecutionPolicyName
JobExecutionTimeout             : 02:00:00
InitialRetryInterval            : 00:00:01
RetryIntervalBackoffCoefficient : 1
MaximumRetryInterval            : 00:00:30
MaximumAttempts                 : 100
```

This command updates an existing execution policy.

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

### -ExecutionPolicyName
Specifies the execution policy name.

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

### -InitialRetryInterval
Specifies the time interval to use between job tasks following a job task execution failure.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobExecutionTimeout
Specifies the timeout to enforce for overall job time.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumAttempts
Specifies the total number of job task execution retry attempts within a job.

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

### -MaximumRetryInterval
Specifies the maximum time to allow to pass between retry attempts.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetryIntervalBackoffCoefficient
Specifies the coefficient used to calculate the next interval between retries.
The following formula is used: (Initial Retry Interval) * Math.pow((Interval Backoff Coefficient), (Number of Retries) - 2).

```yaml
Type: Single
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

[Get-AzureSqlJobExecutionPolicy](./Get-AzureSqlJobExecutionPolicy.md)

[New-AzureSqlJobExecutionPolicy](./New-AzureSqlJobExecutionPolicy.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
