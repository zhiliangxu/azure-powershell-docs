---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
ms.assetid: 5D857FF6-A27D-4031-948D-8A69D24B4AD4
online version:
schema: 2.0.0
updated_at: 03/11/2017 23:03 PM
ms.date: 03/11/2017
content_git_url: https://github.com/Azure/azure-docs-powershell/blob/master/azureps-cmdlets-docs/ResourceManager/AzureRM.Network/v3.5.0/Remove-AzureRmVpnClientRootCertificate.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell/blob/master/azureps-cmdlets-docs/ResourceManager/AzureRM.Network/v3.5.0/Remove-AzureRmVpnClientRootCertificate.md
gitcommit: https://github.com/Azure/azure-docs-powershell/blob/bc71000aa3c7f754b95442dcc415a7324626a15c
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Remove-AzureRmVpnClientRootCertificate

## SYNOPSIS
Removes an existing VPN client root certificate.

## SYNTAX

```
Remove-AzureRmVpnClientRootCertificate -VpnClientRootCertificateName <String>
 -VirtualNetworkGatewayName <String> -ResourceGroupName <String> -PublicCertData <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureRmVpnClientRootCertificate** cmdlet removes the specified root certificate from a virtual network gateway.
Root certificates are X.509 certificates that identify your Root Certification Authority: all other certificates used on the gateway trust the root certificate.
If you remove a root certificate computers that use the certificate for authentication purposes will no longer be able to connect to the gateway.

When you use **Remove-AzureRmVpnClientRootCertificate**, you must supply both the certificate name and a text representation of the certificate data.
For more information about the text representation of a certificate see the *PublicCertData* parameter description.

## EXAMPLES

### Example 1: Remove a client root certificate from a virtual network gateway
```
PS C:\>$Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertficate.cer"
PS C:\> $CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text[$i]}
PS C:\> Remove-AzureRmVpnClientRootCertificate -PublicCertData $CertificateText -ResourceGroupName "ContosoResourceGroup" -VirtualNetworkGatewayName "ContosoVirtualGateway"-VpnClientRootCertificateName "ContosoRootCertificate"
```

This example removes a client root certificate named ContosoRootCertificate from the virtual network gateway ContosoVirtualGateway.

The first command uses the **Get-Content** cmdlet to get a previously-exported text representation of the certificate; this text representation is stored in a variable named $Text.

The second command then uses a for loop to extract all the text in $Text except for the first line and the last line.
This extracted text is stored in a variable named $CertificateText.

The third command uses the information stored in the $CertificateText variable along with the **Remove-AzureRmVpnClientRootCertificate** cmdlet to remove the certificate from the gateway.

## PARAMETERS

### -VpnClientRootCertificateName
Specifies the name of the client root certificate that this cmdlet removes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetworkGatewayName
Specifies the name of the virtual network gateway that the certificate is removed from.

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

### -ResourceGroupName
Specifies the name of the resource group that the virtual network gateway is assigned to.

Resource groups categorize items to help simplify inventory management and general Azure administration.

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

### -PublicCertData
Specifies the text representation of the root certificate to be removed.
To obtain the text representation, export your certificate in .cer format (using Base64) encoding, then open the resulting file in a text editor.
You should see output similar to the following (note that the actual output will contain many more lines of text than the abbreviated sample shown here):

----- BEGIN CERTIFICATE -----
MIIC13FAAXC3671Auij9HHgUNEW8343NMJklo09982CVVFAw8w
----- END CERTIFICATE -----

The PublicCertData is made up of all the lines between the first line (----- BEGIN CERTIFICATE -----) and the last line (----- END CERTIFICATE -----) in the file.
You can retrieve the PublicCertData using Windows PowerShell commands similar to this:

$Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertficate.cer"
$CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text\[$i\]}

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

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureRmVpnClientRootCertificate](./Add-AzureRmVpnClientRootCertificate.md)

[Get-AzureRmVpnClientRootCertificate](./Get-AzureRmVpnClientRootCertificate.md)

[New-AzureRmVpnClientRootCertificate](./New-AzureRmVpnClientRootCertificate.md)


