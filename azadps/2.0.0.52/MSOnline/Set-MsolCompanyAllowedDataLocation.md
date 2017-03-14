---
external help file: Microsoft.Online.Administration.Automation.PSModule.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 326AC6B3-327F-4A2C-9018-C969949606A0
updated_at: 11/09/2016 06:11 AM
ms.date: 11/09/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/MSOnline/v1/Set-MsolCompanyAllowedDataLocation.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/MSOnline/v1/Set-MsolCompanyAllowedDataLocation.md
gitcommit: https://github.com/Azure/azure-docs-powershell-azuread/blob/1f9ce90a071efd51795186ba3f8b8d76905a96c3
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Set-MsolCompanyAllowedDataLocation

## SYNOPSIS
Sets an allowed data location for a service type for a company in Azure Active Directory.

## SYNTAX

```
Set-MsolCompanyAllowedDataLocation -ServiceType <String> -Location <String> [-IsDefault <Boolean>]
 [-InitialDomain <String>] [-Overwrite <Boolean>] [-TenantId <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-MsolCompanyAllowedDataLocation** cmdlet attempts to set an allowed data location or update an existing allowed data location for a service type for a company in v1.

## EXAMPLES

### Example 1: Set an allowed data location
```
PS C:\> Set-MsolCompanyAllowedDataLocation -ServiceType "MicrosoftCommunicationsOnline" -Location "EUR"
```

This command attempts to set an allowed data location for the **MicrosoftCommunicationsOnline** service type for Europe for a company.
The **MicrosoftCommunicationsOnline** service type is also known as Skype for Business.

## PARAMETERS

### -ServiceType
Specifies the service type of the allowed data location to set.

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

### -Location
Specifies the allowed data location of a service type.
This value must match one of the current supported data locations by the service type.
Otherwise, this cmdlet returns an error.

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

### -IsDefault
Specifies whether the location is the default allowed data location for the given service type.
There is exactly one default allowed data location per service type.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InitialDomain
Specifies the initial MOERA domain to reserve for SharePoint service provisioning purpose.
In v1, specify a valid DNS domain fully qualified domain name.

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

### -Overwrite
Indicates whether to overwrite an existing allowed data location if one already exists for the same {ServiceType, Location} pair for the company.

```yaml
Type: Boolean
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

## NOTES

## RELATED LINKS
[Get-MsolCompanyAllowedDataLocation](./Get-MsolCompanyAllowedDataLocation.md)
