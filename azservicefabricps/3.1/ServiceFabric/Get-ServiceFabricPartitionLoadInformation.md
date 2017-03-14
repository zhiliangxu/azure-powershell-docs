---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: A72F38C0-29A8-4933-B7DE-EE98B1F098EB
updated_at: 11/03/2016 02:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricPartitionLoadInformation.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricPartitionLoadInformation.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/a04d7fb81ddb4ca19a8c0101c71d7745ad5e082a
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricPartitionLoadInformation

## SYNOPSIS
Gets the load reports for a Service Fabric partition.

## SYNTAX

```
Get-ServiceFabricPartitionLoadInformation [-PartitionId] <Guid> [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricPartitionLoadInformation** cmdlet gets the load reports for a Service Fabric partition.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Get the reported load for a service partition
```
PS C:\>$ToDoPartition01 = Get-ServiceFabricPartition -ServiceName fabric:/myapp/persistenttodolist/svc1
PS C:\> Get-ServiceFabricPartitionLoadInformation -PartitionId $ToDoPartition01.PartitionId
```

The first command uses the [Get-ServiceFabricPartition](./Get-ServiceFabricPartition.md) cmdlet to get the service partition object for the named service, and then stores the object in the $ToDoPartition01 variable.

The second command specifies the **PartitionId** property of the object stored in $ToDoPartition01 to get the reported load of the partition.

## PARAMETERS

### -PartitionId
Specifies the ID of a Service Fabric partition.

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

### System.Guid
This cmdlet accepts the ID of a Service Fabric partition.

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.Query.PartitionLoadInformation** object for a Service Fabric partition.

## NOTES

## RELATED LINKS

[Get-ServiceFabricPartition](./Get-ServiceFabricPartition.md)

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)
