---
title: Set-CsLisServiceProvider
TOCTitle: Set-CsLisServiceProvider
ms:assetid: 3fe2878c-6ad2-4b7f-a844-e978c263163f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425911(v=OCS.15)
ms:contentKeyID: 49312612
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsLisServiceProvider

 

_**上一次修改主题：** 2015-03-09_

Creates or modifies information about the web service provided by the Enhanced 9-1-1 (E9-1-1) Network Routing Provider to verify locations. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsLisServiceProvider -CertFileName <String> -Password <SecureString> -ServiceProviderName <String> -ValidationServiceUrl <String> [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

One of the required parameters for creating an entry for an E9-1-1 Network Routing Provider web service is a secure string containing the password to access the certificate file. Because of that, the first line in this example is a call to the **Read-Host** cmdlet. The **Read-Host** cmdlet will prompt for user input. We specify the parameter AsSecureString, which will display that input as asterisks (\*) as it is entered. We’ve assigned the result of this command to the variable $p. The result will be a secure string, which is an encrypted version of the user input. In other words, running this command will prompt for the password to the web service and will store that password in the variable $p.

Now that we have the password, we can create an object that will access the web service. We do this by calling the **Set-CsLisServiceProvider** cmdlet. We pass several parameters to this cmdlet. The first is the name of the provider, in this case E911Provider. Next we provide a value for the ValidationServiceUrl, https://www.911contoso.com/validation/. Note that this must be a “secure site,” with the prefix https rather than http. Next we enter the name of the file containing the certificate used to access this web service, C:\\MS-Contoso-Cert.pfx. Finally, we pass the variable $p (which contains the secure string with the web service password) to the Password parameter.

    $p = Read-Host -AsSecureString
    Set-CsLisServiceProvider -ServiceProviderName E911Provider -ValidationServiceUrl https://www.911contoso.com/validation/ -CertFileName C:\MS-Contoso-Cert.pfx -Password $p

## Detailed Description

In an Enterprise Voice implementation with E9-1-1, emergency calls must first be routed through an E9-1-1 Network Routing Provider to ensure that the calls are routed to the appropriate Public Safety Answering Point (PSAP). (A PSAP is the agency in the United States that directs the calls to the nearest emergency services, such as police, fire, and ambulance services.) In order to do this, the provider must have a list of locations from the organization that it can then match against the Master Street Address Guide to ensure all locations are valid. This cmdlet creates or modifies information about a provider, including the name of the provider, a URL for the web service that the organization will use to send the locations, and a certificate and password for the secure web service.

You cannot define more than one service provider for a given E9-1-1 implementation. This cmdlet will not succeed unless it can resolve the URL and security information for the web service.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsLisServiceProvider** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsLisServiceProvider"}

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
<td><p><em>CertFileName</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The name (and full path) of the certificate file. This file must have a PFX file extension.</p></td>
</tr>
<tr class="even">
<td><p><em>Password</em></p></td>
<td><p>Required</p></td>
<td><p>System.Security.SecureString</p></td>
<td><p>A secure string containing the password needed to access the certificate in the password protected file. Secure strings can be created by using the <strong>ConvertTo-SecureString</strong> cmdlet or the <strong>Read-Host</strong> cmdlet with the AsSecureString parameter.</p></td>
</tr>
<tr class="odd">
<td><p><em>ServiceProviderName</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The name of the E9-1-1 Network Routing Provider.</p></td>
</tr>
<tr class="even">
<td><p><em>ValidationServiceUrl</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The URL of the web service. This must be a secure URL, beginning with the prefix https://.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Accepts pipelined input of Location Information Server (LIS) service provider objects.

## Return Types

This cmdlet creates or modifies an object of type System.Management.Automation.PSCustomObject.

## 另请参阅

#### 其他资源

[Remove-CsLisServiceProvider](remove-cslisserviceprovider.md)  
[Get-CsLisServiceProvider](get-cslisserviceprovider.md)

