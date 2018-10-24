---
title: New-CsDiagnosticHeaderConfiguration
TOCTitle: New-CsDiagnosticHeaderConfiguration
ms:assetid: 5322e63e-c02c-4dec-8206-04f701258d6b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398350(v=OCS.15)
ms:contentKeyID: 49312856
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsDiagnosticHeaderConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new diagnostic header configuration setting collection. Diagnostic header configuration settings determine whether SIP messages are accompanied by header information that can be useful in troubleshooting and error reporting. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsDiagnosticHeaderConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-SendToExternalNetworks <$true | $false>] [-SendToOutsideUnauthenticatedUsers <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 creates a new diagnostic header configuration for the Redmond site (-Identity site:Redmond). In addition to specifying the Identity, the command also uses the SendToOutsideAuthenticatedUsers parameter and the parameter value $True; this enables the sending of information to authenticated users outside the internal network.

    New-CsDiagnosticHeaderConfiguration -Identity site:Redmond -SendToOutsideUnauthenticatedUsers $True

## EXAMPLE 2

The commands shown in Example 2 demonstrate how you can create a collection of diagnostic header settings that initially exist only in memory. To do this, the first command in the example calls the **New-CsDiagnosticHeaderConfiguration** cmdlet along with Identity and the InMemorys parameter. The resulting object is stored in the variable $x.

After the virtual settings have been created, commands 2 and 3 are used to modify the values of the SendToOutsideUnauthenticatedUsers and SendToExternalNetworks properties, respectively. Finally, command 4 is used to transform the virtual diagnostic header configuration settings into an actual collection of settings applied to the Redmond site. Note that this final command is mandatory. If you do not call the **Set-CsDiagnosticHeaderConfiguration** cmdlet, no settings will be applied to the site, and the virtual settings will disappear as soon as you end your Windows PowerShell session or delete the variable $x.

    $x = New-CsDiagnosticHeaderConfiguration -Identity site:Redmond -InMemory
    $x.SendToOutsideUnauthenticatedUsers = $True
    $x.SendToExternalNetworks = $True
    Set-CsDiagnosticHeaderConfiguration -Instance $x

## Detailed Description

Administrators have the option of attaching an ms-diagnostic header to each SIP message sent in an organization. This message (which is not visible to end users) contains information that might be useful in troubleshooting connection issues or in reporting errors. For example, the diagnostic header might contain error codes that enable the client application (for example, Lync) to take a predetermined course of action should a specific situation arise.

For SIP messages sent within your internal network, there’s little reason not to include these diagnostic headers: they have a minimal impact on message size and can be an invaluable tool for administrators trying to troubleshoot connectivity issues. However, diagnostic headers also contain information – such as the fully qualified domain names (FQDNs) of your SIP servers – that you might not want to make available to people outside the internal network. Because of this, the diagnostic header configuration settings enable you to decide whether you want diagnostic headers sent to users on external networks (such as users in a federated domain) and/or to outside users. (Outside users are users who have connected from outside the internal network and have not yet been authenticated.)

By default, diagnostic headers are not included in messages sent either to external networks or to unauthenticated users. However, you can modify the global diagnostic header settings to include headers to external networks and/or unauthenticated users. Alternatively, you can create custom settings at the site scope or at the service scope (for the 边缘服务器 or the Registrar service). That way, you can choose to include diagnostic headers on messages sent from one site, or through one 边缘服务器, while disallowing headers on messages sent from other sites or through other Edge Servers.

Custom diagnostic header settings are created using the **New-CsDiagnosticHeaderConfiguration** cmdlet. As noted, new settings can be created at either the site scope or the service scope (albeit for only the 边缘服务器 and the Registrar services). Keep in mind that you can only have one such settings collection per site or service. For example, suppose you try to create a new collection for the Redmond site, and that site already hosts a diagnostic header settings collection. In that case, your command will fail. Likewise, your command will fail if you try to create a new collection at the global scope.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsDiagnosticHeaderConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsDiagnosticHeaderConfiguration"}

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
<td><p>Unique identifier for the diagnostic header configuration settings to be created. To create a new settings collection at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;. To create a new settings collection at the service scope, use syntax like this: -Identity &quot;service:EdgeServer:atl-cs-001.litwareinc.com&quot;.</p>
<p>You cannot create new settings at the global scope. In addition, you cannot create new settings at the site or service scope if the specified site or service (for example, site:Redmond) already hosts a settings collection.</p></td>
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
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>SendToExternalNetworks</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, diagnostic headers will be attached to messages sent to external users.</p></td>
</tr>
<tr class="even">
<td><p><em>SendToOutsideUnauthenticatedUsers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, diagnostic headers will be attached to messages sent to outside users. Outside users are users who have connected from outside the internal network (for example, through a proxy server) and have not yet been authenticated.</p>
<p>The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsDiagnosticHeaderConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **New-CsDiagnosticHeaderConfiguration** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Diagnostics.DiagnosticHeaderSettings object.

## 另请参阅

#### 其他资源

[Get-CsDiagnosticConfiguration](get-csdiagnosticconfiguration.md)  
[Remove-CsDiagnosticHeaderConfiguration](remove-csdiagnosticheaderconfiguration.md)  
[Set-CsDiagnosticHeaderConfiguration](set-csdiagnosticheaderconfiguration.md)

