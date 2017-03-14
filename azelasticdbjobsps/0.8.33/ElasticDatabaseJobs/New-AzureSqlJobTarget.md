---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: B19A0CEE-F7C4-4B8D-9C61-EBC67FC81139
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/New-AzureSqlJobTarget.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/New-AzureSqlJobTarget.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# New-AzureSqlJobTarget

## SYNOPSIS
Creates a set of databases that can be used as a target for jobs.

## SYNTAX

### Server
```
New-AzureSqlJobTarget -ServerName <String> -MasterDatabaseCredentialName <String> [-LiteralServerName]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### Database
```
New-AzureSqlJobTarget -ServerName <String> -DatabaseName <String> [-LiteralServerName]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### ShardMap
```
New-AzureSqlJobTarget -ShardMapManagerServerName <String> -ShardMapManagerDatabaseName <String>
 -ShardMapManagerCredentialName <String> -ShardMapName <String> [-LiteralServerName]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### CustomCollection
```
New-AzureSqlJobTarget -CustomCollectionName <String> [[-AzureSqlJobConnection] <AzureSqlJobConnection>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureSqlJobTarget** cmdlet creates a set of databases that can be used as a target for jobs.
Targets can be created in the form of either custom collections, Elastic Scale shard maps or databases.

## EXAMPLES

### Example 1: Create a database target
```
PS C:\>New-AzureSqlJobTarget -ServerName "MyServer.database.contoso.net" -DatabaseName "MyDatabase"
TargetDescription : {"ServerName":"myServer.database.windows.net","DatabaseName":"myDatabase"}
ServerName        : myServer.database.windows.net
DatabaseName      : myDatabase
TargetId          : caab9f96-e34a-4c51-9df9-feb33f5cdb50

TargetType        : Database
```

This command creates a database target using the database server named MyServer.database.contoso.net and database named MyDatabase.

### Example 2: Create a custom collection
```
PS C:\>New-AzureSqlJobTarget -CustomCollectionName "MyCustomCollection"    
TargetDescription             CustomCollectionName          TargetId                                         TargetType
-----------------             --------------------          --------                                         ----------
{"CustomCollectionName":"m... MyCustomCollection            b525727e-6ed0-44cc-94da-63...              CustomCollection
```

This command creates a custom collection.
After a custom collection is created, database targets can be added as child targets using the [Add-AzureSqlJobChildTarget](./Add-AzureSqlJobChildTarget.md) cmdlet.

### Example 3: Create an Elastic Scale shared map target
```
PS C:\>New-AzureSqlJobTarget -ShardMapManagerServerName "MyShardMapManagerServer.database.contoso.net" -ShardMapManagerDatabaseName "MyShardMapManagerDatabase" -ShardMapManagerCredentialName "MyShardMapCredentials" -ShardMapName "MyShardMap"
TargetDescription               : {"ShardMapName":"MyShardMap","ShardMapManagerServerName":"MyShardMapManagerServer.dat
                                  abase.windows.net","ShardMapManagerDatabaseName":"MyShardMapManagerDatabase"}
ShardMapName                    : MyShardMap
ShardMapManagerServerName       : myShardMapManagerServer.database.windows.net
ShardMapManagerDatabaseName     : myShardMapManagerDatabase
ShardMapManagerDatabaseTargetId : 9eb3ee50-e4b2-4feb-b2f7-3ee1cd7f7997
ShardMapManagerCredentialName   : MyShardMapCredentials
TargetId                        : 1afd9326-1277-4344-832f-8170d0375ff7
TargetType                      : ShardMap
```

This command creates an Elastic Scale shared map target using the provided shard map server name, database name and name.
Job runs targeting the shard map target expand to run against each database shard in the shard map.
The database shards within the shard map are determined by the system through connecting to the shard map database using the specified shard map credentials.
A database target for the database server and the database must first be created along with the credentials.

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
Specifies the name of the custom collection.

```yaml
Type: String
Parameter Sets: CustomCollection
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the database.

```yaml
Type: String
Parameter Sets: Database
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the server.

```yaml
Type: String
Parameter Sets: Server, Database
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShardMapManagerCredentialName
Specifies the name of the credential to use whenever connecting to the shard map database to lookup the shards within the shard map.

```yaml
Type: String
Parameter Sets: ShardMap
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShardMapManagerDatabaseName
Specifies the database name containing the Elastic Scale shard map.

```yaml
Type: String
Parameter Sets: ShardMap
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShardMapManagerServerName
Specifies the database server name containing the Elastic Scale shard map.

```yaml
Type: String
Parameter Sets: ShardMap
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShardMapName
Specifies the name of the Elastic Scale shard map.

```yaml
Type: String
Parameter Sets: ShardMap
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralServerName
{{Fill LiteralServerName Description}}

```yaml
Type: SwitchParameter
Parameter Sets: Server, Database, ShardMap
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MasterDatabaseCredentialName
{{Fill MasterDatabaseCredentialName Description}}

```yaml
Type: String
Parameter Sets: Server
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

[Get-AzureSqlJobTarget](./Get-AzureSqlJobTarget.md)

[Set-AzureSqlJobTarget](./Set-AzureSqlJobTarget.md)

[Add-AzureSqlJobChildTarget](./Add-AzureSqlJobChildTarget.md)
