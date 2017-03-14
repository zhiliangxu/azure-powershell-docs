---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 5960F91D-BFD2-4297-B7BE-5A325BCDEA0A
updated_at: 11/02/2016 06:11 AM
ms.date: 11/02/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricApplicationLoadInformation.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Get-ServiceFabricApplicationLoadInformation.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/945bc222fc1036fec4385fa64462f3b4fa439079
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-ServiceFabricApplicationLoadInformation

## SYNOPSIS
Gets application capacity parameters and load information for a Service Fabric application.

## SYNTAX

```
Get-ServiceFabricApplicationLoadInformation [-ApplicationName] <String> [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-ServiceFabricApplicationLoadInformation** cmdlet gets application capacity parameters and load information for a Service Fabric application.

The output of **Get-ServiceFabricApplicationLoadInformation** contains the following information: 

- Minimum Nodes: Minimum number of nodes specified for this application (from **Application Capacity** parameters). 
- Maximum Nodes: Maximum number of nodes specified for this application (from **Application Capacity** parameters). 
- Node Count: Number of nodes currently spanned by the application's child replicas. 
- Application Load Metric Information: Load information for each metric defined in **Application Capacity** parameters. 
For each metric that is defined, the output contains the following information: 
- Metric Name: Name of the metric. 
- Reservation Capacity: Cluster capacity that is reserved in the cluster for this application. 
- Application Load: Total Load of this application's child replicas. 
- Application Capacity: Maximum permitted value of Application Load.

## EXAMPLES

### Example 1: Get load information
```
PS C:\>Get-ServiceFabricApplicationLoadInformation -ApplicationName fabric:/MyApp
```

This command gets load information for the application fabric://MyApp.

## PARAMETERS

### -ApplicationName
Specifies a Service Fabric application.

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

### System.Fabric.Query.ApplicationLoadInformation

## NOTES

## RELATED LINKS

[Get-ServiceFabricClusterLoadInformation](./Get-ServiceFabricClusterLoadInformation.md)

[Get-ServiceFabricNodeLoadInformation](./Get-ServiceFabricNodeLoadInformation.md)

[Get-ServiceFabricPartitionLoadInformation](./Get-ServiceFabricPartitionLoadInformation.md)


