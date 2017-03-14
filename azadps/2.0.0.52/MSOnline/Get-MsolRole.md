---
external help file: Microsoft.Online.Administration.Automation.PSModule.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 430D359B-200B-4EA6-A6B7-D347A0264CC9
updated_at: 11/10/2016 06:11 AM
ms.date: 11/10/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/MSOnline/v1/Get-MsolRole.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/MSOnline/v1/Get-MsolRole.md
gitcommit: https://github.com/Azure/azure-docs-powershell-azuread/blob/a602340dee47e7edf41f6c5af3edb93e03ac1b45
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Get-MsolRole

## SYNOPSIS
Gets administrator roles.

## SYNTAX

### ListRoles__0 (Default)
```
Get-MsolRole [-TenantId <Guid>] [<CommonParameters>]
```

### GetRole__0
```
Get-MsolRole -ObjectId <Guid> [-TenantId <Guid>] [<CommonParameters>]
```

### GetRoleByName__0
```
Get-MsolRole -RoleName <String> [-TenantId <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MsolRole** cmdlet gets a list of administrator roles.

## EXAMPLES

### Example 1: Get administrator roles for the company
```
PS C:\> Get-MsolRole
```

This command gets administrator roles for the company.

## PARAMETERS

### -ObjectId
Specifies the unique object ID of the role to retrieve.

```yaml
Type: Guid
Parameter Sets: GetRole__0
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoleName
Specifies the name of the role to retrieve.

```yaml
Type: String
Parameter Sets: GetRoleByName__0
Aliases:

Required: True
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

### Microsoft.Online.Administration.Role
This cmdlet returns role objects that contain the following fields:

* Description. A description of the role.

* IsEnabled. Whether or not the role is enabled.

* IsSystem. Whether or not the role was created by Azure Active Directory.

* Name. The name of the role.

* ObjectId. The unique ID of the role.

## NOTES

## RELATED LINKS
