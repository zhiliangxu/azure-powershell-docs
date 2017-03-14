---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 97D767C4-EAD7-4D19-A085-2BD1F992C099
updated_at: 11/04/2016 01:11 AM
ms.date: 11/04/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Stop-ServiceFabricTestCommand.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Stop-ServiceFabricTestCommand.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/79292df3c325e2a04987a559a1141637740ddd4c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Stop-ServiceFabricTestCommand

## SYNOPSIS
Cancels a Service Fabric test command.

## SYNTAX

```
Stop-ServiceFabricTestCommand -OperationId <Guid> [-ForceCancel] [-Force] [-TimeoutSec <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-ServiceFabricTestCommand** cmdlet cancels an Azure Service Fabric test command.
Specify the ID of the operation that you provided when you initiated the test command.
To run this cmdlet, **FaultAnalysisService** must be enabled.

If you do not specify the *Force* parameter, this cmdlet cancels the command and cleans up state information.
The command closes with a state of RollingBack during cleanup.
The final state of the command is Cancelled.

Important Note: If *Force* is true, state may be left behind.
[Remove-ServiceFabricTestState](./Remove-ServiceFabricTestState.md) should be invoked to remove state that may have been left behind.

TestCommandProgressState.RollingBack indicates the system is cleaning up the internal system state caused by executing the command.
It does not restore data if the test command was to cause data loss.
For example, if you call [Start-ServiceFabricPartitionDataLoss](./Start-ServiceFabricPartitionDataLoss.md) and then call this cmdlet, the system will only clean up its internal state from running the command.
It will not restore the target partition's data if the command progressed far enough to cause data loss.

## EXAMPLES

### Example 1: Cancel an operation
```
PS C:\>Stop-ServiceFabricTestCommand -OperationId a268cc73-2e30-462b-b3df-3a0d30e5b330
```

This command cancels an operation that has the *OperationId* a268cc73-2e30-462b-b3df-3a0d30e5b330.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to be cancelled.
The use of this parameter may leave state information behind.
The final state of the command is ForceCancelled.

You can specify *Force* only if the test command has a state of RollingBack.
The command has that state only if you previously ran this cmdlet without *Force* specified, or if the test command rolls back due to a fatal error.

We do not recommend specifying *Force* unless the command is not proceeding.

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

### -ForceCancel
You can specify *Force* only if the test command has a state of RollingBack.
The command has that state only if you previously ran this cmdlet without *Force* specified, or if the test command rolls back due to a fatal error.

We do not recommend specifying *Force* unless the command is not proceeding.

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

### -OperationId
Specifies a unique identifier for the command that this cmdlet cancels.
You assign this value when you initiated the command.

```yaml
Type: Guid
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-ServiceFabricTestCommandStatusList](./Get-ServiceFabricTestCommandStatusList.md)

[Remove-ServiceFabricTestState](./Remove-ServiceFabricTestState.md)

[Start-ServiceFabricPartitionDataLoss](./Start-ServiceFabricPartitionDataLoss.md)
