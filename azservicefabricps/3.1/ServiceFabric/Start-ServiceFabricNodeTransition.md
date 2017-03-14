---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
updated_at: 01/07/2017 05:01 AM
ms.date: 01/07/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Start-ServiceFabricNodeTransition.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Start-ServiceFabricNodeTransition.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/eb308dd471400263264adbb79d1c32e357dd1049
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Start-ServiceFabricNodeTransition

## SYNOPSIS
Initiates an operation to start or stop a Service Fabric node.

## SYNTAX

### To transition a node to Stopped
```
Start-ServiceFabricNodeTransition -Stop -OperationId <Guid> -NodeName <String> -NodeInstanceId <BigInteger>
 -StopDurationInSeconds <Int32> [-TimeoutSec <Int32>]
```

### To transition a node from Stopped to Started
```
Start-ServiceFabricNodeTransition -Start -OperationId <Guid> -NodeName <String> -NodeInstanceId <BigInteger>
 [-TimeoutSec <Int32>]
```

## DESCRIPTION
The **Start-ServiceFabricNodeTransition** cmdlet initiates an asynchronous operation to start or stop a Service Fabric node. 

A Service Fabric node is process, not a virtual machine or computer. 
A virtual machine or computer continues to run. 
Specifying the *Stop* parameter puts a node into a Stopped state.
In the Stopped state, the node is not a member of the cluster and cannot host services.
A stopped node simulates a *down* node. 

Specifying the *Start* parameter starts a node that was stopped.

When this cmdlet returns successfully, the system has accepted the operation. 
Running this cmdlet does not imply that the operation finishes. 
To get information about the current state of the operation, run the [Get-ServiceFabricNodeTransitionProgress](./Get-ServiceFabricNodeTransitionProgress.md) cmdlet. 

This cmdlet is preferred over the [Start-ServiceFabricNode](./Start-ServiceFabricNode.md) and [Stop-ServiceFabricNode](./Stop-ServiceFabricNode.md) cmdlets. 

Avoid mixing usage of this cmdlet with **Start-ServiceFabricNode** and **Stop-ServiceFabricNode**. 
If a node is has already been stopped by using **Stop-ServiceFabricNode**, start it using **Start-ServiceFabricNode** before using **Start-ServiceFabricNodeTransition**.
Use Start-ServiceFabricNodeTransition from then on.

For more information, see [Replacing the Start Node and Stop node APIs with the Node Transition API](https://docs.microsoft.com/azure/service-fabric/service-fabric-node-transition-apis). 


## EXAMPLES

### Example 1: Stop a Service Fabric node
```
PS C:\> Start-ServiceFabricNodeTransition -Stop -OperationId 097b03e3-760a-419c-9fce-e83f8cc0894b -NodeName N0050 -NodeInstanceId 131242467532403195 -StopDurationInSeconds 3600
```

This command initiates an operation to stop a Service Fabric node for one hour. 
After one hour, the node automatically starts itself. 
Keep track of the *OperationId* value. 
You can use it to run **Get-ServiceFabricNodeTransitionProgress**.

### Example 2: Stop a Service Fabric node
```
PS C:\> Start-ServiceFabricNodeTransition -Start -OperationId 6d1bf9a1-9733-4d83-be59-0acea3be57a7 -NodeName N0050 -NodeInstanceId 131242467532403195
```


This command initiates an operation to start a Stopped Service Fabric node. 


## PARAMETERS

### -OperationId
Specifies a unique ID that identifies the operation. 
Use the same value for this cmdlet, which initiates the operation, and **Get-ServiceFabricNodeTransitionProgress**, which gets operation progress. 

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeName
Specifies the name of the Service Fabric node that this cmdlet starts or stops. 
To obtain Service Fabric nodes in your cluster, run the [Get-ServiceFabricNode](./Get-ServiceFabricNode.md) cmdlet.

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

### -NodeInstanceId
Specifies ID of the node instance that this cmdlet starts or stops. 
To obtain node instance IDs, run **Get-ServiceFabricNode** on the target node. 
For example, for the node N0050, the command `Get-ServiceFabricNode -NodeName "N0050"` returns a **Node** object that contains the node instance ID.

```yaml
Type: BigInteger
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### -Start
Indicates that this cmdlet starts a stopped node.

```yaml
Type: SwitchParameter
Parameter Sets: Start
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stop
Indicates that this cmdlet stops a running node.

```yaml
Type: SwitchParameter
Parameter Sets: Stop
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StopDurationInSeconds
Specifies the duration, in seconds, to keep a stopped node stopped after the operation to stop is completed. 
After this time, the node automatically starts. 

The minimum value is 600. 
The maximum value is 14400. 

You must specify the *Stop* parameter in order to specify a stop duration.


```yaml
Type: Int32
Parameter Sets: Stop
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSec
Specifies the time-out value, in seconds, for this cmdlet.

This is not the length of time that the stopped node remains stopped. 
To control how long a node is stopped, use the *StopDurationInSeconds* parameter.

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

## INPUTS


## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-ServiceFabricNode](./Get-ServiceFabricNode.md)

[Get-ServiceFabricNodeTransitionProgress](./Get-ServiceFabricNodeTransitionProgress.md)

[Start-ServiceFabricNode](./Start-ServiceFabricNode.md)

[Stop-ServiceFabricNode](./Stop-ServiceFabricNode.md)

[Replacing the Start Node and Stop node APIs with the Node Transition API](https://docs.microsoft.com/azure/service-fabric/service-fabric-node-transition-apis)
