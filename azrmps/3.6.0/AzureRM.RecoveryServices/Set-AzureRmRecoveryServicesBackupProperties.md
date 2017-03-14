---
external help file: Microsoft.Azure.Commands.RecoveryServices.ARM.dll-Help.xml
ms.assetid: C635D723-0F03-4EF8-9435-24DBE0859899
online version:
schema: 2.0.0
updated_at: 03/11/2017 23:03 PM
ms.date: 03/11/2017
content_git_url: https://github.com/Azure/azure-docs-powershell/blob/master/azureps-cmdlets-docs/ResourceManager/AzureRM.RecoveryServices/v2.6.0/Set-AzureRmRecoveryServicesBackupProperties.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell/blob/master/azureps-cmdlets-docs/ResourceManager/AzureRM.RecoveryServices/v2.6.0/Set-AzureRmRecoveryServicesBackupProperties.md
gitcommit: https://github.com/Azure/azure-docs-powershell/blob/bc71000aa3c7f754b95442dcc415a7324626a15c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Set-AzureRmRecoveryServicesBackupProperties

## SYNOPSIS
Sets the properties for backup management.

## SYNTAX

```
Set-AzureRmRecoveryServicesBackupProperties -Vault <ARSVault>
 [-BackupStorageRedundancy <AzureRmRecoveryServicesBackupStorageRedundancyType>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmRecoveryServicesBackupProperties** cmdlet sets backup storage properties for a Recovery Services vault.

## EXAMPLES

### Example 1: Set GeoRedundant storage for a vault
```
PS C:\> $Vault01 = Get-AzureRmRecoveryServicesVault -Name "TestVault"
PS C:\> Set-AzureRmRecoveryServicesBackupProperties -Vault $Vault01 -BackupStorageRedundancy GeoRedundant
```

The first command gets the vault named TestVault, and then stores it in the $Vault01 variable.

The second command sets the backup storage redundancy for $Vault01 to GeoRedundant.

## PARAMETERS

### -Vault
Specifies the name of the vault.
The vault must be an **AzureRmRecoveryServicesVault** object.

```yaml
Type: ARSVault
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BackupStorageRedundancy
Specifies the backup storage redundancy type.

```yaml
Type: AzureRmRecoveryServicesBackupStorageRedundancyType
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

[Get-AzureRmRecoveryServicesBackupProperties](./Get-AzureRmRecoveryServicesBackupProperties.md)

[Get-AzureRmRecoveryServicesVault](./Get-AzureRmRecoveryServicesVault.md)


