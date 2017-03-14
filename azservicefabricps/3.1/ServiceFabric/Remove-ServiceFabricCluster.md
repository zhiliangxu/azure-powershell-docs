---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 1F7B207A-83D7-45F1-AC0C-E3222D98D54D
updated_at: 11/03/2016 09:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Remove-ServiceFabricCluster.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Remove-ServiceFabricCluster.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/01e9ebd12a5214c9c4f85a2b71b372181a0bf8a9
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Remove-ServiceFabricCluster

## SYNOPSIS
Removes a Service Fabric cluster.

## SYNTAX

```
Remove-ServiceFabricCluster [-ClusterConfigurationFilePath] <String> [-DeleteLog] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-ServiceFabricCluster** cmdlet removes a Service Fabric cluster based on a cluster configuration file in JavaScript Object Notation (JSON) format.
The configuration includes target computers from which the cmdlet removes Fabric nodes.

## EXAMPLES

### Example 1: Remove a cluster
```
PS C:\>Remove-ServiceFabricCluster -ClusterConfigurationFilePath "D:\standalone\ClusterConfig.Unsecure.DevCluster.json"
```

Removes the Service Fabric cluster nodes based on computers specified in the cluster configuration file.

## PARAMETERS

### -ClusterConfigurationFilePath
Specifies the path of the cluster configuration JSON file.
The configuration describes target computers from which Fabric nodes are removed.

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

### -DeleteLog
Indicates that the cmdlet removes log files as part of cluster removal.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[New-ServiceFabricCluster](./New-ServiceFabricCluster.md)
