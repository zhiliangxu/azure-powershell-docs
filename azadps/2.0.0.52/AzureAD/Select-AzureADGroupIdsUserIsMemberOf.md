---
external help file: Microsoft.Open.AzureAD16.Graph.PowerShell.dll-Help.xml
ms.assetid: 66D77613-4992-463D-B318-E2D53B14AED4
online version:
schema: 2.0.0
updated_at: 12/06/2016 04:12 AM
ms.date: 12/06/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/v2/Select-AzureADGroupIdsUserIsMemberOf.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/v2/Select-AzureADGroupIdsUserIsMemberOf.md
gitcommit: https://github.com/Azure/azure-docs-powershell-azuread/blob/a3f4eb41072cf1506c8f82aa100e942b0830fc23
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Select-AzureADGroupIdsUserIsMemberOf

## SYNOPSIS
Selects the groups that a user is a member of.

## SYNTAX

```
Select-AzureADGroupIdsUserIsMemberOf -ObjectId <String>
 -GroupIdsForMembershipCheck <GroupIdsForMembershipCheck> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Select-AzureADGroupIdsUserIsMemberOf** cmdlet selects the groups that a user is a member of in Azure Actve Directory (AD).

## EXAMPLES

### Example 1: Get the group membership of a group for a user
```
PS C:\> $Groups = New-Object Microsoft.Open.AzureAD.Model.GroupIdsForMembershipCheck
PS C:\> $Groups.GroupIds = (Get-AzureADGroup -Top 1).ObjectId
PS C:\> $UserID = (Get-AzureADUser -Top 1).ObjectId
PS C:\> Select-AzureADGroupIdsUserIsMemberOf  -ObjectId $UserId -GroupIdsForMembershipCheck $Groups

OdataMetadata                                                                                   Value
-------------                                                                                   -----
https://graph.windows.net/85b5ff1e-0402-400c-9e3c-0f9e965325d1/$metadata#Collection(Edm.String) {093fc0e2-1d6e-4a1b-9bf8-effa0196f1f7}
```

The first command creates a **GroupIdsForMembershipCheck** object, and then stores it in the $Groups variable.

The second command gets an ID for a group by using the [Get-AzureADGroup](./Get-AzureADGroup.md) cmdlet, and then stores it as a property of $Groups.

The third command gets the ID of a user by using the [Get-AzureADUser](./Get-AzureADUser.md) cmdlet, and then stores it in the $UserId variable.

The final command gets the group membership of a group for a user identified by $UserId.
This cmdlet returns an **oData** object.
To find the groups this user is a member of, iterate through the **Value** attribute of the returned **oData** objects.


## PARAMETERS

### -GroupIdsForMembershipCheck
Specifies an array of group object IDs.

```yaml
Type: GroupIdsForMembershipCheck
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -InformationAction
Specifies how this cmdlet responds to an information event. The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies an information variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
Specifies the ID of a user (as a UPN or ObjectId) in Azure AD.

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
