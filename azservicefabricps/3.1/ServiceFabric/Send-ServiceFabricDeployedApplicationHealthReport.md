---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 83AFB00A-7A9E-4DCB-9000-720D3FCDB31C
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Send-ServiceFabricDeployedApplicationHealthReport.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Send-ServiceFabricDeployedApplicationHealthReport.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Send-ServiceFabricDeployedApplicationHealthReport

## SYNOPSIS
Sends a health report on a Service Fabric application deployed on a node.

## SYNTAX

```
Send-ServiceFabricDeployedApplicationHealthReport [-ApplicationName] <Uri> [-NodeName] <String>
 -HealthState <HealthState> -SourceId <String> -HealthProperty <String> [-Description <String>]
 [-TimeToLiveSec <Int32>] [-RemoveWhenExpired] [-SequenceNumber <Int64>] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Send-ServiceFabricDeployedApplicationHealthReport** cmdlet sends a health report for a health event on a Service Fabric application deployed on a node.

The deployed application must already exist in the health store.
To check whether the application exists on a node, use the [Get-ServiceFabricDeployedApplicationHealth](./Get-ServiceFabricDeployedApplicationHealth.md) cmdlet.
Alternatively, you can use the [Get-ServiceFabricApplicationHealth](./Get-ServiceFabricApplicationHealth.md) cmdlet and check the DeployedApplicationHealthStates section to find the node.

The cmdlet sends the report after an interval specified by the *HealthReportSendIntervalInSec* parameter of the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.
The cluster connection must be kept alive during this time.
The command is evaluated on the client without reference to running on the health store.
The report may not be applied in health store even if the command returns success.
For example, the health store may reject the report because of an invalid parameter, like a stale sequence number.

To see whether the report was applied in the health store, use the **Get-ServiceFabricDeployedApplicationHealth** cmdlet and check that the report appears in the HealthEvents section.

To manage Service Fabric clusters, start Windows PowerShell by using the Run as administrator option.
Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the **Connect-ServiceFabricCluster** cmdlet and then the [Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md) cmdlet.

## EXAMPLES

### Example 1: Report Error health report with infinite TTL
```
PS C:\>Send-ServiceFabricDeployedApplicationHealthReport -ApplicationName fabric:/MyApplication -NodeName "Node01" -HealthProperty "Availability" -HealthState Error -SourceId "MyWatchdog"
```

This command sends a health report for the application named fabric:/MyApplication on the node named Node01 from the source MyWatchdog.
The health report contains information about the health property **Availability** in an Error health state, with infinite TTL.

### Example 2: Report Warning valid for specified TTL
```
PS C:\>Send-ServiceFabricDeployedApplicationHealthReport -ApplicationName fabric:/MyApplication -NodeName "Node01"-HealthProperty "Availability" -HealthState Warning -SourceId "MyWatchdog" -RemoveWhenExpired -TimeToLiveSec 10
```

This command sends a health report for the application named fabric:/MyApplication on the node named Node01 from the source MyWatchdog.
The health report contains information about the health property **Availability** in a Warning health state, with 10 seconds TTL.
The report is removed when it expires.

## PARAMETERS

### -ApplicationName
Specifies the Uniform Resource Identifier (URI) of a Service Fabric application.
The cmdlet sends a health report for the application that has the URI that you specify.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies human readable information about the condition that triggered the report.
The *SourceId*, *HealthProperty*, and *HealthState* parameters fully describe the report.

The maximum string length for the description is 4096 characters.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HealthProperty
Specifies the property of the report.
Together with the *SourceId* parameter, this property uniquely identifies the report.
The report overrides any previous reports with the same values for the *SourceId* and *HealthProperty* parameters on the same entity.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HealthState
Specifies a **HealthState** object that represents the reported health state.

```yaml
Type: HealthState
Parameter Sets: (All)
Aliases:
Accepted values: Invalid, Ok, Warning, Error, Unknown

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NodeName
Specifies the name of a Service Fabric node.
The cmdlet sends a health report for the application on the node that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemoveWhenExpired
Indicates that the report is removed from the health store when it expires.
If you do not specify this parameter, the entity is considered in Error state when the report time to live expires.
The reports that are removed when expired can be used for conditions that are only valid for a period of time or for clearing reports from Health Store.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SequenceNumber
Specifies the sequence number associated with the health report.
If you do not specify a value for this parameter, the sequence number is set automatically.
If you specify a sequence number, that value must be higher than any previous sequence number set on the same *SourceId* and *HealthProperty*, or the report will be rejected due to staleness.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceId
Specifies the identifier of the source that triggered the report.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TimeToLiveSec
Specifies the Time to Live (TTL) of the report in seconds.
When the TTL expires, the report is removed from the health store if the *RemoveWhenExpired* parameter is specified.
Otherwise, the entity is evaluated at Error because of the expired report.
The default value is Infinite.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### System.Uri, String, System.Fabric.HealthState
This cmdlet accepts a URI that represents the name of a Service Fabric application, or the name of a Service Fabric node, or the source ID and health property as a string, or a **HealthState** value that represents the health state of the report.

## OUTPUTS

### None
This cmdlet does not return any output.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricDeployedApplicationHealth](./Get-ServiceFabricDeployedApplicationHealth.md)

[Get-ServiceFabricApplicationHealth](./Get-ServiceFabricApplicationHealth.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)
