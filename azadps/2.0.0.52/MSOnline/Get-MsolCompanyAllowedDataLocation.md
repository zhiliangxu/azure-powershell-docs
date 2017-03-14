---
external help file: Microsoft.Online.Administration.Automation.PSModule.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 85832284-6D5C-4003-BE79-DA7D985B9056
updated_at: 11/09/2016 06:11 AM
ms.date: 11/09/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/MSOnline/v1/Get-MsolCompanyAllowedDataLocation.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/MSOnline/v1/Get-MsolCompanyAllowedDataLocation.md
gitcommit: https://github.com/Azure/azure-docs-powershell-azuread/blob/1f9ce90a071efd51795186ba3f8b8d76905a96c3
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-MsolCompanyAllowedDataLocation

## SYNOPSIS
Get the current allowed data locations of a company from Azure Active Directory.

## SYNTAX

```
Get-MsolCompanyAllowedDataLocation [-TenantId <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MsolCompanyAllowedDataLocation** cmdlet gets all the current allowed data locations of a company from Azure Active Directory.
If a company has not opted in the multinational feature or has no allowed data locations, the cmdlet returns an empty list.

## EXAMPLES

### Example 1: Get current allowed data locations
```
PS C:\> Get-MsolCompanyAllowedDataLocation
```

This command returns all the current allowed data locations of a company from Azure Active Directory.

## PARAMETERS

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

### Microsoft.Online.Administration.AllowedDataLocation
This cmdlet returns all the current allowed data locations of a company from Azure Active Directory.
If a company has not opted in the multinational feature or has no allowed data locations, then the cmdlet will return an empty list.

## NOTES

## RELATED LINKS
[Set-MsolCompanyAllowedDataLocation](./Set-MsolCompanyAllowedDataLocation.md)
