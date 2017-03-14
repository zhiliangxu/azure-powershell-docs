---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 62655A15-5FF6-4172-A050-2DC0081C12D9
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Add-AzureSqlJobChildTarget.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Add-AzureSqlJobChildTarget.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Add-AzureSqlJobChildTarget

## SYNOPSIS
Associates a target to a custom collection target.

## SYNTAX

### TargetId (Default)
```
Add-AzureSqlJobChildTarget [-Exclude] -CustomCollectionName <String> -TargetId <Guid[]>
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### Database
```
Add-AzureSqlJobChildTarget [-Exclude] -CustomCollectionName <String> -ServerName <String[]>
 -DatabaseName <String[]> [-LiteralServerName] [[-AzureSqlJobConnection] <AzureSqlJobConnection>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureSqlJobChildTarget** cmdlet associates a target to a custom collection target.
Jobs that are run targeting custom collections are expanded to target all targets associated within the custom collection at the time this cmdlet is run.

## EXAMPLES

### Example 1: Add a database target to a custom collection as a child target
```
PS C:\>Add-AzureSqlDatabaseJobChildTarget -CustomCollectionName "MyCustomCollection" -ServerName "MyServer.database.contoso.net" -DatabaseName "MyDatabase"
```

This command adds a database target to a custom collection as a child target.
You must first create the database target using the [New-AzureSqlDatabaseJobTarget](./New-AzureSqlDatabaseJobTarget.md) cmdlet.
Database targets can be child targets of multiple custom collections.

### Example 2: Add a custom collection to another custom collection
```
PS C:\>Add-AzureSqlDatabaseJobChildTarget -CustomCollectionName "MyCustomCollection" -TargetId (Get-AzureSqlDatabaseJobTarget -CustomCollectionName "MyOtherCustomCollection").TargetId
```

This command adds a custom collection to another custom collection.

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

### -CustomCollectionName
Specifies the name of the custom collection target to contain the association of the provided database.

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

### -DatabaseName
Specifies the database name of the database target to add as a child target to the specified custom collection.

```yaml
Type: String[]
Parameter Sets: Database
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
Specifies the server name of the database target to add as a child target to the specified custom collection.

```yaml
Type: String[]
Parameter Sets: Database
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetId
Specifies the ID of the target to add into the provided custom collection.

```yaml
Type: Guid[]
Parameter Sets: TargetId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Exclude
{{Fill Exclude Description}}

```yaml
Type: SwitchParameter
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
Parameter Sets: Database
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

[Remove-AzureSqlJobChildTarget](./Remove-AzureSqlJobChildTarget.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
