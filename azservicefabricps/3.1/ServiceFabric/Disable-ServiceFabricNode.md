---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 27DE3E8D-897E-498F-A0EA-9BF60E5688B0
updated_at: 11/03/2016 02:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Disable-ServiceFabricNode.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Disable-ServiceFabricNode.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a04d7fb81ddb4ca19a8c0101c71d7745ad5e082a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Disable-ServiceFabricNode

## SYNOPSIS
Disables a Service Fabric node.

## SYNTAX

```
Disable-ServiceFabricNode [-NodeName] <String> [-Intent] <NodeDeactivationIntent> [-Force]
 [-TimeoutSec <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-ServiceFabricNode** cmdlet informs Service Fabric before an administrative action is taken on a node that may impact the replicas on the node.

For example, before restarting a node, disabling the node with intent restart informs Service Fabric to gracefully close the replicas on the node.
You must wait for the node to become disabled before restarting the node.
Use the [Get-ServiceFabricNode](.\Get-ServiceFabricNode.md) cmdlet to view the disabling status of the node.
Service Fabric ensures that services stay available even if these replicas are closed.
The node stays in the disabling state until it is safe to disable it without impacting service availability.
After the restart has been completed, the node can be enabled using the [Enable-ServiceFabricNode](.\Enable-ServiceFabricNode.md) cmdlet, which informs Service Fabric that the node can now be used for placing replicas.

To manage Service Fabric clusters, start Windows PowerShell by using the Run as administrator option.
Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Deactivate a node with intent restart
```
PS C:\>Disable-ServiceFabricNode -NodeName "DB.41" -Intent Restart
```

This command disables a node with node name DB.41 with intent restart.

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

### -Intent
Specifies the intent for the disable node.
The intent determines the action that Service Fabric takes for the node.
The acceptable values for this parameter are:

- Pause.
No new replicas are placed on the node.
Existing replicas continue to run.
You might specify this setting to debug replicas that run on the node.
- Restart.
Existing replicas on the node are closed.
Replicas are not moved to other node.
You might specify this setting when a node restart is required for installing a patch.
- RemoveData.
Specifies that the data on the node is to be permanently lost.
This cmdlet creates copies of the replicas that run on the node on other nodes to ensure high availability.
You might specify this setting when the hard disk is being reimaged.
- RemoveNode.
Specifies that the data on the node is to be permanently lost.
This cmdlet creates copies of the replicas that run on the node on other nodes to ensure high availability.
You might specify this setting when the node is being removed from the cluster.

```yaml
Type: NodeDeactivationIntent
Parameter Sets: (All)
Aliases:
Accepted values: Invalid, Pause, Restart, RemoveData, RemoveNode

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeName
Specifies the name of a Service Fabric node.
The cmdlet disables the node that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSec
Specifies the time-out period, in seconds, for the operation.

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

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### System.Object
This cmdlet returns a message that includes the status of the operation.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Enable-ServiceFabricNode](./Enable-ServiceFabricNode.md)

[Get-ServiceFabricNode](./Get-ServiceFabricNode.md)
