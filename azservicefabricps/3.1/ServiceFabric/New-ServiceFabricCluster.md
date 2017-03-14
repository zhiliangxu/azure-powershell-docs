---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 17029E25-66BE-422A-8965-04990FAB833C
updated_at: 11/03/2016 09:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/New-ServiceFabricCluster.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/New-ServiceFabricCluster.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/01e9ebd12a5214c9c4f85a2b71b372181a0bf8a9
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# New-ServiceFabricCluster

## SYNOPSIS
Creates a Service Fabric cluster.

## SYNTAX

```
New-ServiceFabricCluster [-ClusterConfigurationFilePath] <String> -FabricRuntimePackagePath <String>
 [-NoCleanupOnFailure] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **New-ServiceFabricCluster** cmdlet creates a Service Fabric cluster based on a configuration file in JavaScript Object Notation (JSON) format and a Service Fabric runtime package CAB file.
The cmdlet orchestrates installations from the controller computer.

## EXAMPLES

### Example 1: Create a cluster
```
PS C:\>New-ServiceFabricCluster -ClusterConfigurationFilePath "D:\standalone\ClusterConfig.Unsecure.DevCluster.json" -FabricRuntimePackagePath "D:\deployanywhere\MicrosoftAzureServiceFabric.cab"
```

This command creates a cluster based on the input cluster configuration path and runtime CAB package.

### Example 2: Create a cluster without clean up if failures are encountered
```
PS C:\>New-ServiceFabricCluster -ClusterConfigurationFilePath "D:\standalone\ClusterConfig.Unsecure.DevCluster.json" -FabricRuntimePackagePath "D:\deployanywhere\MicrosoftAzureServiceFabric.cab" -NoCleanupOnFailure
```

This command creates a cluster based on the input cluster configuration path and runtime CAB package, and for deployment failure, Fabric resources are not cleaned up on the target computers.

## PARAMETERS

### -ClusterConfigurationFilePath
Specifies the path of the cluster configuration JSON file.

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

### -FabricRuntimePackagePath
Specifies the path of the Service Fabric package CAB file.

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

### -NoCleanupOnFailure
Indicates that the system should retain Fabric data if the cluster cannot fully come up.

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

[Remove-ServiceFabricCluster](./Remove-ServiceFabricCluster.md)
