---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 9A5DA030-1323-4157-A3DE-3ED68A2AA354
updated_at: 11/03/2016 09:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Remove-ServiceFabricNodeConfiguration.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Remove-ServiceFabricNodeConfiguration.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/01e9ebd12a5214c9c4f85a2b71b372181a0bf8a9
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Remove-ServiceFabricNodeConfiguration

## SYNOPSIS
Removes information related to a configured node.

## SYNTAX

```
Remove-ServiceFabricNodeConfiguration [-DeleteLog] [-Force] [-MachineName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-ServiceFabricNodeConfiguration** cmdlet removes all the data and configuration settings stored on the operating system instance related to the node.
This cmdlet does not change the Service Fabric state.
To completely remove all information about the node, including the state, you must also use the [Remove-ServiceFabricNodeState](./Remove-ServiceFabricNodeState.md) cmdlet.
This removes the state from the system services.

To manage Service Fabric clusters, start your Windows PowerShell session by using the Run as administrator option.

## EXAMPLES

### Example 1: Remove a service node configuration
```
PS C:\> Remove-ServiceFabricNodeConfiguration -MachineName "192.168.1.1" -DeleteLog
```

This command removes the service node configuration from the computer with the IP address 192.168.1.1.
The *DeleteLog* parameter is included in order to remove the per-node log as well.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeleteLog
Indicates that the cmdlet removes the per-node log.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -MachineName
Specifies the computer that the configuration is removed from.
You can use either the computer name or the computer IP address.
For example:

`-MachineName "192.168.1.1"`

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
This cmdlet does not accept pipelined input.

## OUTPUTS

###  
This cmdlet returns the status of the operation as a string.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[New-ServiceFabricNodeConfiguration](./New-ServiceFabricNodeConfiguration.md)

[Update-ServiceFabricNodeConfiguration](./Update-ServiceFabricNodeConfiguration.md)

[Remove-ServiceFabricNodeState](./Remove-ServiceFabricNodeState.md)
