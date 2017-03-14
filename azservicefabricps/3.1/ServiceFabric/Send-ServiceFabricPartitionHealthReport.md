---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 56FED04E-8162-4BD9-83BA-C4A79DC46B57
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Send-ServiceFabricPartitionHealthReport.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Send-ServiceFabricPartitionHealthReport.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Send-ServiceFabricPartitionHealthReport

## SYNOPSIS
Sends a health report on a Service Fabric service partition.

## SYNTAX

```
Send-ServiceFabricPartitionHealthReport [-PartitionId] <Guid> -HealthState <HealthState> -SourceId <String>
 -HealthProperty <String> [-Description <String>] [-TimeToLiveSec <Int32>] [-RemoveWhenExpired]
 [-SequenceNumber <Int64>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Send-ServiceFabricPartitionHealthReport** cmdlet sends a health report on a Service Fabric service partition.

The partition must already exist in the health store.
To check whether it exists, use the [Get-ServiceFabricPartitionHealth](./Get-ServiceFabricPartitionHealth.md) cmdlet and specify the partition ID.
Alternatively, you can use the [Get-ServiceFabricServiceHealth](./Get-ServiceFabricServiceHealth.md) cmdlet and check the partition health states section to find the partition.

The cmdlet sends the report after an interval specified by the *HealthReportSendIntervalInSec* parameter of the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.
The cluster connection must be kept alive during this time.

The cmdlet may return success, but the report is sent asynchronously, so its processing may fail.
To see whether the report was applied in the health store, use the **Get-ServiceFabricPartitionHealth** cmdlet and check that the report appears in the HealthEvents section.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the **Connect-ServiceFabricCluster** cmdlet.

## EXAMPLES

### Example 1: Report Error health report with infinite TTL
```
PS C:\>Send-ServiceFabricPartitionHealthReport -PartitionId 869dd2e9-fdda-42a5-ad96-4b71c795dfd3 -SourceId "MyWatchdog" -HealthProperty "Availability" -HealthState Error
```

This command sends a health report on the specified partition from the source MyWatchdog.
The health report contains information about the health property **Availability** in an Error health state, with infinite TTL.

### Example 2: Report Warning valid for specified health report with set TTL and remove it when it expiresvalid for specified
```
PS C:\>Send-ServiceFabricPartitionHealthReport -PartitionId 869dd2e9-fdda-42a5-ad96-4b71c795dfd3 -SourceId "MyWatchdog" -HealthProperty "ReplicaSet" -HealthState Warning -TimeToLiveSec 10 -RemoveWhenExpired -Description "The communication between replicas have high latency."
```

This command sends a health report on the specified partition from the source MyWatchdog.
The health report contains information about the health property **ReplicaSet** in a Warning health state with 10 seconds TTL.
The report is marked for removal on expiration.

## PARAMETERS

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

### -PartitionId
Specifies the ID of a Service Fabric partition.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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
If you specify a sequence number, that value must be higher than any previous sequence number set on the same **SourceId** and **HealthProperty**, or the report will be rejected due to staleness.

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

### System.Guid, String, System.Fabric.HealthState
This cmdlet accepts the ID of a Service Fabric partition, or the source ID and health property as a string, or a **HealthState** value that represents the health state of the report.

## OUTPUTS

### None
This cmdlet does not return any output.

## NOTES

## RELATED LINKS

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricPartitionHealth](./Get-ServiceFabricPartitionHealth.md)

[Get-ServiceFabricServiceHealth](./Get-ServiceFabricServiceHealth.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)
