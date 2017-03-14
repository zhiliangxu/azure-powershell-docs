---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 239A882B-8E31-4404-AB35-2A39D8ABC600
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Start-ServiceFabricRepairTask.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Start-ServiceFabricRepairTask.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Start-ServiceFabricRepairTask

## SYNOPSIS
Starts a repair task.

## SYNTAX

### NodeBuiltInAuto (Default)
```
Start-ServiceFabricRepairTask [-NodeName] <String> [-NodeAction] <SystemNodeRepairAction> [-TaskId <String>]
 [-Description <String>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### NodeCustomAuto
```
Start-ServiceFabricRepairTask [-NodeNames] <String[]> [-CustomAction] <String> [-TaskId <String>]
 [-Description <String>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### NodeManual
```
Start-ServiceFabricRepairTask [-NodeNames] <String[]> [-NodeImpact] <NodeImpactLevel> [-TaskId <String>]
 [-Description <String>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-ServiceFabricRepairTask** cmdlet starts a repair task.
You can create Service Fabric repair tasks that run automatically or manually.
To create repair tasks, first enable the Repair Manager system service in the cluster configuration.
For repair tasks that run automatically, an appropriate repair executor must be running for each repair action to run automatically.
These are currently only available in specially-configured Azure Cloud Services.

This cmdlet supports the Service Fabric platform.
Do not run this cmdlet directly.

To create a manual repair task, provide the set of impacted node names and the expected impact.
When the state of the created repair task changes to approved, you can safely perform repair actions on those nodes.
After you finish repairing the nodes, use the [Complete-ServiceFabricRepairTask](./Complete-ServiceFabricRepairTask.md) cmdlet to complete the task and bring the nodes back online.

To create an automatic repair task, provide the target node name and desired repair action.
You can provide one of the built-in node repair actions, or you can specify a string that contains the full name of the custom repair action.
If the custom repair executor for the action supports it, you can also specify more than one target node.

This cmdlet requires that you connect to the cluster with credentials that are granted administrator access to the cluster.
Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Create a manual repair task
```
PS C:\>Start-ServiceFabricRepairTask -NodeNames "MyNode.0","MyNode.4" -NodeImpact RemoveData
```

This command creates a manual repair task for two nodes whose data will be removed.

## PARAMETERS

### -CustomAction
Specifies the repair action to perform.
You can specify any action that one of the repair executors supports.

```yaml
Type: String
Parameter Sets: NodeCustomAuto
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description of the purpose of the repair task, or other information.

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

### -NodeAction
Specifies the repair action to perform.
Valid values are:

- Reboot.
Requests a reboot of the computer on which the node runs.
- ReimageOS.
Requests that the operating system volume be reimaged on the computer on which the given node is running.
- FullReimage.
Requests that all disk volumes be reimaged on the computer on which the given node runs.

```yaml
Type: SystemNodeRepairAction
Parameter Sets: NodeBuiltInAuto
Aliases:
Accepted values: Reboot, ReimageOS, FullReimage

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeImpact
Specifies the expected level of impact of a manual repair of a set of nodes.
Valid values are:

- Invalid.
Do not specify this value.
- None.
No expected impact.
- Restart.
The node is expected to stop and restart.
- RemoveData.
The node is expected to stop.
It may lose all of its persisted state prior to restarting.

```yaml
Type: NodeImpactLevel
Parameter Sets: NodeManual
Aliases:
Accepted values: Invalid, None, Restart, RemoveData

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeName
Specifies the name of a Service Fabric node.
This cmdlet repairs the node that this parameter specifies.

```yaml
Type: String
Parameter Sets: NodeBuiltInAuto
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NodeNames
Specifies an array of names of Service Fabric nodes.
This cmdlet repairs the nodes that this parameter specifies.

```yaml
Type: String[]
Parameter Sets: NodeCustomAuto, NodeManual
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskId
Specifies the ID of the repair task to create.
If you do not specify an ID, this cmdlet generates a unique ID.

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

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### System.Object
This cmdlet returns an object that contains the **TaskID** and **Version** of the newly created repair task.

## NOTES

## RELATED LINKS

[Approve-ServiceFabricRepairTask](./Approve-ServiceFabricRepairTask.md)

[Complete-ServiceFabricRepairTask](./Complete-ServiceFabricRepairTask.md)

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricRepairTask](./Get-ServiceFabricRepairTask.md)

[Remove-ServiceFabricRepairTask](./Remove-ServiceFabricRepairTask.md)

[Stop-ServiceFabricRepairTask](./Stop-ServiceFabricRepairTask.md)
