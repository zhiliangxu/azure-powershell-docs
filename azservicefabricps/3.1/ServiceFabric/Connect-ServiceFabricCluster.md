---
external help file: Microsoft.ServiceFabric.Powershell.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 7370AD41-FB09-4948-9BB7-8FD67B5E99E4
updated_at: 11/11/2016 08:11 AM
ms.date: 11/11/2016
content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Connect-ServiceFabricCluster.md
original_content_git_url: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/master/Service-Fabric-cmdlets/ServiceFabric/vlatest/Connect-ServiceFabricCluster.md
gitcommit: https://github.com/Azure/azure-docs-powershell-servicefabric/blob/1e386f2c4d3f0d7aa5edba5cc7deaac957310f26
ms.topic: reference
author: erickson-doug
ms.author: PowerShellHelpPub
keywords: powershell, cmdlet
---

# Connect-ServiceFabricCluster

## SYNOPSIS
Creates a connection to a Service Fabric cluster.

## SYNTAX

### Aad
```
Connect-ServiceFabricCluster -ConnectionEndpoint <String[]> [-AllowNetworkConnectionOnly]
 [-ServerCommonName <String[]>] [-ServerCertThumbprint <String[]>] [-AzureActiveDirectory]
 [-SecurityToken <String>] [-GetMetadata] [-ConnectionInitializationTimeoutInSec <Double>]
 [-HealthOperationTimeoutInSec <Double>] [-HealthReportSendIntervalInSec <Double>]
 [-HealthReportRetrySendIntervalInSec <Double>] [-KeepAliveIntervalInSec <Double>]
 [-ServiceChangePollIntervalInSec <Double>] [-PartitionLocationCacheLimit <Int64>]
 [-AuthTokenBufferSize <Int64>] [-SkipChecks <Boolean>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Default
```
Connect-ServiceFabricCluster [-ConnectionEndpoint <String[]>] [-AllowNetworkConnectionOnly]
 [-ConnectionInitializationTimeoutInSec <Double>] [-HealthOperationTimeoutInSec <Double>]
 [-HealthReportSendIntervalInSec <Double>] [-HealthReportRetrySendIntervalInSec <Double>]
 [-KeepAliveIntervalInSec <Double>] [-ServiceChangePollIntervalInSec <Double>]
 [-PartitionLocationCacheLimit <Int64>] [-AuthTokenBufferSize <Int64>] [-SkipChecks <Boolean>]
 [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Windows
```
Connect-ServiceFabricCluster -ConnectionEndpoint <String[]> [-AllowNetworkConnectionOnly] [-WindowsCredential]
 [-ClusterSpn <String>] [-ConnectionInitializationTimeoutInSec <Double>]
 [-HealthOperationTimeoutInSec <Double>] [-HealthReportSendIntervalInSec <Double>]
 [-HealthReportRetrySendIntervalInSec <Double>] [-KeepAliveIntervalInSec <Double>]
 [-ServiceChangePollIntervalInSec <Double>] [-PartitionLocationCacheLimit <Int64>]
 [-AuthTokenBufferSize <Int64>] [-SkipChecks <Boolean>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### X509
```
Connect-ServiceFabricCluster -ConnectionEndpoint <String[]> [-AllowNetworkConnectionOnly] [-X509Credential]
 [-ServerCommonName <String[]>] [-ServerCertThumbprint <String[]>] -FindType <X509FindType> -FindValue <String>
 [-StoreLocation <StoreLocation>] [-StoreName <String>] [-ConnectionInitializationTimeoutInSec <Double>]
 [-HealthOperationTimeoutInSec <Double>] [-HealthReportSendIntervalInSec <Double>]
 [-HealthReportRetrySendIntervalInSec <Double>] [-KeepAliveIntervalInSec <Double>]
 [-ServiceChangePollIntervalInSec <Double>] [-PartitionLocationCacheLimit <Int64>]
 [-AuthTokenBufferSize <Int64>] [-SkipChecks <Boolean>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

### Dsts
```
Connect-ServiceFabricCluster -ConnectionEndpoint <String[]> [-AllowNetworkConnectionOnly]
 [-ServerCommonName <String[]>] [-ServerCertThumbprint <String[]>] [-DSTS] -MetaDataEndpoint <String>
 [-CloudServiceName <String>] [-CloudServiceDNSNames <String[]>]
 [-ConnectionInitializationTimeoutInSec <Double>] [-HealthOperationTimeoutInSec <Double>]
 [-HealthReportSendIntervalInSec <Double>] [-HealthReportRetrySendIntervalInSec <Double>]
 [-KeepAliveIntervalInSec <Double>] [-ServiceChangePollIntervalInSec <Double>]
 [-PartitionLocationCacheLimit <Int64>] [-AuthTokenBufferSize <Int64>] [-Interactive <Boolean>]
 [-SkipChecks <Boolean>] [-TimeoutSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Connect-ServiceFabricCluster** cmdlet creates a connection to a Service Fabric cluster that allows you to run management actions for that cluster.
After you connect to a cluster, you can view the settings of the connection by using the [Get-ServiceFabricClusterConnection](.\Get-ServiceFabricClusterConnection.md) cmdlet.

To manage Service Fabric clusters, start Windows PowerShell by using the **Run as administrator** option.

## EXAMPLES

### Example 1: Connect to a cluster
```
PS C:\>Connect-ServiceFabricCluster -ConnectionEndpoint "ServiceFabric01.ContosoCloudApp.net:19000"
```

This command creates a connection to the specified cluster.

### Example 2: Connect to a cluster using an X.509 certificate
```
PS C:\>$ConnectArgs = @{  ConnectionEndpoint = 'mycluster.cloudapp.net:19000';  X509Credential = $True;  StoreLocation = 'CurrentUser';  StoreName = "MY";  ServerCommonName = "mycluster.cloudapp.net";  FindType = 'FindByThumbprint';  FindValue = "AA11BB22CC33DD44EE55FF66AA77BB88CC99DD00"   }
PS C:\> Connect-ServiceFabricCluster $ConnectArgs
```

This command connects to a cluster using an X.509 certificate.
This command uses the splatting feature of Windows PowerShell to create a hash table for parameters, and then supplies them to the **Connect-ServiceFabricCluster** cmdlet.

### Example 3: Connect to a cluster using Azure Active Directory
```
PS C:\>$ConnectArgs = @{  ConnectionEndpoint = 'mycluster.cloudapp.net:19000';  AzureActiveDirectory = $True; ServerCertThumbprint = "AA11BB22CC33DD44EE55FF66AA77BB88CC99DD00"   }
PS C:\> Connect-ServiceFabricCluster $ConnectArgs
```

This command connects to a cluster using Azure Active Directory(AAD) authentication.
This command uses the splatting feature of Windows PowerShell to create a hash table for parameters, and then supplies them to the **Connect-ServiceFabricCluster** cmdlet.

### Example 4: Connect to a cluster secured with a group-managed service account
```
PS C:\>$ConnectArgs = @{  ConnectionEndpoint = 'mycluster.cloudapp.net:19000';  WindowsCredential = $True; ClusterSpn = 'ServiceFabric/MyCluster.MyDomain.MyOrg'  }
PS C:\> Connect-ServiceFabricCluster @connectArgs
```

This command uses the splatting feature of Windows PowerShell to create a hash table for parameters, and then supplies them to the **Connect-ServiceFabricCluster** cmdlet.

### Example 5: Connect to a cluster secured with machine accounts
```
PS C:\>$connectArgs = @{  ConnectionEndpoint = 'mycluster.cloudapp.net:19000';  WindowsCredential = $True;  }
PS C:\> Connect-ServiceFabricCluster @connectArgs
```

This command connects to a cluster secured with machine accounts.

### Example 6: Connect to a cluster without the primary checks
```
PS C:\>Connect-ServiceFabricCluster -ConnectionEndpoint -SkipChecks $True "ServiceFabric01.ContosoCloudApp.net:19000"
```

This command creates a connection to the specified cluster.

## PARAMETERS

### -AllowNetworkConnectionOnly
Indicates that the cmdlet allows connecting to the cluster even when system services are unresponsive as long as an underlying network connection can be established.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthTokenBufferSize
When connecting with *AzureActiveDirectory*, specifies the buffer size to allocate for security token acquisition.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureActiveDirectory
Specifies that Azure Active Directory should be used for authentication and authorization.

```yaml
Type: SwitchParameter
Parameter Sets: Aad
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloudServiceDNSNames
This parameter is for internal use only.

```yaml
Type: String[]
Parameter Sets: Dsts
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloudServiceName
This parameter is for internal use only.

```yaml
Type: String
Parameter Sets: Dsts
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterSpn
Specifies the cluster security principal name to use for Windows credential.

```yaml
Type: String
Parameter Sets: Windows
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionEndpoint
Specifies an array of connection endpoints for the cluster in the format ClusterAddress: ClientConnectionEndpoint, where ClusterAddress is the IPv4 address, IPv6 address, or fully qualified domain name (FQDN) of the cluster node to connect to and ClientConnectionEndpoint is the client connection port specified in the cluster manifest.
Enclose IPv6 addresses in square brackets (\[\]).
Valid endpoints have the following form:

IPv4Address:ClientConnectionEndpoint
\[IPv6Address\]:ClientConnectionEndpoint
FQDN:ClientConnectionEndpoint

```yaml
Type: String[]
Parameter Sets: Aad, Windows, X509, Dsts
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String[]
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionInitializationTimeoutInSec
Specifies the time-out period, in seconds, for the operation.

```yaml
Type: Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DSTS
This parameter is for internal use only.

```yaml
Type: SwitchParameter
Parameter Sets: Dsts
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FindType
Specifies the type of **FindValue** for searching certificate in certificate store.
The following filter types are supported:

- FindByThumbprint.
Find certificate by certificate thumbprint.
- FindBySubjectName.
Search certificate in certificate store by subject distinguished name or common name, when subject distinguished name is provided in **FindValue**, subject name in the certificate must be encoded in ASN encoding due to a restriction in native Windows crypto API.
There is no such restriction when common name is provided in **FindValue**.
- FindBySubjectDistinguishedName
- FindByIssuerName
- FindByIssuerDistinguishedName
- FindBySerialNumber
- FindByTimeValid
- FindByTimeNotYetValid
- FindByTimeExpired
- FindByTemplateName
- FindByApplicationPolicy
- FindByCertificatePolicy
- FindByExtension
- FindByKeyUsage
- FindBySubjectKeyIdentifier

```yaml
Type: X509FindType
Parameter Sets: X509
Aliases:
Accepted values: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FindValue
Specifies filter value to search a certificate in certificate store.

```yaml
Type: String
Parameter Sets: X509
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GetMetadata
When connecting with *AzureActiveDirectory*, anonymously retrieves the metadata used for token acquisition and does not attempt any authentication.

```yaml
Type: SwitchParameter
Parameter Sets: Aad
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthOperationTimeoutInSec
Specifies the time-out period, in seconds, for sending health reports.
When a health operation times out or fails with a communication error, the health client internally retries the operation.

```yaml
Type: Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthReportRetrySendIntervalInSec
Specifies the interval, in seconds, at which the health client retries sending the reports that failed to be sent or to be persisted in health store.

```yaml
Type: Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthReportSendIntervalInSec
Specifies the interval, in seconds, at which the health client sends the health reports to health store.
If set to 0, the health client will send the reports immediately.

```yaml
Type: Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Interactive
Indicates whether the cmdlet operates interactively.

```yaml
Type: Boolean
Parameter Sets: Dsts
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeepAliveIntervalInSec
Specifies the connection keep-alive period in seconds.
This interval prevents a connection from being terminated because of inactivity during operations that run asynchronously.

```yaml
Type: Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MetaDataEndpoint
This parameter is for internal use only.

```yaml
Type: String
Parameter Sets: Dsts
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionLocationCacheLimit
Specifies the number of partitions cached for service resolution.
The default value is 0, which signifies no limit.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecurityToken
When connecting with *AzureActiveDirectory*, the specified security token is used directly for authentication and authorization rather than performing interactive user login.

```yaml
Type: String
Parameter Sets: Aad
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerCertThumbprint
Specifies an array of the expected thumbprints for the cluster side.
These thumbprints are used to authenticate that the cmdlet connects to the endpoint of the correct cluster during x509 or Azure Active Directory mutual authentication.

```yaml
Type: String[]
Parameter Sets: Aad, X509, Dsts
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerCommonName
Specifies an array of the expected common names for the cluster side.
These names are used to authenticate that the cmdlet connects to the endpoint of the correct cluster during x509 or Azure Active Directory mutual authentication.

```yaml
Type: String[]
Parameter Sets: Aad, X509, Dsts
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceChangePollIntervalInSec
Specifies the interval, in seconds, at which the fabric client polls for service changes.
This interval is used by old model of poll-based service address change notifications.

```yaml
Type: Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipChecks
Indicates to bypass system service responsiveness validation checks when connecting to the cluster.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoreLocation
Specifies the store location of a certificate.
The acceptable values for this parameter are:

- CurrentUser
- LocalMachine

```yaml
Type: StoreLocation
Parameter Sets: X509
Aliases:
Accepted values: CurrentUser, LocalMachine

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoreName
Specifies the name of the certificate store to load the client certificate.

```yaml
Type: String
Parameter Sets: X509
Aliases:

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

### -WindowsCredential
Indicates that the cmdlet uses Windows credentials to connect to a Service Fabric cluster.

```yaml
Type: SwitchParameter
Parameter Sets: Windows
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -X509Credential
Indicates that the cmdlet uses an x509 certificate to perform mutual authentication with a Service Fabric cluster.

```yaml
Type: SwitchParameter
Parameter Sets: X509
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### System.Object
This cmdlet returns a **System.Fabric.Powershell.ClusterConnection** that represents the Service Fabric cluster connection.

## NOTES

## RELATED LINKS

[Get-ServiceFabricClusterConnection](./Get-ServiceFabricClusterConnection.md)

[Test-ServiceFabricClusterConnection](./Test-ServiceFabricClusterConnection.md)
