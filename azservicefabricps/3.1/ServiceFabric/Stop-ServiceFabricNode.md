---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 4BC03E59-F564-4678-A6DE-83974795422C
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Stop-ServiceFabricNode.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Stop-ServiceFabricNode.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Stop-ServiceFabricNode

## SYNOPSIS
Stops a Service Fabric node.

## SYNTAX

```
Stop-ServiceFabricNode [-NodeName] <String> [[-NodeInstanceId] <BigInteger>]
 [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-ServiceFabricNode** cmdlet stops the node that you specify with the *NodeName* parameter by stopping the Fabric.exe process, which stops all of the system service and user service replicas hosted on that Service Fabric node.
If the command succeeds the intent is recorded, but the node may not stop immediately.

Safety checks are not performed when using this cmdlet.

If you specify the *NodeInstanceId* parameter, only the node with that ID is stopped.
If you specify a value for *NodeInstanceId* that does not match the active node, an error occurs.

Use this command to test the failover recovery paths by simulating stopped nodes in a cluster.
Unlike the [Restart-ServiceFabricNode](./Restart-ServiceFabricNode.md) cmdlet, **Stop-ServiceFabricNode** keeps the node stopped until you run the [Start-ServiceFabricNode](./Start-ServiceFabricNode.md) cmdlet to start the node.
If you stop a node with the **Stop-ServiceFabricNode** cmdlet, you should only start the node with the **Start-ServiceFabricNode** cmdlet.

Before using this cmdlet, connect to the Service Fabric cluster.

## EXAMPLES

### Example 1: Stop a node
```
PS C:\>Stop-ServiceFabricNode -NodeName "Node01" -CommandCompletionMode DoNotVerify
```

This command stops the node named Node01 and does not wait for the restart to complete.

### Example 2: Stop a node by instance ID
```
PS C:\>Stop-ServiceFabricNode -NodeName "Node02" -NodeInstanceId 1234 -CommandCompletionMode DoNotVerify
```

This command stops the node named Node02 and with the node instance ID of 1234.
If the value of the *NodeInstanceID* parameter does not match the node instance ID of the currently running node, an error occurs.

## PARAMETERS

### -CommandCompletionMode
Specifies whether the action waits for the restart to complete.

```yaml
Type: CompletionMode
Parameter Sets: (All)
Aliases:
Accepted values: Invalid, DoNotVerify, Verify

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeInstanceId
Specifies a node instance ID.
Unless you specify 0, the node instance ID is matched against the current node before the node is stopped.
The default value is 0.

```yaml
Type: BigInteger
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NodeName
Specifies the name of a Service Fabric node.
The cmdlet stops the node that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### string
Specifies the name of a Service Fabric node.

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.Testability.StopNode** object that represents the operation result.

## NOTES

## RELATED LINKS

[Disable-ServiceFabricNode](./Disable-ServiceFabricNode.md)

[Enable-ServiceFabricNode](./Enable-ServiceFabricNode.md)

[Get-ServiceFabricNode](./Get-ServiceFabricNode.md)

[Restart-ServiceFabricNode](./Restart-ServiceFabricNode.md)

[Start-ServiceFabricNode](./Start-ServiceFabricNode.md)
