---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 4290C7C9-446B-4A8F-BD52-5E2508700FFC
updated_at: 11/03/2016 09:11 AM
ms.date: 11/03/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/New-ServiceFabricNodeConfiguration.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/New-ServiceFabricNodeConfiguration.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/01e9ebd12a5214c9c4f85a2b71b372181a0bf8a9
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# New-ServiceFabricNodeConfiguration

## SYNOPSIS
Configures a node to join a Service Fabric cluster.

## SYNTAX

```
New-ServiceFabricNodeConfiguration [-ClusterManifestPath] <String> [-InfrastructureManifestPath <String>]
 [-FabricDataRoot <String>] [-FabricLogRoot <String>] [-FabricHostCredential <PSCredential>]
 [-RunFabricHostServiceAsManual] [-RemoveExistingConfiguration] [-BootstrapMSIPath <String>]
 [-UsingFabricPackage] [-FabricPackageRoot <String>] [-MachineName <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-ServiceFabricNodeConfiguration** cmdlet configures a node to join a Service Fabric cluster.
This cmdlet typically uses configuration information taken from a cluster manifest and then creates the settings required for the node to join the cluster.
The node will join the cluster as soon as the Service Fabric Host Service is started.

To manage Service Fabric clusters make sure you start your Windows PowerShell session by using the Run as administrator option.

## EXAMPLES

### Example 1: Configure a five-node development cluster
```
PS C:\>New-ServiceFabricNodeConfiguration -ClusterManifestPath "<samples>\\ConfigStore\Management\Deployment\ClusterManifest\Server\DevEnv-FiveNodes.xml"
```

This command configures a development cluster by using the DevEnv-FiveNodes.xml manifest from the Service Fabric samples.
That manifest configures a Service Fabric cluster of five nodes on your development computer.

## PARAMETERS

### -BootstrapMSIPath
Specifies the path of the bootstrap .msi file.
If you use this parameter, a self-baseline upgrade automatically occurs when you perform either a configure upgrade or fabric upgrade.

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

### -ClusterManifestPath
Specifies the path of a Service Fabric cluster manifest.
The cmdlet creates a cluster configuration based on the specified manifest.

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

### -FabricDataRoot
Specifies the path where the Service Fabric runtime stores the internal data needed to operate a cluster.

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

### -FabricHostCredential
Specifies a **PSCredential** object for the Service Fabric Host Service.
To obtain a **PSCredential** object, use the [Get-Credential](http://go.microsoft.com/fwlink/?LinkID=293936) cmdlet.
For more information, type `Get-Help Get-Credential`.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FabricLogRoot
Specifies the path for the Service Fabric trace logs.

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

### -FabricPackageRoot
This parameter is reserved for future use.

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

### -InfrastructureManifestPath
Specifies the path of the infrastructure manifest.
In Azure, this is the path to the .csdef and .cscfg files.

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

### -MachineName
Specifies the computer that will host the configuration.
You can use either the computer name or the computer IP address.
For example:

`-MachineName "192.168.1.1"`

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

### -RemoveExistingConfiguration
Indicates that this cmdlet removes any existing configurations.

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

### -RunFabricHostServiceAsManual
Indicates that the Fabric Host service must be started manually.

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

### -UsingFabricPackage
Indicates that node configurations should use the xcopy/CAB runtime package.
This is used when MSI is not installed and we are using a client package to execute the cmdlet.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
**New-ServiceFabricNodeConfiguration** does not accept pipelined input.

## OUTPUTS

###  
**New-ServiceFabricNodeConfiguration** returns status information as a string value.

## NOTES

## RELATED LINKS

[Get-Credential](http://go.microsoft.com/fwlink/?LinkID=293936)

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Remove-ServiceFabricNodeConfiguration](./Remove-ServiceFabricNodeConfiguration.md)

[Update-ServiceFabricNodeConfiguration](./Update-ServiceFabricNodeConfiguration.md)
