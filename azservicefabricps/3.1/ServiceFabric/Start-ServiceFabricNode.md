---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 368529F1-EA7E-407B-93A7-352ED6D2048C
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Start-ServiceFabricNode.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Start-ServiceFabricNode.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Start-ServiceFabricNode

## SYNOPSIS
Starts a Service Fabric node.

## SYNTAX

```
Start-ServiceFabricNode [-NodeName] <String> [[-NodeInstanceId] <BigInteger>] [[-IpAddressOrFQDN] <String>]
 [[-ClusterConnectionPort] <Int32>] [-CommandCompletionMode <CompletionMode>] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-ServiceFabricNode** cmdlet starts the node specified by the *NodeName* parameter that has been stopped using the [Stop-ServiceFabricNode](./Stop-ServiceFabricNode.md) cmdlet, StopNodeAsync, or a representational state transfer (REST) equivalent.
If the cmdlet succeeds, the intent is recorded but the node may not be immediately available.

Use this cmdlet to test your service along the failover recovery paths.
This cmdlet helps to test when nodes are added to the cluster to restore the state of persisted replicas, and helps to test load balancing when capacity is added to the system.

If you specify the *NodeInstanceId* parameter, then you can only use this cmdlet to start a node with that instance ID.
If you specify 0 for the *NodeInstanceId* parameter, it is ignored.

The optional *IpAddressOrFQDN* and *ClusterConnectionPort* parameters must be used together.
If you specify one, you must also specify the other.
If you do not specify the *IpAddressOrFQDN* and *ClusterConnectionPort* parameters, the system performs an internal query to determine how to forward the command.
If some system services are in quorum loss, the internal query will fail.
In this case, be sure to specify the *IpAddressOrFQDN* and *ClusterConnectionPort* parameters.
In general, you should not specify *IpAddressOrFQDN * or *ClusterConnectionPort*.
You should use the **Start-ServiceFabricNode** cmdlet only on nodes that were stopped using the **Stop-ServiceFabricNode** cmdlet.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Start a node
```
PS C:\>Start-ServiceFabricNode -NodeName "Node01" -CommandCompletionMode DoNotVerify
```

This command starts the node named Node01 and does not wait for the start to complete.

### Example 2: Start a node with a specific NodeInstanceId
```
PS C:\>Start-ServiceFabricNode -NodeName "Node02" -NodeInstanceId 1234 -CommandCompletionMode DoNotVerify
```

This command starts the node named Node02 with a NodeInstanceId value of 1234 and does not wait for the start to complete.

### Example 3: Start a node and specify the IPAddressOrFQDN and ClusterConnectionPort parameters
```
PS C:\>Start-ServiceFabricNode -NodeName "Node03" -IpAddressOrFQDN 172.16.0.0 -ClusterConnectionPort 10555 -CommandCompletionMode DoNotVerify
```

This command starts the node named Node03, which has the IP address 172.16.0.0 and a cluster connection port of 10555.
You can get the IP address and cluster connection port of a node by using the [Get-ServiceFabricNode](./Get-ServiceFabricNode.md) cmdlet.

## PARAMETERS

### -ClusterConnectionPort
Specifies the cluster connection port for the node to start.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -IpAddressOrFQDN
Specifies the IP address or fully qualified domain name (FQDN) for the node to start.
You can use the **Get-ServiceFabricNode** cmdlet to get the FQDN or IP address of a node.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NodeInstanceId
Specifies a node instance ID.
Unless you specify 0, the node instance ID that you specify is matched against the current node before the node is started.

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
The cmdlet starts the node that you specify.

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
This cmdlet returns a **System.Fabric.Testability.StartNodeResult** object that represents the operation result.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Disable-ServiceFabricNode](./Disable-ServiceFabricNode.md)

[Enable-ServiceFabricNode](./Enable-ServiceFabricNode.md)

[Get-ServiceFabricNode](./Get-ServiceFabricNode.md)

[Restart-ServiceFabricNode](./Restart-ServiceFabricNode.md)

[Stop-ServiceFabricNode](./Stop-ServiceFabricNode.md)
