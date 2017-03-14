---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 57A27B58-D6EC-464F-97FA-63F5D0391954
updated_at: 11/02/2016 06:11 AM
ms.date: 11/02/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Add-ServiceFabricNode.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Add-ServiceFabricNode.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/945bc222fc1036fec4385fa64462f3b4fa439079
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Add-ServiceFabricNode

## SYNOPSIS
Adds a Service Fabric node to a cluster.

## SYNTAX

```
Add-ServiceFabricNode [-NodeName] <String> -NodeType <String> -IpAddressOrFQDN <String> -UpgradeDomain <String>
 -FaultDomain <String> -FabricRuntimePackagePath <String> [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-ServiceFabricNode** adds a Service Fabric node to a cluster.
You must run this cmdlet on the computer that you want to add.

## EXAMPLES

### Example 1: Add a node to a cluster
```
PS C:\>Add-ServiceFabricNode -NodeName "N011" -NodeType "NodeType0" -IpAddressOrFQDN "10.10.100.100" -UpgradeDomain "ud5" -FaultDomain "fd:/dc5/r0" -FabricRuntimePackagePath "D:\deployanywhere\MicrosoftAzureServiceFabric.cab"
```

This command adds the specified node to a cluster.

### Example 2: Add a node to a cluster secured with a group-managed service account
```
PS C:\>Add-ServiceFabricNode -NodeName "N011" -NodeType "NodeType1" -IpAddressOrFQDN "mycluster.cloudapp.net:19000" -UpgradeDomain "UD5" -FaultDomain "fd:/dc5/r0" -FabricRuntimePackagePath ".\MicrosoftAzureServiceFabric.cab"
```

This command adds a node to a cluster secured with a group-managed account.

## PARAMETERS

### -FabricRuntimePackagePath
Specifies the path of the .cab file.

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

### -FaultDomain
Specifies the fault domain of the node.

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

### -IpAddressOrFQDN
Specifies the IP address or fully qualified domain name (FQDN) of the node.

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

### -NodeName
Specifies the name of the node that this cmdlet adds.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeType
Specifies the type of node that this cmdlet adds.

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

### -UpgradeDomain
Specifies the upgrade domain for the node.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String
This cmdlet accepts a string for the name of a Service Fabric node, node type, IP address of the machine to add, upgrade domain, fault domain, and Fabric package source path.

## OUTPUTS

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Disable-ServiceFabricNode](./Disable-ServiceFabricNode.md)

[Enable-ServiceFabricNode](./Enable-ServiceFabricNode.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Remove-ServiceFabricNode](./Remove-ServiceFabricNode.md)

[Restart-ServiceFabricNode](./Restart-ServiceFabricNode.md)

[Start-ServiceFabricNode](./Start-ServiceFabricNode.md)

[Stop-ServiceFabricNode](./Stop-ServiceFabricNode.md)
