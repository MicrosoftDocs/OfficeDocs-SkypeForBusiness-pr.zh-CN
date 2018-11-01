---
title: New-CsWebTrustedCACertificate
TOCTitle: New-CsWebTrustedCACertificate
ms:assetid: a0a94971-372a-401a-8ae0-9ff649a9c301
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412746(v=OCS.15)
ms:contentKeyID: 49313787
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsWebTrustedCACertificate

 

_**上一次修改主题：** 2015-03-09_

Creates a new certificate ID object based on an existing certification authority (CA) certificate. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsWebTrustedCACertificate -CAStore <TrustedRootCA | IntermediateCA | ThirdPartyRootCA> -Thumbprint <String>

## Examples

## EXAMPLE 1

The commands shown in Example 1 create a new trusted CA certificate and then add that certificate to the TrustedCACerts property of the Web Services configuration settings for the Redmond site. To carry out this task, the first command in the example uses the **New-CsWebTrustedCACertificate** cmdlet to create a new trusted CA certificate; that certificate can be found in the Trusted Root certificate store and has the Thumbprint D543DFF74FEEA425162FD25F342786F1AB453BB3. The resulting certificate object is stored in a variable named $x.

After the certificate object has been created, the second command in the example adds that certificate to the TrustedCACerts property. To do this, the command uses the **Set-CsWebServiceConfiguration** cmdlet and the TrustedCACerts parameter. The parameter value ${Add=$x} tells the cmdlet to add the certificate stored in the variable $x to the collection of trusted CA certificates.

    $x = New-CsWebTrustedCACertificate -Thumbprint "D543DFF74FEEA425162FD25F342786F1AB453BB3" -CAStore TrustedRootCA
    
    Set-CsWebServiceConfiguration -Identity site:Redmond -TrustedCACerts @{Add=$x}

## Detailed Description

Web Services configuration settings are used to help manage Lync Server Web servers and Web Services. Among the property values that can be managed using these settings is the TrustedCACerts property, which represents a collection of certification authorities trusted by Lync Phone Edition. Certificates obtained from trusted CAs allow these clients to enhance the security of connections with servers running Lync Server. To add a new CA to the collection of trusted certification authorities, you must add the certificate chain for that CA in the local computer’s certificate store. After you have verified that the certificate chain has been installed, you can then use the **New-CsWebTrustedCACertificate** cmdlet to create a certificate ID object that can be added to a collection of Web Services configuration settings.

Note that the certification authority that signs the default server certificate used when installing Lync Server is automatically trusted and does not need to be added to the TrustedCACerts property of a collection of Web 服务 configuration settings. TrustedCACerts should only contain the identities of CAs that need to be trusted in addition to the CA that issued the default certificate. In most cases, the CA that issued the default certificate will be the only certification authority that needs to be trusted.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsWebTrustedCACertificate** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself) run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsWebTrustedCACertificate"}

## 参数


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>CAStore</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Web.CAStore</p></td>
<td><p>Indicates the name of the certificate store (on the local computer) where the certificate is stored. Valid values are:</p>
<p>TrustedRootCA</p>
<p>IntermediateCA</p>
<p>ThirdPartyRootCA</p></td>
</tr>
<tr class="even">
<td><p><em>Thumbprint</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Thumbprint of the certificate which should be trusted by Lync Phone Edition . You can retrieve certificate issuer and thumbprint values by running this command:</p>
<p>Get-CsCertificate | Select-Object Issuer, Thumbprint.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsWebTrustedCACertificate** cmdlet does not accept pipelined input.

## Return Types

The **New-CsWebTrustedCACertificate** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Web.CACertID object.

## 另请参阅

#### 其他资源

[New-CsWebServiceConfiguration](New-CsWebServiceConfiguration.md)  
[Set-CsWebServiceConfiguration](set-cswebserviceconfiguration.md)

