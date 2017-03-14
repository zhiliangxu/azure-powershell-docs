---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 0A5D69FE-2951-4F57-8935-D9FEEBBCBA0C
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Use-AzureSqlJobConnection.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/Use-AzureSqlJobConnection.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Use-AzureSqlJobConnection

## SYNOPSIS
Sets the Azure PowerShell session context to use the provided connection to the Elastic Database Jobs control database.

## SYNTAX

### ConnectionObject
```
Use-AzureSqlJobConnection [-AzureSqlJobConnection] <AzureSqlJobConnection> [<CommonParameters>]
```

### None
```
Use-AzureSqlJobConnection [-None] [<CommonParameters>]
```

### CurrentAzureSubscription
```
Use-AzureSqlJobConnection [-CurrentAzureSubscription] [-ResourceGroupName <String>] -Credential <PSCredential>
 [<CommonParameters>]
```

### ConnectionDetails
```
Use-AzureSqlJobConnection -ServerName <String> -DatabaseName <String> [-LiteralServerName]
 -Credential <PSCredential> [<CommonParameters>]
```

## DESCRIPTION
The **Use-AzureSqlJobConnection** cmdlet sets the Azure PowerShell session context to use the provided connection to the Elastic Database jobs control database.

Subsequent Elastic Database Jobs cmdlet invocations will make use of the connection information specified within the [Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md) cmdlet invocation.

## EXAMPLES

### Example 1: Set the PowerShell session context to use the provided connection to the Elastic Database jobs control database previously installed
```
PS C:\>Use-AzureSqlJobConnection -CurrentAzureSubscription
```

This command sets the Azure PowerShell session context to use a connection to the Elastic Database Jobs database previously installed within the current Azure subscription within the __ElasticDatabaseJobs__ resource group.
Following the cmdlet invocation, credentials will be prompted.

### Example 2: Set the PowerShell session context to use the provided connection to the Elastic Database jobs control database.
```
PS C:\>Use-AzureSqlJobConnection -ServerName "MyServer" -DatabaseName "MyDatabase"
```

This command sets the Azure PowerShell session context to use a connection to the Elastic Database jobs database named MyDatabase.
You are then prompted for credentials after the cmdlet runs.

## PARAMETERS

### -AzureSqlJobConnection
Specifies the connection state object for the job.
You can get the connection state object through the [New-AzureSqlJobConnection](./New-AzureSqlJobConnection.md) cmdlet.
If you do not specify this parameter, the connection state is used from a prior call to the [Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md) cmdlet.

```yaml
Type: AzureSqlJobConnection
Parameter Sets: ConnectionObject
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
Specifies the **PSCredential** containing the username and password for the Elastic Database job control database connections.

```yaml
Type: PSCredential
Parameter Sets: CurrentAzureSubscription, ConnectionDetails
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CurrentAzureSubscription
Indicates that the Elastic Database jobs control database will be looked up within the current subscription by finding the Azure SQL Database within the ElasticDatabaseJobs resource group.

```yaml
Type: SwitchParameter
Parameter Sets: CurrentAzureSubscription
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Specifies the database name of the Elastic Database jobs control database.

```yaml
Type: String
Parameter Sets: ConnectionDetails
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -None
Indicates that any set connection info context within the session from previous calls to this cmdlet are removed.

```yaml
Type: SwitchParameter
Parameter Sets: None
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the Azure resource group that contains the Elastic Database jobs control database.
The cmdlet will identify the Elastic Database jobs control database within the resource group.

```yaml
Type: String
Parameter Sets: CurrentAzureSubscription
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the database server name of the Elastic Database jobs control database.

```yaml
Type: String
Parameter Sets: ConnectionDetails
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
Parameter Sets: ConnectionDetails
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

[New-AzureSqlJobConnection](./New-AzureSqlJobConnection.md)

[Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
