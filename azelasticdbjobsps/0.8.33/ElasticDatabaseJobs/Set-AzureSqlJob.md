---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 74A798B5-44A6-437B-82EB-E957DC7D8366
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Set-AzureSqlJob.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Set-AzureSqlJob.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Set-AzureSqlJob

## SYNOPSIS
Updates a job definition.

## SYNTAX

### TargetIdUpdateResultSetDestination (Default)
```
Set-AzureSqlJob -JobName <String[]> [-CredentialName <String>] [-ContentName <String>] [-TargetId <Guid>]
 [-ExecutionPolicyName <String>] [-ResultSetDestinationServerName <String>]
 [-ResultSetDestinationDatabaseName <String>] [-ResultSetDestinationCredentialName <String>]
 [-ResultSetDestinationSchemaName <String>] [-ResultSetDestinationTableName <String>] [-LiteralServerName]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### TargetIdRemoveesultSetDestination
```
Set-AzureSqlJob -JobName <String[]> [-CredentialName <String>] [-ContentName <String>] [-TargetId <Guid>]
 [-ExecutionPolicyName <String>] [-RemoveResultSetDestination]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureSqlJob** cmdlet updates a job definition.

## EXAMPLES

### Example 1: Add a result set collection to a specified job
```
PS C:\>Set-AzureSqlDatabaseJob -JobName "MyResultsJob" -ResultSetDestinationServerName "MyResultsServerName.database.contoso.net" -ResultSetDestinationDatabaseName "MyResultsDatabaseName" -ResultSetDestinationCredentialName "MyResultsCredential" -ResultSetDestinationSchemaName "DBO" -ResultSetDestinationTableName "MyResultsTable"
JobName              : MyResultsJob
ContentName          : MyScript
ContentVersionNumber :
TargetDescription    : {"CustomCollectionName":"MyCustomCollection"}
TargetId             : b525727e-6ed0-44cc-94da-63c543e383d7
CredentialName       : MyCredential
ExecutionPolicyName  : Default execution policy
ResultSetDestination : Microsoft.Azure.SqlDatabase.Jobs.Client.ResultSetDestination
```

This command adds a result set collection to the job named MyResultsJob.

### Example 2: Remove a result set collection from a specified job
```
PS C:\>Set-AzureSqlDatabaseJob -JobName "MyResultsJob" -RemoveResultSetDestination
JobName              : MyResultsJob
ContentName          : MyScript
ContentVersionNumber :
TargetDescription    : {"CustomCollectionName":"myCustomCollection"}
TargetId             : b525727e-6ed0-44cc-94da-63c543e383d7
CredentialName       : MyCredential
ExecutionPolicyName  : Default execution policy
ResultSetDestination :
```

This command removes a result set collection from the provided job.

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

### -ContentName
Indicates that this cmdlet updates the content that is run or applied during the job.

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

### -CredentialName
Specifies the credentials to use when connecting to target databases.

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

### -ExecutionPolicyName
Indicates that this cmdlet updates the execution policy to be used during job runs.

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

### -RemoveResultSetDestination
Indicates that this cmdlet removes the use of a result set destination from a job.

```yaml
Type: SwitchParameter
Parameter Sets: TargetIdRemoveesultSetDestination
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultSetDestinationCredentialName
Specifies the name of the credential to use for the database connection used for insertion of the first result set obtained during job execution.

```yaml
Type: String
Parameter Sets: TargetIdUpdateResultSetDestination
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultSetDestinationDatabaseName
Specifies the database name to use for insertion of the first result set obtained during jobs.

```yaml
Type: String
Parameter Sets: TargetIdUpdateResultSetDestination
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultSetDestinationSchemaName
Specifies the database schema name to use for insertion of the first result set obtained during job runs.

```yaml
Type: String
Parameter Sets: TargetIdUpdateResultSetDestination
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultSetDestinationServerName
Specifies the database server name to use for insertion of the first result set obtained during job runs.

```yaml
Type: String
Parameter Sets: TargetIdUpdateResultSetDestination
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultSetDestinationTableName
Specifies the database table name to use for insertion of the first result set obtained during a job run.
If the table does not exist during job execution, the system will automatically create it using a schema matching the result set.

```yaml
Type: String
Parameter Sets: TargetIdUpdateResultSetDestination
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetId
Specifies the target ID.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralServerName
{{Fill LiteralServerName Description}}

```yaml
Type: SwitchParameter
Parameter Sets: TargetIdUpdateResultSetDestination
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

[Get-AzureSqlJob](./Get-AzureSqlJob.md)

[New-AzureSqlJob](./New-AzureSqlJob.md)

[Remove-AzureSqlJob](./Remove-AzureSqlJob.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
