---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: BB0DF9FF-1EAC-46AD-B964-878BE2C22287
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJobTarget.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Get-AzureSqlJobTarget.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-AzureSqlJobTarget

## SYNOPSIS
Gets one or multiple containers of databases that can be used as a target for job runs.

## SYNTAX

### All (Default)
```
Get-AzureSqlJobTarget [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### TargetId
```
Get-AzureSqlJobTarget -TargetId <Guid[]> [[-AzureSqlJobConnection] <AzureSqlJobConnection>]
 [<CommonParameters>]
```

### ParentTargetId
```
Get-AzureSqlJobTarget -ParentTargetId <Guid> [[-AzureSqlJobConnection] <AzureSqlJobConnection>]
 [<CommonParameters>]
```

### Database
```
Get-AzureSqlJobTarget -ServerName <String> -DatabaseName <String> [-LiteralServerName]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### Server
```
Get-AzureSqlJobTarget -ServerName <String> [-LiteralServerName]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### ShardMap
```
Get-AzureSqlJobTarget -ShardMapManagerServerName <String> -ShardMapManagerDatabaseName <String>
 -ShardMapName <String> [-LiteralServerName] [[-AzureSqlJobConnection] <AzureSqlJobConnection>]
 [<CommonParameters>]
```

### CustomCollection
```
Get-AzureSqlJobTarget -CustomCollectionName <String> [[-AzureSqlJobConnection] <AzureSqlJobConnection>]
 [<CommonParameters>]
```

### ParentCustomCollection
```
Get-AzureSqlJobTarget -ParentCustomCollectionName <String> [[-AzureSqlJobConnection] <AzureSqlJobConnection>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSqlJobTarget** cmdlet gets one or multiple containers of databases that can be used as a target for job execution.

There are multiple supported types of targets, namely custom collection targets, database targets, and Elastic Scale shard map targets.
Each target type can be retrieved through the different parameter sets within this cmdlet.

## EXAMPLES

### Example 1: Get a custom collection
```
PS C:\>Get-AzureSqlJobTarget -CustomCollectionName "MyCustomCollection"
TargetDescription             CustomCollectionName          TargetId                                         TargetType
-----------------             --------------------          --------                                         ----------
{"CustomCollectionName":"m... myCustomCollection            b525727e-6ed0-44cc-94da-63...              CustomCollection
```

This command gets a custom collection named MyCustomCollection.

### Example 2: Get all child targets within the specified parent custom collection
```
PS C:\>Get-AzureSqlDatabaseJobTarget -ParentCustomCollectionName "MyCustomCollection"
TargetDescription                       CustomCollectionName                    TargetId                                                           TargetType
-----------------                       --------------------                    --------                                                           ----------
{"CustomCollectionName":"myCustomCol... myCustomCollection                      b525727e-6ed0-44cc-94da-63c543e383d7                         CustomCollection
{"ServerName":"myServer.database.win...                                         0f31294a-f42f-414d-a00f-4df43e9bd493                                 Database
```

This command gets all child targets within the provided parent custom collection named MyCustomCollection.

### Example 3: Get an elastic scale shard map target
```
PS C:\>Get-AzureSqlJobTarget -ShardMapManagerServerName "MyShardMapManagerServer.database.contoso.net" -ShardMapManagerDatabaseName "MyShardMapManagerDatabase" -ShardMapName "MyShardMap"
TargetDescription               : {"ShardMapName":"myShardMap","ShardMapManagerServerName":"myShardMapManagerServer.dat
                                  abase.contoso.net","ShardMapManagerDatabaseName":"myShardMapManagerDatabase"}
ShardMapName                    : MyShardMap
ShardMapManagerServerName       : MyShardMapManagerServer.database.contoso.net
ShardMapManagerDatabaseName     : MyShardMapManagerDatabase
ShardMapManagerDatabaseTargetId : 9eb3ee50-e4b2-4feb-b2f7-3ee1cd7f7997
ShardMapManagerCredentialName   : myShardMapCredentials
TargetId                        : 1afd9326-1277-4344-832f-8170d0375ff7
TargetType                      : ShardMap
```

This command gets an elastic scale shard map target.

### Example 4: Get a database target
```
PS C:\>Get-AzureSqlJobTarget -ServerName "myServer.database.contoso.net" -DatabaseName "MyDatabase"
TargetDescription : {"ServerName":"myServer.database.contoso.net","DatabaseName":"myDatabase"}
ServerName        : myServer.database.contoso.net
DatabaseName      : myDatabase
TargetId          : 0f31294a-f42f-414d-a00f-4df43e9bd493
TargetType        : Database
```

This command gets a database target named MyDatabase.

### Example 5: Get all job targets
```
PS C:\>Get-AzureSqlJobTarget
TargetDescription             CustomCollectionName          TargetId                                         TargetType
-----------------             --------------------          --------                                         ----------
{"CustomCollectionName":"m... myCustomCollection            b525727e-6ed0-44cc-94da-63...              CustomCollection
{"ServerName":"myServer.da...                               0f31294a-f42f-414d-a00f-4d...                      Database
{"ServerName":"myShardMapM...                               9eb3ee50-e4b2-4feb-b2f7-3e...                      Database
{"ShardMapName":"myShardMa...                               1afd9326-1277-4344-832f-81...                      ShardMap
```

This command gets all job targets.

## PARAMETERS

### -AzureSqlJobConnection
Specifies the connection state object for the job.
You can get the connection state object through the N[ew-AzureSqlJobConnection](./New-AzureSqlJobConnection.md) cmdlet.
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
Specifies the name of the custom collection that this cmdlet gets.

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
Specifies the name of a database within a database target that this cmdlet gets.

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

### -ParentCustomCollectionName
Specifies the name of the parent custom collection name to get targets.
This cmdlet gets all child targets of the specified customâ€¦

```yaml
Type: String
Parameter Sets: ParentCustomCollection
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentTargetId
Specifies the parent target ID.
If you specify this parameter, this cmdlet returns all child targets of the specified parent target ID.

```yaml
Type: Guid
Parameter Sets: ParentTargetId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the name of a database server within a database target that this cmdlet gets.

```yaml
Type: String
Parameter Sets: Database, Server
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShardMapManagerDatabaseName
Specifies the elastic scale shard map database name.

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
Specifies the elastic scale shard map server name.

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
Specifies the elastic scale shard map name.

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

### -TargetId
Specifies the target ID.

```yaml
Type: Guid[]
Parameter Sets: TargetId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LiteralServerName
{{Fill LiteralServerName Description}}

```yaml
Type: SwitchParameter
Parameter Sets: Database, Server, ShardMap
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

[New-AzureSqlJobTarget](./New-AzureSqlJobTarget.md)

[Set-AzureSqlJobTarget](./Set-AzureSqlJobTarget.md)

[New-AzureSqlJobConnection](./New-AzureSqlJobConnection.md)

[Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
