---
title: Remove-CsDiagnosticHeaderConfiguration
TOCTitle: Remove-CsDiagnosticHeaderConfiguration
ms:assetid: d71b79f1-49f2-4a6c-8b3e-ca909e8d5f49
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398941(v=OCS.15)
ms:contentKeyID: 49314401
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsDiagnosticHeaderConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes one or more of the diagnostic header configuration setting collections currently in use in your organization. Diagnostic header configuration settings determine whether SIP messages are accompanied by header information that can be useful in troubleshooting and error reporting. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsDiagnosticHeaderConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the diagnostic header configuration settings that have the Identity site:Redmond are removed.

    Remove-CsDiagnosticHeaderConfiguration -Identity site:Redmond

## EXAMPLE 2

The command shown in Example 2 deletes all the diagnostic header configuration settings that have been applied at the service scope. To do this, the command first calls the **Get-CsDiagnosticHeaderConfiguration** cmdlet and the Filter parameter. The filter value "service:\*" limits the returned data to those settings where the Identity begins with the characters "service:". This filtered collection is then piped to the **Remove-CsDiagnosticHeaderConfiguration** cmdlet, which deletes each item in the collection.

    Get-CsDiagnosticHeaderConfiguration -Filter service:* | Remove-CsDiagnosticHeaderConfiguration

## EXAMPLE 3

Example 3 deletes all the diagnostic header configuration settings that allow sending to external networks. To do this, the command first uses the **Get-CsDiagnosticHeaderConfiguration** cmdlet to return a collection of all the diagnostic header settings currently in use. This collection is piped to the **Where-Object** cmdlet, which picks out only those settings where the SendToExternalNetworks property is equal to True. These settings are then piped to the **Remove-CsDiagnosticHeaderConfiguration** cmdlet, which deletes each setting that allows sending to external networks.

    Get-CsDiagnosticHeaderConfiguration | Where-Object {$_.SendToExternalNetworks -eq $True} | Remove-CsDiagnosticHeaderConfiguration

## Detailed Description

Administrators have the option of attaching an ms-diagnostic header to each SIP message sent in their organization. This message (which is not visible to end users) contains information that might be useful in troubleshooting connection problems or in reporting errors. For example, the diagnostic header might contain error codes that enable the client application to take a predetermined course of action should a specific situation arise.

For SIP messages sent within your internal network, there’s little reason not to include these diagnostic headers: they have a minimal impact on message size and can be an invaluable tool for administrators trying to troubleshoot connectivity problems. However, diagnostic headers also contain information -- such as the fully qualified domain names (FQDNs) of your SIP servers -- that you might not want to make available to people outside the internal network. Because of this, the diagnostic header configuration settings enable you to decide whether you want diagnostic headers sent to users on external networks (such as users in a federated domain) and/or to outside users. (Outside users are users who have connected from outside the internal network and have not yet been authenticated.)

Alternatively, you can create custom settings at the site scope or at the service scope (for the 边缘服务器 or Registrar service). That way, you can choose to include diagnostic headers on messages sent from one site, or through one 边缘服务器, while disallowing headers on messages sent from other sites or through other Edge Servers.

Any new collections you create (at either the site or the service scope) can later be removed by using the **Remove-CsDiagnosticHeaderConfiguration** cmdlet. You can also run this cmdlet against the global collection. In that case, however, the global collection will not be removed because you can’t remove the global collection. Instead, the two properties contained in the global collection -- SendToExternalNetworks and SendToOutsideUnauthenticatedUsers -- will be reset to their default values (which, in each case, is False).

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsDiagnosticHeaderConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsDiagnosticHeaderConfiguration"}

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
<td><p>Unique identifier for the diagnostic header configuration settings to be removed. To remove settings configured at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;. To remove settings configured at the service scope, use syntax similar to this: -Identity &quot;service:EdgeServer:atl-edge-001.litwareinc.com&quot;.</p>
<p>The <strong>Remove-CsDiagnosticHeaderConfiguration</strong> cmdlet can also be run against the global configuration settings; in that case, use this syntax: –Identity global. Note, however, that the global settings will not actually be removed; instead, the properties found in the global settings will be reset to their default values.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.Diagnostics.DiagnosticHeaderSettings object. The **Remove-CsDiagnosticHeaderConfiguration** cmdlet accepts pipelined instances of the diagnostic header settings object.

## Return Types

None. Instead, the **Remove-CsDiagnosticHeaderConfiguration** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Diagnostics.DiagnosticHeaderSettings object.

## 另请参阅

#### 其他资源

[Get-CsDiagnosticHeaderConfiguration](get-csdiagnosticheaderconfiguration.md)  
[New-CsDiagnosticHeaderConfiguration](new-csdiagnosticheaderconfiguration.md)  
[Set-CsDiagnosticHeaderConfiguration](set-csdiagnosticheaderconfiguration.md)

