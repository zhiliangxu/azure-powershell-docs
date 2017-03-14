---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
updated_at: 01/07/2017 05:01 AM
ms.date: 01/07/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricNodeTransitionProgress.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricNodeTransitionProgress.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/eb308dd471400263264adbb79d1c32e357dd1049
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricNodeTransitionProgress

## SYNOPSIS
Gets the progress of a node transition operation.

## SYNTAX

```
Get-ServiceFabricNodeTransitionProgress -OperationId <Guid> [-TimeoutSec <Int32>]
```

## DESCRIPTION
The **Get-ServiceFabricNodeTransitionProgress** cmdlet gets the progress of a node transition operation that is started by using the [Start-ServiceFabricNodeTransition](./Start-ServiceFabricNodeTransition.md) cmdlet. 
This cmdlet returns an object of type **System.Fabric.NodeTransitionProgress**. 
The **State** property of that object indicates the current state of the operation. 
For example, Running means the operation is in progress. 
Completed means it finished successfully. 

## EXAMPLES

### Example 1: Check progress of an operation 
```
PS C:\> $currentProgress = Get-ServiceFabricNodeTransitionProgress -OperationId c645433e-a68f-4c8a-8cfb-076d339726a8

  State Result
  ----- ------
Running
```

The first command gets the progress of operation that has the specified ID. 
The operation was started by using **Start-ServiceFabricNodeTransition**. 
The command stores the result in the $CurrentProgress variable.
 
The second command displays the state of $CurrentProgress. 
In this example, the state is Running.

### Example 2: Troubleshoot failed operation
```
PS C:\> $CurrentProgress = Get-ServiceFabricNodeTransitionProgress -OperationId 6f2bedbe-72c7-4d25-891d-4e070e8809a0

PS C:\> $CurrentProgress.State

  State Result
  ----- ------
Faulted

PS C:\> $CurrentProgress.Result.Exception.ErrorCode

InstanceIdMismatch

```

The first command gets the progress of operation that has the specified ID.
The command stores the result in $CurrentProgress.

The second command displays the state of $CurrentProgress. 
In this example, the operation fails. 
The value of **State** property is Faulted. 

The third command displays the **Result.Exception.ErrorCode** value of the **State**. 
Until the operation reaches a terminal state, the result object is $Null. 
In this example, an incorrect *NodeInstanceId* was provided.


## PARAMETERS

### -OperationId
Specifies the unique ID used to track an operation. 
Specify the same value that you used to start the operation by using **Start-ServiceFabricNodeTransition**.

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

### -TimeoutSec
Specifies the time-out value, in seconds, for this cmdlet.

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

### System.Fabric.NodeTransitionProgress

## NOTES

## RELATED LINKS

[Start-ServiceFabricNodeTransition](./Start-ServiceFabricNodeTransition.md)

[Replacing the Start Node and Stop node APIs with the Node Transition API](https://docs.microsoft.com/azure/service-fabric/service-fabric-node-transition-apis)
