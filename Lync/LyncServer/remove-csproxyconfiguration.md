---
title: Remove-CsProxyConfiguration
TOCTitle: Remove-CsProxyConfiguration
ms:assetid: 738f731c-4d62-4395-bdc3-3f5e5738f443
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398553(v=OCS.15)
ms:contentKeyID: 49313243
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsProxyConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes an existing collection of proxy server configuration settings. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsProxyConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 deletes the proxy configuration settings that have the Identity service:EdgeServer:atl-edge-litwareinc.com.

    Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com 

## EXAMPLE 2

In Example 2, all of the proxy configuration settings applied at the service scope are deleted. To accomplish this task, the command first calls the **Get-CsProxyConfiguration** cmdlet along with the Filter parameter. The filter value "service:\*" ensures that only proxy settings that have an Identity that begins with the string value "service:" will be returned. That filtered collection is then piped to the **Remove-CsProxyConfiguration** cmdlet, which deletes each item in the collection.

    Get-CsProxyConfiguration -Filter "service:*" | Remove-CsProxyConfiguration

## EXAMPLE 3

Example 3 deletes any proxy configuration settings that treat all clients as remote clients. To do this, the **Get-CsProxyConfiguration** cmdlet is first called without any parameters in order to return a collection of all the proxy server configuration settings currently in use. This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the TreatAllClientsAsRemote property is equal to True. This subset of proxy configuration settings is then piped to the **Remove-CsProxyConfiguration** cmdlet, which removes all the settings in the collection.

    Get-CsProxyConfiguration | Where-Object {$_.TreatAllClientsAsRemote -eq $True} | Remove-CsProxyConfiguration

## Detailed Description

Lync Server enables you to manage your proxy servers through proxy server configuration settings. These settings, which can be applied at both the global scope and the service scope (albeit for only the 边缘服务器 and Registrar services) enable you to control such things as the authentication protocols that can be used by client endpoints and whether or not compression will be used on incoming and outgoing proxy server connections. When you install Lync Server, a global collection of proxy server configuration settings is automatically created for you. As noted, you can also create additional collections at the service scope.

Any new proxy server settings you create can later be removed by using the **Remove-CsProxyConfiguration** cmdlet. You can also run the **Remove-CsProxyConfiguration** cmdlet against the global collection. In that case, however, the global settings will not be removed; that’s because Lync Server does not allow you to remove global settings. Instead, all of the properties within the global collection will be reset to their default values. For example, by default proxy server settings allow clients to use the Kerberos protocol for authentication. You can change the global settings to disable the use of Kerberos. However, if you run the **Remove-CsProxyConfiguration** cmdlet against the global collection, the property in question (UseKerberosForClientToProxyAuth) will be reset to its default value, and Kerberos will again be enabled for use as an authentication protocol.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsProxyConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsProxyConfiguration"}

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier of the proxy server configuration settings to be removed; for example: -Identity &quot;service:Registrar:atl-cs-001.litwareinc.com&quot;.</p>
<p>The <strong>Remove-CsProxyConfiguration</strong> cmdlet can also be run against the global settings. In that case, however, the settings will not be removed. Instead, the properties within that global collection will all be reset to their default values.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.ProxySettings object. The **Remove-CsProxyConfiguration** cmdlet accepts pipelined instances of the proxy settings object.

## Return Types

None. Instead, the **Remove-CsProxyConfiguration** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.ProxySettings object.

## 另请参阅

#### 其他资源

[Get-CsProxyConfiguration](get-csproxyconfiguration.md)  
[New-CsProxyConfiguration](new-csproxyconfiguration.md)  
[Set-CsProxyConfiguration](set-csproxyconfiguration.md)

