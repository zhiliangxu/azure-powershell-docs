---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 1D699B1C-8047-4106-ABFF-8CDF9FEF142C
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Test-ServiceFabricConfiguration.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Test-ServiceFabricConfiguration.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Test-ServiceFabricConfiguration

## SYNOPSIS
Validates cluster configuration and tests whether deployment can succeed.

## SYNTAX

```
Test-ServiceFabricConfiguration [-ClusterConfigurationFilePath] <String> [-FabricRuntimePackagePath <String>]
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-ServiceFabricConfiguration** cmdlet validates the cluster configuration and tests whether deployment can succeed for the target computers in the configuration from the controller.
Specify the configuration file in JavaScript Object Notation (JSON) format.

## EXAMPLES

### Example 1: Validate deployment
```
PS C:\>Test-ServiceFabricConfiguration -ClusterConfigurationFilePath "D:\standalone\ClusterConfig.Unsecure.DevCluster.json"
```

This command validates that the cluster deploys from the current computer by using the specified configuration.

### Example 2: Validate deployment and runtime CAB file
```
PS C:\>Test-ServiceFabricConfiguration -ClusterConfigurationFilePath "D:\standalone\ClusterConfig.Unsecure.DevCluster.json" -FabricRuntimePackagePath "D:\deployanywhere\MicrosoftAzureServiceFabric.cab"
```

This command validates that the cluster deploys from the current computer by using this configuration.
The command also validates whether the runtime CAB can be used to deploy the cluster.

## PARAMETERS

### -ClusterConfigurationFilePath
Specifies the path of the JSON cluster configuration file.

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
Specifies the path of the Service Fabric runtime package CAB file.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)
