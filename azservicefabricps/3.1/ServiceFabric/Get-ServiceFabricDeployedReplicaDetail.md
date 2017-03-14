---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: C8EDDC0C-C129-4D69-A269-A27B9FB5EB90
updated_at: 11/03/2016 02:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricDeployedReplicaDetail.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricDeployedReplicaDetail.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a04d7fb81ddb4ca19a8c0101c71d7745ad5e082a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricDeployedReplicaDetail

## SYNOPSIS
Gets information about Service Fabric replicas from a host process.

## SYNTAX

```
Get-ServiceFabricDeployedReplicaDetail [-NodeName] <String> [-PartitionId] <Guid>
 [-ReplicaOrInstanceId] <Int64> [-ReplicatorDetail] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricDeployedReplicaDetail** cmdlet gets information about Service Fabric replicas from the host process in which they run.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Get Replica Detail for a replica running on a node
```
PS C:\>Get-ServiceFabricDeployedReplicaDetail -NodeName "DB.41" -PartitionId 7B7D6D73-3D41-42A9-B7DF-B9D93A386BFF -ReplicaOrInstanceId 130705747836122602
```

This command gets the replica detail for a replica running on a node from the service host process.

### Example 2: Get Replica Detail for a replica running on a node including the replicator detail
```
PS C:\>Get-ServiceFabricDeployedReplicaDetail -NodeName "DB.41" -PartitionId 7B7D6D73-3D41-42A9-B7DF-B9D93A386BFF -ReplicaOrInstanceId 130705747836122602 -ReplicatorDetail
```

This command gets the replica detail for a replica running on a node from the service host process.

## PARAMETERS

### -NodeName
Specifies the name of a Service Fabric node.
This cmdlet gets details about replicas that run in this node.

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

### -PartitionId
Specifies the ID of a Service Fabric partition.
This parameter identifies the partition that has the replica or instance ID.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplicaOrInstanceId
Specifies the Service Fabric service replica or instance ID for which to get information.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplicatorDetail
Indicates that this cmdlet gets information from the Service Fabric Replicator.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
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

### String, System.Guid, Int64
This parameter accepts a string that represents a Service Fabric node name, or the GUID of a Service Fabric partition, or an integer replica or instance ID.

## OUTPUTS

### System.Object
This cmdlet returns a **DeployedServiceReplicaDetail** object that contains information about a Service Fabric replica.

## NOTES

## RELATED LINKS

[Get-ServiceFabricDeployedReplica](./Get-ServiceFabricDeployedReplica.md)

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)
