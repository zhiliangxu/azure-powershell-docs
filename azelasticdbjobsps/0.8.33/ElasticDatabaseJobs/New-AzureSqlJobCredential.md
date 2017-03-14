---
external help file: Microsoft.Azure.SqlDatabase.Jobs.PowerShell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 4B254709-7D68-4202-8CE9-B7F3D4F8FE30
updated_at: 11/16/2016 17:11 PM
ms.date: 11/16/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/New-AzureSqlJobCredential.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/master/ElasticDB/ElasticDatabaseJobs/v0.8.33/New-AzureSqlJobCredential.md
gitcommit: https://github.com/Azure/azure-docs-powershell-elasticdb/blob/b6a4e720f68675b3b0e9f6aa6be6e55d3ebdc390
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# New-AzureSqlJobCredential

## SYNOPSIS
Creates database credentials when connecting to databases to run jobs.

## SYNTAX

```
New-AzureSqlJobCredential -CredentialName <String> -Credential <PSCredential>
 [-EncryptionCertificateThumbprint <String>] [[-AzureSqlJobConnection] <AzureSqlJobConnection>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureSqlJobCredential** cmdlet creates database credentials (username and password) when connecting to databases to run jobs.
Passwords are encrypted locally prior to transmission through the use of a public key stored within the Elastic Database Jobs database.

## EXAMPLES

### Example 1: Create a new credential using the specified name
```
PS C:\>New-AzureSqlJobCredential -CredentialName MyCredential
CredentialName                                              UserName
--------------                                              --------
MyCredential                                                MyUsername
```

This command creates a new credential using the provided name.
Following cmdlet invocation, you are prompted for the username and password credentials.

## PARAMETERS

### -AzureSqlJobConnection
Specifies the connection state object for the job.
You can get the connection state object through the [New-AzureSqlJobConnection](./New-AzureSqlJobConnection.md) cmdlet.
If you do not specify this parameter, the connection state is used from a prior call to the [Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md) cmdlet.

```yaml
Type: AzureSqlJobConnection
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the **PSCredential** containing the username and password.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CredentialName
Specifies the name of the credential.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionCertificateThumbprint
Specifies that the certificate's thumbprint must match the provided thumbprint prior to encryption of the password.

```yaml
Type: String
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSqlJobCredential](./Get-AzureSqlJobCredential.md)

[Set-AzureSqlJobCredential](./Set-AzureSqlJobCredential.md)

[New-AzureSqlJobConnection](./New-AzureSqlJobConnection.md)

[Use-AzureSqlJobConnection](./Use-AzureSqlJobConnection.md)

[Azure Elastic Database Jobs Cmdlets](./ElasticDatabaseJobs.md)
