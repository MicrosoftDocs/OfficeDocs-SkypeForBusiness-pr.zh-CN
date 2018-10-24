---
title: New-CsProxyConfiguration
TOCTitle: New-CsProxyConfiguration
ms:assetid: 5133470e-1d77-4958-8844-a091336b2a3c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398335(v=OCS.15)
ms:contentKeyID: 49312836
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsProxyConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of proxy configuration settings. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsProxyConfiguration -Identity <XdsIdentity> [-AcceptClientCompression <$true | $false>] [-AcceptServerCompression <$true | $false>] [-AllowPartnerPollingSubscribes <$true | $false>] [-Confirm [<SwitchParameter>]] [-DisableNtlmFor2010AndLaterClients <$true | $false>] [-DnsCacheRecordCount <UInt32>] [-EnableLoggingAllMessageBodies <$true | $false>] [-EnableWhiteSpaceKeepAlive <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-LoadBalanceEdgeServers <$true | $false>] [-LoadBalanceInternalServers <$true | $false>] [-MaxClientCompressionCount <UInt32>] [-MaxClientMessageBodySizeKb <UInt32>] [-MaxKeepAliveInterval <UInt32>] [-MaxServerCompressionCount <UInt32>] [-MaxServerMessageBodySizeKb <UInt32>] [-OutgoingTlsCount <UInt32>] [-Realm <IRealmChoice>] [-RequestServerCompression <$true | $false>] [-TreatAllClientsAsRemote <$true | $false>] [-UseCertificateForClientToProxyAuth <$true | $false>] [-UseKerberosForClientToProxyAuth <$true | $false>] [-UseNtlmForClientToProxyAuth <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 creates a new collection of proxy configuration settings for the service EdgeServer:atl-edge-001.litwareinc.com. These new settings use all the default proxy server property values except for two: RequestServerCompression, which is set to True; and MaxClientMessageBodySizeKb, which is set to 256. Note that this command will fail if proxy server settings have already been configured for the service EdgeServer:atl-edge-001.litwareinc.com.

    New-CsProxyConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -RequestServerCompression $True -MaxClientMessageBodySizeKb 256

## EXAMPLE 2

The commands shown in Example 2 demonstrate how you can create a collection of proxy server settings that initially exist only in memory. To do this, the first command calls the **New-CsProxyConfiguration** cmdlet along with two parameters: Identity (which specifies the Identity for the settings) and InMemory, which indicates that the new settings should be created in memory only. The resulting object is stored in the variable $x.

After these virtual settings have been created, commands 2 and 3 are used to modify the values of the RequestServerCompression and MaxClientMessageBodySizeKb properties, respectively. Finally, command 4 is used to transform the virtual proxy server configuration settings into an actual collection of settings applied to the service EdgeServer:atl-edge-001.litwareinc.com. This final command is mandatory. If you do not call the **Set-CsProxyConfiguration** cmdlet, no settings will be applied to EdgeServer:atl-edge-001.litwareinc.com and the virtual settings will disappear as soon as you end your Windows PowerShell session or delete the variable $x.

    $x = New-CsProxyConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -InMemory
    $x.RequestServerCompression = $True 
    $x.MaxClientMessageBodySizeKb = 256
    Set-CsProxyConfiguration -Instance $x

## Detailed Description

Lync Server enables you to manage your proxy servers through proxy server configuration settings. These settings, which can be applied at both the global scope and the service scope (albeit for only the 边缘服务器 and Registrar services) enable you to control such things as the authentication protocols that can be used by client endpoints and whether or not compression will be used on incoming and outgoing proxy server connections. When you install Lync Server, a global collection of proxy server configuration settings is automatically created for you. As noted, you can also create additional collections at the service scope. These new collections are created by using the **New-CsProxyConfiguration** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsProxyConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsProxyConfiguration"}

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
<td><p>Unique identifier for the proxy server configuration settings to be created. Proxy server configuration settings can only be created at the service scope, and only for the 边缘服务器 and Registrar services. You cannot create settings at the global scope; likewise, you cannot create settings at the service scope if the service in question already hosts a collection of proxy server settings. For example, if the service Registrar:atl-cs-001.litwareinc.com already hosts proxy server settings, then any command that attempts to create new settings for that service will fail.</p>
<p>To specify the Identity for your new proxy server settings, use syntax similar to this: -Identity &quot;service:Registrar:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>AcceptClientCompression</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value), the proxy server will accept all incoming compression requests from client endpoints.</p></td>
</tr>
<tr class="odd">
<td><p><em>AcceptServerCompression</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value), the proxy server will accept all incoming compression requests from other servers.</p></td>
</tr>
<tr class="even">
<td><p><em>AllowPartnerPollingSubscribes</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set the True, partner applications are allowed to periodically poll the service for state changes. The default value is False ($False).</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>DisableNtlmFor2010AndLaterClients</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, users logging on from Lync must use the Kerberos protocol for authentication. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>DnsCacheRecordCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum number of records that can be maintained in the DNS record cache. The default value is 3000.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableLoggingAllMessageBodies</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, Microsoft Lync Server will log the actual content of all instant messages. For privacy reasons, message content is typically deleted and only information about the communicating endpoints is included in the log files.</p>
<p>The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableWhiteSpaceKeepAlive</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value), the proxy server expects clients to periodically send a &quot;whitespace message&quot; (an empty message with no content) to indicate that the connection is still active.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
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
<td><p>Indicates whether or not security credentials are processed by the default proxy server realm (SIP Communications Service) or by a custom realm. Custom realms must be specified (and created) by using the <strong>New-CsSipProxyCustom</strong> cmdlet.</p></td>
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
<td><p>When set to True, the proxy server functions as if all client connections are external connections that pass through the 边缘服务器 running the 访问边缘服务. The default value is False.</p></td>
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
<td><p>When set to True (the default value), client endpoints will be allowed to use the NTLM protocol for authentication. Although NTLM is a less secure protocol than Kerberos, NTLM can be used if the client belongs to a different domain than the server. That is not true for Kerberos authentication.</p></td>
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

None. The **New-CsProxyConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **New-CsProxyConfiguration** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.ProxySettings object.

## 另请参阅

#### 其他资源

[Get-CsProxyConfiguration](get-csproxyconfiguration.md)  
[Remove-CsProxyConfiguration](remove-csproxyconfiguration.md)  
[Set-CsProxyConfiguration](set-csproxyconfiguration.md)

