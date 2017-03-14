---
external help file: Microsoft.Open.AzureAD16.Graph.PowerShell.dll-Help.xml
ms.assetid: 18A501C7-DFDE-4F4D-A82C-6AA855EB5C33
online version:
schema: 2.0.0
updated_at: 12/06/2016 04:12 AM
ms.date: 12/06/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/v2/Remove-AzureADDeviceRegisteredUser.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/v2/Remove-AzureADDeviceRegisteredUser.md
gitcommit: https://github.com/Azure/azure-docs-powershell-azuread/blob/a3f4eb41072cf1506c8f82aa100e942b0830fc23
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Remove-AzureADDeviceRegisteredUser

## SYNOPSIS
Removes a registered user from a device.

## SYNTAX

```
Remove-AzureADDeviceRegisteredUser -ObjectId <String> -UserId <String> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureADDeviceRegisteredUser** cmdlet removes a registered user from an Azure Active Directory device.

## EXAMPLES

### Example 1: Remove a registered user from a device
```
PS C:\> $Device = Get-AzureADDevice -Top 1
PS C:\> $User = Get-AzureADDeviceRegisteredUser -ObjectId $Device.ObjectId
PS C:\> Remove-AzureADDeviceRegisteredOwner -ObjectId $Device.ObjectId -OwnerId $Owner.ObjectId
```

The first command gets a device by using the [Get-AzureADDevice](./Get-AzureADDevice.md) cmdlet, and then stores it in the $Device variable.

The second command gets the registered user for the device in $Device by using the [Get-AzureADDeviceRegisteredUser](./Get-AzureADDeviceRegisteredUser.md) cmdlet.
The command stores it in the $User variable.

The final command removes the user in $User from the device in $Device.


## PARAMETERS

### -ObjectId
Specifies the ID of an object.
```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -UserId
Specifies the ID of a user.
```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureADDeviceRegisteredUser](./Add-AzureADDeviceRegisteredUser.md)

[Get-AzureADDeviceRegisteredUser](./Get-AzureADDeviceRegisteredUser.md)
