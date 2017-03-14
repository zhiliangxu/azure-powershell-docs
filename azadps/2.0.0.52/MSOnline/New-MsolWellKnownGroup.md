---
external help file: Microsoft.Online.Administration.Automation.PSModule.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 629EE8A1-A6F9-4923-94FC-C371CA0F4D5C
updated_at: 11/15/2016 05:11 AM
ms.date: 11/15/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/MSOnline/v1/New-MsolWellKnownGroup.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/MSOnline/v1/New-MsolWellKnownGroup.md
gitcommit: https://github.com/Azure/azure-docs-powershell-azuread/blob/2fc7c934766545163d747d78fd2431e341b5bd4f
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# New-MsolWellKnownGroup

## SYNOPSIS
Creates a well-known group.

## SYNTAX

```
New-MsolWellKnownGroup -WellKnownGroupName <String> [-TenantId <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **New-MsolWellKnownGroup** cmdlet creates a well-known group.

## EXAMPLES


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

### -WellKnownGroupName
Specifies a name for the well-known group. 

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
