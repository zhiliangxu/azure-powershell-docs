---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: A315ECB3-FC8C-451B-85B0-C3C4887B78C9
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Resolve-ServiceFabricService.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Resolve-ServiceFabricService.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Resolve-ServiceFabricService

## SYNOPSIS
Retrieves the replica or instance address of a Service Fabric service.

## SYNTAX

### Singleton NonRefresh (Default)
```
Resolve-ServiceFabricService [-PartitionKindSingleton] [-ServiceName] <Uri>
 [-PreviousResult <ResolvedServicePartition>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Singleton ForceRefresh
```
Resolve-ServiceFabricService [-PartitionKindSingleton] [-ServiceName] <Uri> [-ForceRefresh]
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

### UniformInt64 ForceRefresh
```
Resolve-ServiceFabricService [-PartitionKindUniformInt64] [-ServiceName] <Uri> [-PartitionKey] <String>
 [-ForceRefresh] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### UniformInt64 NonRefresh
```
Resolve-ServiceFabricService [-PartitionKindUniformInt64] [-ServiceName] <Uri> [-PartitionKey] <String>
 [-PreviousResult <ResolvedServicePartition>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Named ForceRefresh
```
Resolve-ServiceFabricService [-PartitionKindNamed] [-ServiceName] <Uri> [-PartitionKey] <String>
 [-ForceRefresh] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Named NonRefresh
```
Resolve-ServiceFabricService [-PartitionKindNamed] [-ServiceName] <Uri> [-PartitionKey] <String>
 [-PreviousResult <ResolvedServicePartition>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Resolve-ServiceFabricService** cmdlet retrieves the replica or instance address of a Service Fabric service.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

## EXAMPLES

### Example 1: Resolve addresses
```
PS C:\>Resolve-ServiceFabricService -PartitionKindUniformInt64 -ServiceName fabric:/myApp/myService -PartitionKey "0"
```

This command retrieves the addresses of a uniform Int64 partition mapped to by partition key 0 in a service named fabric:/myApp/myService.

## PARAMETERS

### -ForceRefresh
Indicates that the cmdlet forces the local cache of resolved addresses to refresh.

```yaml
Type: SwitchParameter
Parameter Sets: Singleton ForceRefresh, UniformInt64 ForceRefresh, Named ForceRefresh
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionKey
Specifies the partition key for the Service Fabric service.

```yaml
Type: String
Parameter Sets: UniformInt64 ForceRefresh, UniformInt64 NonRefresh, Named ForceRefresh, Named NonRefresh
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionKindNamed
Indicates that the Service Fabric service is a named partition.

```yaml
Type: SwitchParameter
Parameter Sets: Named ForceRefresh, Named NonRefresh
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionKindSingleton
Indicates that the Service Fabric service is a singleton partition.

```yaml
Type: SwitchParameter
Parameter Sets: Singleton NonRefresh, Singleton ForceRefresh
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionKindUniformInt64
Indicates that the Service Fabric service is a UniformInt64 partition.

```yaml
Type: SwitchParameter
Parameter Sets: UniformInt64 ForceRefresh, UniformInt64 NonRefresh
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreviousResult
Specifies the previous resolve service partition results.

```yaml
Type: ResolvedServicePartition
Parameter Sets: Singleton NonRefresh, UniformInt64 NonRefresh, Named NonRefresh
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Specifies the URI of a Service Fabric service.

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

### System.Uri, String, System.Fabric.ResolvedServicePartition
This cmdlet accepts a URI that represents the name of a Service Fabric service, or the partition key as a string, or a **System.Fabric.ResolvedServicePartition** object that represents a previous resolve service partition result.

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.ResolvedServicePartition** object that represents the Service Fabric resolved service partition.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Get-ServiceFabricService](./Get-ServiceFabricService.md)

[New-ServiceFabricService](./New-ServiceFabricService.md)

[Remove-ServiceFabricService](./Remove-ServiceFabricService.md)

[Update-ServiceFabricService](./Update-ServiceFabricService.md)
