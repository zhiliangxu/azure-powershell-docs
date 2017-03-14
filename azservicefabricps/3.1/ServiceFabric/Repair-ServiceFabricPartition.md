---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: E64F672A-23EB-408C-82E8-8BD8B2C5A7A2
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Repair-ServiceFabricPartition.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Repair-ServiceFabricPartition.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Repair-ServiceFabricPartition

## SYNOPSIS
Brings a partition out of quorum loss.

## SYNTAX

### Partition (Default)
```
Repair-ServiceFabricPartition [-Force] [-PartitionId] <Guid> [-TimeoutSec <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Service
```
Repair-ServiceFabricPartition [-Service] [-Force] -ServiceName <Uri> [-TimeoutSec <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### All
```
Repair-ServiceFabricPartition [-All] [-Force] [-TimeoutSec <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### System
```
Repair-ServiceFabricPartition [-System] [-Force] [-TimeoutSec <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Repair-ServiceFabricPartition** cmdlet brings a stateful persisted partition forcefully out of quorum loss.
If a majority of the replicas of a stateful persisted partition go down, the partition goes into a state of quorum loss.
While in this state, write operations are not allowed for that partition and the partition cannot be reconfigured.
The expectation at this point is for the replicas to come back up so that the partition can resume making progress.
However, if replicas cannot come back up, you can run this cmdlet to bring the partition out of quorum loss.
If the primary replica is also down, data loss is declared for the partition.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Repair all partitions
```
PS C:\>Repair-ServiceFabricPartition -All
```

This command repairs all the partitions that are in the quorum loss state.

### Example 2: Repair a partition
```
PS C:\>Repair-ServiceFabricPartition -PartitionId 861907d2-1c38-4cf8-8bb4-49f4fec4a2e5
```

This command repairs the partition with the specified partition ID.

### Example 3: Repair all the partitions of a service
```
PS C:\>Repair-ServiceFabricPartition -Service -ServiceName fabric:/MyApp/MyPersistedService
```

This command repairs all the partitions of the service fabric:/MyApp/MyPersistedService.

### Example 4: Repair the partitions of the system services
```
PS C:\>Repair-ServiceFabricPartition -System
```

This command repairs all the partitions of all the system services.

## PARAMETERS

### -All
Indicates that this cmdlet repairs all the partitions that are in quorum loss.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -PartitionId
Specifies the ID of a Service Fabric partition.
This cmdlet repairs only the partition that this parameter specifies.

```yaml
Type: Guid
Parameter Sets: Partition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Service
Indicates that this cmdlet repairs only the partitions of the service that the *ServiceName* parameter specifies.

```yaml
Type: SwitchParameter
Parameter Sets: Service
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceName
Specifies the Uniform Resource Identifier (URI) of a Service Fabric service.

```yaml
Type: Uri
Parameter Sets: Service
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -System
Indicates that this cmdlet repairs all the partitions of the system services.

```yaml
Type: SwitchParameter
Parameter Sets: System
Aliases:

Required: True
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

### System.Uri, System.Guid
This cmdlet accepts a URI that represents the name of a Service Fabric service or the ID of a Service Fabric partition.

## OUTPUTS

### System.Object
This cmdlet returns the status of the operation as a string.

## NOTES

## RELATED LINKS

[Get-ServiceFabricPartition](./Get-ServiceFabricPartition.md)

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)
