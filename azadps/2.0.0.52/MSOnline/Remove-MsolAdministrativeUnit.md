---
external help file: Microsoft.Online.Administration.Automation.PSModule.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: BA22F11F-5010-421E-A9A9-680C9EA014B4
updated_at: 11/05/2016 06:11 AM
ms.date: 11/05/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/MSOnline/v1/Remove-MsolAdministrativeUnit.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/MSOnline/v1/Remove-MsolAdministrativeUnit.md
gitcommit: https://github.com/Azure/azure-docs-powershell-azuread/blob/3c22ad9f927dcfe00a363b1a2c343fc086da2ac5
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Remove-MsolAdministrativeUnit

## SYNOPSIS
Deletes an administrative unit from Azure Active Directory.

## SYNTAX

```
Remove-MsolAdministrativeUnit -ObjectId <Guid> [-Force] [-TenantId <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-MsolAdministrativeUnit** cmdlet deletes an administrative unit from Azure Active Directory.

## EXAMPLES

### Example 1: Remove an administrative unit

```
PS C:\> $AdminstrativeUnit = Get-MsolAdministrativeUnit -SearchString "West Coast"
PS C:\> Remove-MsolAdministrativeUnit -ObjectId $AdminstrativeUnit.ObjectId -Force
```

The first command gets an administrative unit that matches a search string by using the [Get-MsolAdministrativeUnit](./Get-MsolAdministrativeUnit.md) cmdlet.
The command stores the administrative unit in the $AdminstrativeUnit variable.

The second command deletes the administrative unit.
The command specifies the administrative unit by using the object ID of $AdminstrativeUnit.
The command specifies the _Force_ parameter.
It does not prompt for comfirmation.


## PARAMETERS

### -ObjectId
Specifies the unique ID of the administrative unit to remove.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Indicates that this cmdlet does not prompt you for confirmation.

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

### -TenantId
Specifies the unique ID of the tenant on which to perform the operation.
The default value is the tenant of the current user.
This parameter applies only to partner users.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
[Get-MsolAdministrativeUnit](./Get-MsolAdministrativeUnit.md)

[New-MsolAdministrativeUnit](./New-MsolAdministrativeUnit.md)

[Set-MsolAdministrativeUnit](./Set-MsolAdministrativeUnit.md)
