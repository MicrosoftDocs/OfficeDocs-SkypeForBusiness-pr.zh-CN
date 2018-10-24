---
title: Set-CsProxyConfiguration
TOCTitle: Set-CsProxyConfiguration
ms:assetid: 2eb74d25-05b5-4901-aa92-eeda2f351e25
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425796(v=OCS.15)
ms:contentKeyID: 49312387
ms.date: 01/13/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsProxyConfiguration

 

_**上一次修改主题：** 2017-01-12_

Modifies an existing collection of proxy server configuration settings. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsProxyConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsProxyConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AcceptClientCompression <$true | $false>] [-AcceptServerCompression <$true | $false>] [-AllowPartnerPollingSubscribes <$true | $false>] [-Confirm [<SwitchParameter>]] [-DisableNtlmFor2010AndLaterClients <$true | $false>] [-DnsCacheRecordCount <UInt32>] [-EnableLoggingAllMessageBodies <$true | $false>] [-EnableWhiteSpaceKeepAlive <$true | $false>] [-Force <SwitchParameter>] [-LoadBalanceEdgeServers <$true | $false>] [-LoadBalanceInternalServers <$true | $false>] [-MaxClientCompressionCount <UInt32>] [-MaxClientMessageBodySizeKb <UInt32>] [-MaxKeepAliveInterval <UInt32>] [-MaxServerCompressionCount <UInt32>] [-MaxServerMessageBodySizeKb <UInt32>] [-OutgoingTlsCount <UInt32>] [-Realm <IRealmChoice>] [-RequestServerCompression <$true | $false>] [-TreatAllClientsAsRemote <$true | $false>] [-UseCertificateForClientToProxyAuth <$true | $false>] [-UseKerberosForClientToProxyAuth <$true | $false>] [-UseNtlmForClientToProxyAuth <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, all the proxy configuration settings that have the Identity service:EdgeServer:atl-edge-001.litwareinc.com are modified to accept server compression. This is done by calling the **Set-CsProxyConfiguration** cmdlet and the AcceptServerCompression parameter, and by setting the parameter value to True.

    Set-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-001.litwareinc.com -AcceptServerCompression $True

## EXAMPLE 2

Example 2 locates all of the proxy configuration settings that accept server compression, and then modifies these settings to accept client compression as well. To do this, the command first calls the **Get-CsProxyConfiguration** cmdlet without any parameters in order to return a collection of all the proxy settings in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the AcceptServerCompression property is equal to True. The filtered collection is then piped to the **Set-CsProxyConfiguration** cmdlet, which takes each item in the collection and sets the AcceptClientCompression property to True.

    Get-CsProxyConfiguration | Where-Object {$_.AcceptServerCompression -eq $True} | Set-CsProxyConfiguration -AcceptClientCompression $True

## EXAMPLE 3

Example 3 shows how you can modify all of the proxy settings that have been configured at the service scope. In order to do this, the command first calls the **Get-CsProxyConfiguration** cmdlet and includes the Filter parameter; the filter value "service:\*" ensures that only settings that have an Identity that begins with the string value "service:" are returned. The filtered collection is then piped to the **Set-CsProxyConfiguration** cmdlet, which takes each item in the collection and sets the UseNtlmForClientToProxyAuth property to False.

    Get-CsProxyConfiguration -Filter service:* | Set-CsProxyConfiguration -UseNtlmForClientToProxyAuth $False

## Detailed Description

Lync Server enables you to manage your proxy servers through proxy server configuration settings. These settings, which can be applied at both the global scope and the service scope (albeit for only the 边缘服务器 and Registrar services) enable you to control such things as the authentication protocols that can be used by client endpoints and whether or not compression will be used on incoming and outgoing proxy server connections. When you install Lync Server, a global collection of proxy server configuration settings is automatically created for you. As noted, you can also create additional collections at the service scope.

The **Set-CsProxyConfiguration** cmdlet provides a way for you to modify the property values of an existing collection of proxy server configuration settings.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsProxyConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsProxyConfiguration"}

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
<td><p><em>AcceptClientCompression</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value), the proxy server will accept all incoming compression requests from client endpoints.</p></td>
</tr>
<tr class="even">
<td><p><em>AcceptServerCompression</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value), the proxy server will accept all incoming compression requests from other servers.</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowPartnerPollingSubscribes</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set the True, partner applications are allowed to periodically poll the service for state changes. The default value is False ($False).</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>DisableNtlmFor2010AndLaterClients</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, users logging on from Lync must use the Kerberos protocol for authentication. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>DnsCacheRecordCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum number of records that can be maintained in the DNS record cache. The default value is 30000.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableLoggingAllMessageBodies</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, Lync Server will log the actual content of all instant messages. For privacy reasons, message content is typically deleted and only information about the communicating endpoints is included in the log files.</p>
<p>The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableWhiteSpaceKeepAlive</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value) the proxy server expects clients to periodically send a &quot;whitespace message&quot; (an empty message with no content) to indicate that the connection is still active.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the proxy server configuration settings to be modified. To modify the global settings, use this syntax: -Identity global. To modify settings configured at the service scope, use syntax similar to this: -Identity &quot;service: EdgeServer:atl-edge-001.litwareinc.com&quot;.</p>
<p>If this parameter is not included, the <strong>Set-CsProxyConfiguration</strong> cmdlet will automatically modify the global settings.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>ProxySettings object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="even">
<td><p><em>LoadBalanceEdgeServers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When True, software load balancing is employed for requests to Edge Servers. The default value is True ($True).</p></td>
</tr>
<tr class="odd">
<td><p><em>LoadBalanceInternalServers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When True, software load balancing is employed for requests to Registrars and other internal servers. The default value is true ($True).</p></td>
</tr>
<tr class="even">
<td><p><em>MaxClientCompressionCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates the maximum number of client-to-server connections that can be compressed at any given time; additional connections beyond this limit will not be compressed. The compression count can be set to any integer value between 0 and 65535, inclusive. The default value is 15000.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxClientMessageBodySizeKb</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>The maximum-allowed size (in kilobytes) for the body of a message sent from a client endpoint. The default value is 128, meaning that messages with a body size larger than 128 KB will be rejected. The client message body size can be set to any integer value between 64 and 256, inclusive.</p></td>
</tr>
<tr class="even">
<td><p><em>MaxKeepAliveInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Specifies the amount of time (in minutes) that can elapse before the server verifies that the connection with the client is still valid. The default value is 20 minutes.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxServerCompressionCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates the maximum number of server-to-server connections that can be compressed at any given time; additional connections beyond this limit will not be compressed. The server compression count can be set to any integer value between 0 and 65535, inclusive. The default value is 1024.</p></td>
</tr>
<tr class="even">
<td><p><em>MaxServerMessageBodySizeKb</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>The maximum-allowed size (in kilobytes) for the body of a message sent from another server. The default value is 5000, meaning that messages with a body size larger than 5000 KB will be rejected. The server message body size can be set to any integer value between 1000 and 20000, inclusive.</p></td>
</tr>
<tr class="odd">
<td><p><em>OutgoingTlsCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Specifies the maximum number of Transport Layer Security (TLS) connections that can be used for each internal server. The minimum number of TLS connections is 1, and the maximum number is 4. By default, OutgoingTlsCount is set to 4.</p></td>
</tr>
<tr class="even">
<td><p><em>Realm</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.IRealmChoice</p></td>
<td><p>Indicates whether or not security credentials are processed by the default proxy server realm (SIP Communication Services) or by a custom realm. Custom realms must be specified (and created) by using the <strong>New-CsSipProxyCustom</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>RequestServerCompression</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value) the proxy server requests that compression be used on all outgoing connections to other servers.</p></td>
</tr>
<tr class="even">
<td><p><em>TreatAllClientsAsRemote</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, the proxy server functions as if all client connections are external connections that pass through the 边缘服务器. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>UseCertificateForClientToProxyAuth</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value), client endpoints will be allowed to use certificates for authentication.</p></td>
</tr>
<tr class="even">
<td><p><em>UseKerberosForClientToProxyAuth</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value), client endpoints will be allowed to use the Kerberos protocol for authentication. Although Kerberos is a more secure protocol than NTLM, it cannot be used if the client belongs to a different realm than the server.</p></td>
</tr>
<tr class="odd">
<td><p><em>UseNtlmForClientToProxyAuth</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value), client endpoints will be allowed to use the NTLM protocol for authentication. Although NTLM is a less secure protocol than Kerberos, NTLM can be used if the client belongs to a different domain than the server. That is not the case with Kerberos authentication.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.ProxySettings object. The **Set-CsProxyConfiguration** cmdlet accepts pipelined instances of the proxy settings object.

## Return Types

The **Set-CsProxyConfiguration** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.ProxySettings object.

## 另请参阅

#### 其他资源

[Get-CsProxyConfiguration](get-csproxyconfiguration.md)  
[New-CsProxyConfiguration](new-csproxyconfiguration.md)  
[Remove-CsProxyConfiguration](remove-csproxyconfiguration.md)

