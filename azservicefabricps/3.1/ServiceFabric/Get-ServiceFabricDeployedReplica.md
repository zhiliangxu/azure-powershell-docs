---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: DFC277E2-C2C5-451D-9029-0D9054A53E82
updated_at: 11/03/2016 02:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricDeployedReplica.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricDeployedReplica.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a04d7fb81ddb4ca19a8c0101c71d7745ad5e082a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricDeployedReplica

## SYNOPSIS
Gets a Service Fabric replica on a node.

## SYNTAX

### Non-Adhoc (Default)
```
Get-ServiceFabricDeployedReplica [-NodeName] <String> [-ApplicationName] <Uri>
 [[-ServiceManifestName] <String>] [[-PartitionId] <Guid>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Adhoc
```
Get-ServiceFabricDeployedReplica [-NodeName] <String> [-Adhoc] [[-ServiceManifestName] <String>]
 [[-PartitionId] <Guid>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricDeployedReplica** cmdlet gets a Service Fabric replica deployed on a specified node.
This view may be different from the view returned by the [Get-ServiceFabricReplica](./Get-ServiceFabricReplica.md) cmdlet because the node has the most current view of the replica.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Get all deployed replicas
```
PS C:\>Get-ServiceFabricDeployedReplica -NodeName "Node01" -ApplicationName fabric:/MyApplication
```

This command gets all deployed replicas for application fabric:/MyApplication on node Node01.

## PARAMETERS

### -Adhoc
Indicates that the service runs in ad hoc mode.
In ad hoc mode, you manually activate the service host.

```yaml
Type: SwitchParameter
Parameter Sets: Adhoc
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName
Specifies the Uniform Resource Identifier (URI) of a Service Fabric application.
The cmdlet gets the replica for the application that has the URI that you specify.

```yaml
Type: Uri
Parameter Sets: Non-Adhoc
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NodeName
Specifies the name of a Service Fabric node.
The cmdlet gets replicas deployed on the node that you specify.

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
This is an additional filter to return the replica that belongs to that partition.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceManifestName
Specifies the name of a Service Fabric service manifest in the application specified by the *ApplicationName* parameter.
This parameter can be used to filter to only replicas in a specific service manifest.

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

### System.Uri, System.Guid, String
This cmdlet accepts a URI that represents the name of a Service Fabric application, or a string that represents a Service Fabric node name where replicas are deployed, or a GUID of a Service Fabric partition filter, or a string that represents a service manifest name filter.

## OUTPUTS

### System.Object
This cmdlet returns **DeployedServiceReplica** objects that represent replicas.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Get-ServiceFabricReplica](./Get-ServiceFabricReplica.md)
