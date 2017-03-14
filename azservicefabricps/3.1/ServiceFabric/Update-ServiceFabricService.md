---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: DDD8A281-FDC8-49B1-9546-7E58FA7ADFB7
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Update-ServiceFabricService.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Update-ServiceFabricService.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Update-ServiceFabricService

## SYNOPSIS
Updates a Service Fabric service.

## SYNTAX

### Stateless (Default)
```
Update-ServiceFabricService [-Stateless] [-ServiceName] <Uri> [-InstanceCount <Int32>] [-Force]
 [-PlacementConstraints <String>] [-Metric <String[]>] [-Correlation <String[]>] [-PlacementPolicy <String[]>]
 [-DefaultMoveCost <String>] [-TimeoutSec <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Stateful
```
Update-ServiceFabricService [-Stateful] [-ServiceName] <Uri> [-TargetReplicaSetSize <Int32>]
 [-MinReplicaSetSize <Int32>] [-ReplicaRestartWaitDuration <TimeSpan>] [-QuorumLossWaitDuration <TimeSpan>]
 [-StandByReplicaKeepDuration <TimeSpan>] [-Force] [-PlacementConstraints <String>] [-Metric <String[]>]
 [-Correlation <String[]>] [-PlacementPolicy <String[]>] [-DefaultMoveCost <String>] [-TimeoutSec <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-ServiceFabricService** cmdlet updates properties of a running Service Fabric service.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Update a stateful service
```
PS C:\>Update-ServiceFabricService -Stateful fabric:/myapp/test -MinReplicaSetSize 3 -TargetReplicaSetSize 5
```

This command updates the **MinReplicaSetSize** and **TargetReplicaSetSize** of a running Fabric Service to three (3) and five (5).

### Example 2: Update a stateless service
```
PS C:\>Update-ServiceFabricService -Stateless fabric:/myapp/test -InstanceCount -1
```

This command updates the instance count of a running Fabric Service to a value of -1.

### Example 3: Update placement constraints
```
PS C:\>Update-ServiceabricService -Stateless -ServiceName fabric:/myapp/test -PlacementConstraints "NodeName!=NodeBar"
```

This command updates the placement constraints.

### Example 4: Update default load metrics
```
PS C:\>Update-ServiceFabricService -Stateless -ServiceName fabric:/myapp/test -Metric @("CPU,High,10")
PS C:\> Update-ServiceFabricService -Stateful -ServiceName fabric:/myapp/test -Metric @("CPU,High,10,1")
```

The first command updates the default load metrics for a stateless service.

The second command updates the default load metrics for a stateful service.

### Example 5: Update placement policy
```
PS C:\>Update-ServiceFabricService -Stateful -ServiceName fabric:/myapp/test -PlacementPolicy @("InvalidDomain,fd:/dc2/rack2")
```

This command updates the placement policy.

### Example 6: Update service correlation
```
PS C:\>Update-ServiceFabricService -Stateful -ServiceName fabric:/myapp/test -Correlation @("fabric:/app/test2,AlignedAffinity")
```

This command updates the service correlation.

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

### -Correlation
Specifies an updated array of correlation constraints for this service.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultMoveCost
Specifies the updated default move cost that replicas have when they are created.
The acceptable values for this parameter are:

- Zero
- Low
- Medium
- High

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Zero, Low, Medium, High

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

### -InstanceCount
Specifies the updated number of instances for the stateless service.
Do not specify this parameter for stateful services.

```yaml
Type: Int32
Parameter Sets: Stateless
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Metric
Specifies the updated array of metrics that the service reports.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinReplicaSetSize
Specifies the updated minimum replica set size for the Service Fabric stateful service.
The value must be less than the *TargetReplicaSetSize* of this service.
Do not specify this parameter for stateless services.

```yaml
Type: Int32
Parameter Sets: Stateful
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlacementConstraints
Specifies the updated placement constraint for the service.

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

### -PlacementPolicy
Specifies an updated array of placement policies for a service.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QuorumLossWaitDuration
Specifies the updated duration, as a **TimeSpan** object, that Service Fabric waits before it declares data loss for a service partition.
To obtain a **TimeSpan** object, use the [New-TimeSpan](http://go.microsoft.com/fwlink/?LinkID=113360) cmdlet.
For more information, type `Get-Help New-TimeSpan`.

```yaml
Type: TimeSpan
Parameter Sets: Stateful
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaRestartWaitDuration
Specifies the updated interval, as a **TimeSpan** object, that Service Fabric waits for the replica to restart before it creates a replacement replica.
To obtain a **TimeSpan** object, use the **New-TimeSpan** cmdlet.

```yaml
Type: TimeSpan
Parameter Sets: Stateful
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceName
Specifies the URI of a Service Fabric service.
This cmdlet updates the service that this parameter specifies.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StandByReplicaKeepDuration
Specifies the updated stand-by replica keep duration as a **TimeSpan** object.

```yaml
Type: TimeSpan
Parameter Sets: Stateful
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stateful
Indicates that the service is a Service Fabric stateful service.

```yaml
Type: SwitchParameter
Parameter Sets: Stateful
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stateless
Indicates that the service is a Service Fabric stateless service.

```yaml
Type: SwitchParameter
Parameter Sets: Stateless
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetReplicaSetSize
Specifies the updated target replica set size for a Service Fabric stateful service.
Do not specify this parameter for a stateless service.

```yaml
Type: Int32
Parameter Sets: Stateful
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

### System.Uri
Specifies a URI that represents the name of a Service Fabric service.

## OUTPUTS

### System.Object
This cmdlet returns the status of the operation as a string.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Get-ServiceFabricService](./Get-ServiceFabricService.md)

[New-ServiceFabricService](./New-ServiceFabricService.md)

[Remove-ServiceFabricService](./Remove-ServiceFabricService.md)

[Resolve-ServiceFabricService](./Resolve-ServiceFabricService.md)
