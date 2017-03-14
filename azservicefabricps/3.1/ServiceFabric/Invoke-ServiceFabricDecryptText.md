---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 73384750-6F54-4B7D-AD7D-BE53426132A4
updated_at: 03/07/2017 04:03 AM
ms.date: 03/07/2017
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Invoke-ServiceFabricDecryptText.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Invoke-ServiceFabricDecryptText.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/acb318fd1728530f7ac927f78a79dc825e80d533
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Invoke-ServiceFabricDecryptText

## SYNOPSIS
Decrypts the text encrypted by the [Invoke-ServiceFabricEncryptText](/.Invoke-ServiceFabricEncryptText.md) cmdlet.

## SYNTAX

```
Invoke-ServiceFabricDecryptText [-CipherText] <String> [-StoreLocation <StoreLocation>] [-TimeoutSec <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-ServiceFabricDecryptText** cmdlet decrypts text that was encrypted by using the [Invoke-ServiceFabricEncryptText](./Invoke-ServiceFabricEncryptText.md) cmdlet for verification in Service Fabric.

Before you perform any operation on a Service Fabric cluster, establish a connection to the cluster by using the [Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md) cmdlet.

> [!NOTE]
> In order to decrypt the text, the caller of this cmdlet should have access to the private key of the certificate used to encrypt the text.

## EXAMPLES

### 1:
```
PS C:\windows\system32> $encryptedText = Invoke-ServiceFabricEncryptText -Text "hello world" -CertThumbprint $thumbprint
-CertStore -StoreLocation LocalMachine -StoreName My

PS C:\windows\system32> Invoke-ServiceFabricDecryptText -CipherText $encryptedText -StoreLocation LocalMachine
hello world

```

## PARAMETERS

### -CipherText
Specifies the cipher text for the cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StoreLocation
Specifies the location of a certificate store.
Valid values are:

- CurrentUser
- LocalMachine

```yaml
Type: StoreLocation
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSec
Specifies the time-out period, in seconds, for the operation.

```yaml
Type: Int32
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

### String
This cmdlet accepts a string of cipher text.

## OUTPUTS

### System.Object
This cmdlet returns decrypted text as a **String**.

## NOTES

## RELATED LINKS

[Invoke-ServiceFabricEncryptText](./Invoke-ServiceFabricEncryptText.md)

[Connect-ServiceFabricCluster](./Connect-ServiceFabricCluster.md)

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)
