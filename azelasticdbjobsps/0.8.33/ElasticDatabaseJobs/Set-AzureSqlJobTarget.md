---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: AA3F0D08-ADFD-407E-9359-6F3EEB131286
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Set-AzureSqlJobTarget.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Set-AzureSqlJobTarget.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Set-AzureSqlJobTarget

## SYNOPSIS
Updates a job target definition.

## SYNTAX

### Server
```
Set-AzureSqlJobTarget -ServerName <String> -MasterDatabaseCredentialName <String> [-LiteralServerName]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

### ShardMap
```
Set-AzureSqlJobTarget -ShardMapManagerServerName <String> -ShardMapManagerDatabaseName <String>
 -ShardMapManagerCredentialName <String> -ShardMapName <String> [-LiteralServerName]
 [[-AzureSqlJobConnection] <AzureSqlJobConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureSqlJobTarget** cmdlet updates a job target definition.
This currently enables a specified shard map target to have its credentials updated.

## EXAMPLES

### Example 1: Update credentials used within a shard map target
```
PS C:\>New-AzureSqlJobTarget -ShardMapManagerServerName "MyShardMapManagerServer.database.contoso.net" -ShardMapManagerDatabaseName "MyShardMapManagerDatabase" -ShardMapManagerCredentialName "MyUpdatedShardMapCredentials" -ShardMapName "MyShardMap"
TargetDescription               : {"ShardMapName":"MyShardMap","ShardMapManagerServerName":"MyShardMapManagerServer.database.contoso.net","ShardMapManagerDatabaseName":"MyShardMapManagerDatabase"}

ShardMapName                    : MyShardMap

ShardMapManagerServerName       : MyShardMapManagerServer.database.contoso.net

ShardMapManagerDatabaseName     : MyShardMapManagerDatabase

ShardMapManagerDatabaseTargetId : 9eb3ee50-e4b2-4feb-b2f7-3ee1cd7f7997

ShardMapManagerCredentialName   : MyUpdatedShardMapCredentials

TargetId                        : 1afd9326-1277-4344-832f-8170d0375ff7

TargetType                      : ShardMap
```

This command updates the credentials used to determine databases within an Elastic Scale shared map target using the provided shard map server name, database name and name

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
Specifies the Elastic Scale shard map database name.

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
Specifies the Elastic Scale shard map server name.

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
Specifies the Elastic Scale shard map name.

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
Parameter Sets: (All)
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

### -ServerName
Specifies the name of the server.

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

[New-AzureSqlJobTarget](./New-AzureSqlJobTarget.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
