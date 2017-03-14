---
external help file: Microsoft.Online.Administration.Automation.PSModule.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: D0D10A71-D935-4D24-B671-F8E0A5D8979D
updated_at: 11/05/2016 06:11 AM
ms.date: 11/05/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/MSOnline/v1/New-MsolAdministrativeUnit.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/MSOnline/v1/New-MsolAdministrativeUnit.md
gitcommit: https://github.com/Azure/azure-docs-powershell-azuread/blob/3c22ad9f927dcfe00a363b1a2c343fc086da2ac5
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# New-MsolAdministrativeUnit

## SYNOPSIS
Adds a new administrative unit to Azure Active Directory.

## SYNTAX

```
New-MsolAdministrativeUnit [-DisplayName <String>] [-Description <String>] [-TenantId <Guid>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-MsolAdministrativeUnit** cmdlet adds a new administrative unit to Azure Active Directory.

## EXAMPLES

### Example 1: Create an administrative unit

```
PS C:\> New-MsolAdministrativeUnit -DisplayName "West Coast" -Description "West Coast region"
```

This command creates a administrative unit called West Coast that has a description of West Coast region.

## PARAMETERS

### -DisplayName
Specifies a display name for the administrative unit.

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

### -Description
Specifies a description for the administrative unit.

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

### Microsoft.Online.Administration.AdministrativeUnit
Will return the new administrative unit that was created.

## NOTES

## RELATED LINKS
[Get-MsolAdministrativeUnit](./Get-MsolAdministrativeUnit.md)

[Remove-MsolAdministrativeUnit](./Remove-MsolAdministrativeUnit.md)

[Set-MsolAdministrativeUnit](./Set-MsolAdministrativeUnit.md)
